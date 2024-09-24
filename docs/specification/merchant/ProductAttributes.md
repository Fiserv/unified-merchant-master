# Product Attributes

* **Table Name**: `UMM.MERCHANT_PRODUCT_ATTRIBUTES`
* **Description**: Stores attributes associated with a product for a merchant.
* **API section**: `products.[entitlements||valueAddedServices||fees||equipments].attributes`

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
