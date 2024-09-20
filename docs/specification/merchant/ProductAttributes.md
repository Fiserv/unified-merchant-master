# Product Attributes

* **Description**: Merchant may have multiple products ( Fees, Equipment , Entitlement , Value added Products etc).Each product has its own unique characteristic represented by a specific attribute. For instance, a merchant could have a Mastercard product with  Merchant Category Code  5521, Service Type Code 'F', and Floor Limit Amount 15.00. When we assign attribute ID 1 to the Merchant Category Code, ID 2 to the Service Type Code, and ID 3 to the Floor Limit Amount, Merchant will have attribute ID 1 set to 5521, attribute ID 2 set to 'F', and attribute ID 3 set to 15.00 for the Mastercard product. This means, product attributes are stored as key-value pairs for that specific Merchant and product combination.

Further, these attributes will be organized under logical **Domains**. Refer [List of Domains with  attriburtes here] (?path=docs/specification/domain_attribute_list.csv)

* Example of a **Domain**: `feeAttr` is a **domain** that groups all  **Attributes** which  determine how a fee will be processed. Here are some attributes linked to fee products:

      *Frequency Indicator - Indicates whether is a monthly or daily fee 
      *Retail Date - When fee will be billed to merchant 

* **API section**: `products.[entitlements||valueAddedServices||fees||equipments].attributes`

* Sample Product attribute payload:

```json
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
```

* **Example**:Product attribute payload for Value added product.

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

* **Example**:Product attribute payload for Entitlement product.

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

* **Example**:Product attribute payload for Fee product.

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

* Sample Query to pull the attributes  for a merchant and product :

```text

select merchant_id , prdct_code, attribute_id , name attribute_name  , value  
from umm.merchant_product_attribute p , umm.attribute_master am
where effective_end_date is null
and prdct_code = 'ENTLVI'
and merchant_id = '255341441889'
and p.attribute_id = am.id
order by name

```

* **Table Name**: UMM.MERCHANT_PRODUCT_ATTRIBUTES
* **Description**: Stores attributes associated with a product for a merchant.

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String   | 12        |    12        | Required   | Required   | Required   | Required     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required  |       NA     |

<!-- type: tab-end -->

---

### PLATFORM_CODE

* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:
* See supported platforms and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

<!-- type: tab-end -->
---

### PRDCT_CODE

* Description: The product code associated with the product and defined by UMM API.
* API field: productCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type   | Minimum Length | Max Length | Inquiry | Create | Update | Delete |
|--------|:--------------:|:----------:|:-------:|:------:|:------:|:------:|
| Enum   |   NA   |   NA  |  Available |  Required   |     NA      |   NA   |

* See supported Entitlements [here](?path=docs/specification/products_entitlements.md)
* See supported Value Added Services [here](?path=docs/specification/products_vas.md)
* See supported Fees [here](?path=docs/specification/products_fees.md)
* See supported Equipments [here](?path=docs/specification/products_equipments.md)

<!-- type: tab-end -->
---

### UNIQUE_IDENTIFIER

* Description: This field serves as a unique identifier for a particular product
* API field: `uniqueIdentifier`
* Field Specification:

<!-- type: tab 
titles: UMM 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50       |    Available     | NA     |      NA       |    NA         |

<!-- type: tab-end -->
---

### ATTRIBUTE_ID

* Description: Attribute ID that represents a specific characteristic of a product.
* API field: NA

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Number  |      NA         |     38     |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

* See **Entitlements** attribute [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* See **Fees** attrubute [here](?path=docs/specification/merchant/productAttributes_fees.md)
* See **Value Added Services (VAS)** attribute [here](?path=docs/specification/merchant/productAttributes_VAS.md)
* See **Equipment** attribute [here](?path=docs/specification/merchant/productAttributes_equipment.md)

---

### VALUE

* Description: Value of the specific Attribute
* API field: NA
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type     | Minimum Length | Max Length | Inquiry | Create | Update |
|----------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar  |      1       |    200     |   Available   |  Optional   |  Allowed   |

<!-- type: tab-end -->

---
