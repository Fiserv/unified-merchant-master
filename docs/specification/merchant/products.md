# Merchant Products

* **Description**: Merchant may have a variety of products. In UMM Fee, Equipment , Entitlement and Value added service everything is csondidered as a product. Products are grouped  into four different categories :

  * Equipment: Includes processing devices owned by the merchant, denoted by the product code prefix "EQ". See supported Equipments [here](?path=docs/specification/merchant/productAttributes_equipment.md)
  * Entitlement: Encompasses the range of cards supported by the merchant, identified by the product code prefix "ENTL". See supported Entitlements [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
  * Value Added Services (VAS): Consists of additional services consumed by the merchant, such as Transarmor, distinguished by the product code prefix "VAS". See supported Value Added Services [here](?path=docs/specification/merchant/productAttributes_VAS.md)
  * Fee: Represents the fees that apply to the merchant, labeled with the product code prefix "F". Se supported Fees [here](?path=docs/specification/merchant/productAttributes_fees.md)

Every product is defined by a group of attributes, with each attribute representing a specific aspect of the product.For instance, a merchant could have a Mastercard product with  Merchant Category Code  5521, Service Type Code 'F', and Floor Limit Amount 15.00. When we assign attribute ID 1 to the Merchant Category Code, ID 2 to the Service Type Code, and ID 3 to the Floor Limit Amount, Merchant will have attribute ID 1 set to 5521, attribute ID 2 set to 'F', and attribute ID 3 set to 15.00 for the Mastercard product. This means, product attributes are stored as key-value pairs for that specific Merchant and product combination.

Further, these attributes will be organized under logical **Domains**. Refer to the list of Domains with attribrutes [here](?path=docs/specification/domain_attribute_list.md)

* Example of a **Domain**: `feeAttr` is a **domain** that groups all  **Attributes** related to a fee product.

Here are few attributes linked to fee product:

* Frequency Indicator - Indicates whether is a monthly or daily fee
* Retail Date - When fee will be billed to merchant

* **How to Retrieve product & associated attributes from Snowflake Data tables?**:
  * Master Tables: Attributes are defined using below Master tables in UMM
    * UMM.DOMAIN_MASTER : Contains the definition of the Domain
    * UMM.ATTRIBUTE_MASTER: Contains the definition of the attributes and tied to Domain
    * UMM.PRDCT_MASTER: Contains the definition of products
    * umm.PRDCT_ATTRIBUTE_MASTER: Contains the association of attributes with a product
  * UMM.MERCHANT_PRODUCT: Contains available products for a merchant
  * UMM.MERCHANT_PRODUCT_ATTRIBUTES: Contains the ID of the UMM.ATTRIBUTE_MASTER for each merchant and product

* Explore MERCHANT_PRODUCT entity structure [Here](?path=docs/specification/merchant/merchantProduct.md)
* Explore MERCHANT_PRODUCT_ATTRIBUTES entity structure [Here](?path=docs/specification/merchant/ProductAttributes.md)

## Sample Queries

* Sample Query to pull all products for a merchant :

```text

    select *
    from umm.merchant_product p 
    where effective_end_date is null 
    and merchant_id = '302246063994' 
    and status = 'Y'

```

* Sample Query to pull the attributes for a merchant and product

```sql
select merchant_id , prdct_code, attribute_id , name attribute_name  , value  
from umm.merchant_product_attribute p , umm.attribute_master am
where effective_end_date is null
and prdct_code = 'ENTLVI'
and merchant_id = '255341441889'
and p.attribute_id = am.id
order by name
```

* Sample Query to fetch available products in UMM:

```text

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
