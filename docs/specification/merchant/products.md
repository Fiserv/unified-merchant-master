# Merchant Products

* **Description**: Merchant has a list of products to represent subscribed card entitlements,fees, payment features, value added services and equipments. Each product contains various attributes that highlight different aspects of the product. These attributes are categorized under logical domains and stored as key-value pairs.

  * Example of a **Domain**: `feeAttr` is a **domain** that groups all fields called as **Attributes** those defines  processing logic of the fee. Example of some attributes are:
    * Frequency Indicator - Indicates the frequency at which the fee will be billed(e.g. Monhtly or Daily)
    * Retail Date - date When fee will be billed to merchant

## Domain Attribute List

* Explore Entitlement Domain & Attribute [Here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* Explore Value Added Services Domain & Attribute [Here](?path=docs/specification/merchant/productAttributes_VAS.md)
* Explore Fee Domain & Attribute [Here](?path=docs/specification/merchant/productAttributes_fees.md)
* Explore Equipment Domain & Attribute [here](?path=docs/specification/merchant/productAttributes_equipment.md)

## Data Retrieval

* **How to Retrieve product & associated attributes from Snowflake Data tables?**:
  * Master Tables: Attributes are defined using below Master tables in UMM
    * UMM.DOMAIN_MASTER : Contains the definition of the Domain
    * UMM.ATTRIBUTE_MASTER: Contains the definition of the attributes and tied to Domain
    * UMM.PRDCT_MASTER: Contains the definition of products
    * umm.PRDCT_ATTRIBUTE_MASTER: Contains list of attributes associated with a product
  * UMM.MERCHANT_PRODUCT: Contains available products for a merchant
  * UMM.MERCHANT_PRODUCT_ATTRIBUTES: Contains the ID of the UMM.ATTRIBUTE_MASTER for each merchant and product

## Entities

* Explore [**MERCHANT PRODUCT entity**](?path=docs/specification/merchant/merchantProduct.md)
* Explore [**MERCHANT PRODUCT ATTRIBUTES entity**]  (?path=docs/specification/merchant/ProductAttributes.md)

## Sample Queries

### Sample Query to pull all products for a merchant

```sql

select *
from umm.merchant_product p 
where effective_end_date is null 
and merchant_id = '302246063994' 
and status = 'Y'

```

### Sample Query to pull the attributes for a merchant and product

```sql
select merchant_id , prdct_code, attribute_id , name attribute_name  , value  
from umm.merchant_product_attribute p , umm.attribute_master am
where effective_end_date is null
and prdct_code = 'ENTLVI'
and merchant_id = '255341441889'
and p.attribute_id = am.id
order by name
```

### Sample Query to fetch associated attributes for a product

```sql

select DOMAIN, P.prdct_code, p.PRDCT_SHORT_DESC , AM.ID AS ATTRIBUTE_ID, AM.NAME ATTRIBUTE_NAME 
from UMM.PRDCT_MASTER P , UMM.PRDCT_ATTRIBUTE_MASTER PA , UMM.ATTRIBUTE_MASTER AM , UMM.DOMAIN_MASTER DM
where P.PRDCT_CODE = 'ENTLVI'
and p.PRDCT_CODE = PA.PRDCT_CODE
and PA.ATTRIBUTE_ID = AM.ID
and AM.DOMAIN_ID = DM.ID

```

### Sample Query to fetch available products in UMM

```sql

select *  
from umm.prdct_master 
where is_active = 'Y'

```

## Sample Product Payload

```json
{
  "productCode#1": "some product code",
  "productLongDesc": "some description",
  "attributes": {
    "domain#1": {
      "domainDescription": "domain #1 description",
      "attribute#1": {
        "attributeDescription": "attribute description",
        "values": ["some value"]
      },
      "attribute#2": {
        "attributeDescription": "attribute description",
        "values": ["some value"]
      }
    },
    "domain#2": {
      "domainDescription": "domain #2 description",
      "attribute#1": {
        "attributeDescription": "attribute description",
        "values": ["some value"]
      }
    }
  }
}
```

### Sample payload for Value Added Services (VAS) product

```json
{
  "productCode": "VASTRNSARM",
  "productLongDesc": "This Program Enables Pci Compliance By Allowing A Merchant To Receive A Daily File Of Transarmor Tokenized Transaction Data.  The Data Included May Contain Authorization Data, Settlement Data, Or Both.",
  "attributes": {
    "serviceAttr": {
      "encryptServiceLevelCode": {
        "values": [
          "NONE"
        ]
      },
      "encryptTokenOverrideIndicator": {
        "values": [
          "NO"
        ]
      },
      "encryptTokenHierarchyCode": {
        "values": [
          "NONE"
        ]
      },
      "encryptTypeCode": {
        "values": [
          "NONE"
        ]
      }
    }
  }
}
```

### Sample payload for Entitlement product

```json
{
  {
  "productCode": "ENTLVI",
  "productLongDesc": "Visa Entitlement",
  "attributes": {
    "entitlementAttr": {
      "mccCode": {
        "values": [
          "5411"
        ]
      },
      "discountMethodCode": {
        "values": [
          "NONE"
        ]
      },
      "pricingPlanCode": {
        "values": [
          "000"
        ]
      },
      "clearingPlanCode": {
        "values": [
          "000"
        ]
      },
      "edcCode": {
        "values": [
          "NO_SERVICE"
        ]
      },
      "effectiveDate": {
        "values": [
          "2023-09-30"
        ]
      },
      "serviceTypeCode": {
        "values": [
          "FULL_SERVICE"
        ]
      }
    }
  }
}
}
```

### Sample payload for Fee product

```json
{
  "productCode": "FNONSWIPEDDSCNT",
  "productLongDesc": "Non Swiped Discount",
  "attributes": {
    "feeAttr": {
      "processingInd": {
        "values": [
          "1"
        ]
      },
      "retailDate": {
        "values": [
          "2024-07-16"
        ]
      },
      "wholesaleDate": {
        "values": [
          "2024-07-16"
        ]
      },
      "frequencyInd": {
        "values": [
          "DAILY"
        ]
      }
    }
  }
}
```
