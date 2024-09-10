# Product Attributes

* **Description**: Merchant may have multiple products, with  each product containing unique details represented by specific attributes. For example, a merchant could have a Mastercard product with associated values for various fields like Merchant Category Code (with a value of 5521), Service Type Code (with a value of F), and Floor Limit Amount (with a value of 15.00). By assigning attribute ID 1 to Merchant Category Code, ID 2 to Service Type Code, and ID 3 to Floor Limit Amount, the merchant would have attribute ID 1 with a value of 5521, attribute ID 2 with a value of F, and attribute ID 3 with a value of 15.00 for Master Card product.

These attributes will be organized under logical **Domains** and stored as key-value(s) pair for a merchant  and product combination. 

* Example of a **Domain**: feeAttr is a **domain** that groups all fields called as **Attributes** those defines how a fee will be processed. Example of some attributes associated with fee products are :
      *Frequency Indicator - Indicates whether is a monthly or daily fee 
      *Retail Date - When fee will be billed to merchant 

* **API section**: `products.[entitlements||valueAddedServices||fees||equipments].attributes`
* **Table Name**: UMM.MERCHANT_PRODUCT_ATTRIBUTES 

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

* **Example**:Product attribute payload for fee product. 

```json
  "attributes": {
    "feeAttr": {
      "processingInd": {
        "values": ["1"]
      },
      "isAnnualFee": {
        "values": ["YES"]
      },
      "retailDate": {
        "values": ["2024-05-29"]
      },
      "wholesaleDate": {
        "values": ["2024-05-29"]
      },
      "frequencyInd": {
        "values": ["MONTHLY"]
      }
    }
  }
```


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


* Description: Attribute id 
* API field: NA

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Number  |      0         |     38     |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### VALUE

* Description: Value of the Attribute
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


### Product Attributes

* See **Entitlements** attribute [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* See **Fees** attrubute [here](?path=docs/specification/merchant/productAttributes_fees.md)
* See **Value Added Services (VAS)** attribute [here](?path=docs/specification/merchant/productAttributes_VAS.md)
