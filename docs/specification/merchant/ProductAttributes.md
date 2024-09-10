# Product Attributes

* **Description**: Merchant may have multiple products, with  each product containing unique details represented by specific attributes. For example, a merchant could have a Mastercard product with associated values for various fields like Merchant Category Code (with a value of 5521), Service Type Code (with a value of F), and Floor Limit Amount (with a value of 15.00). By assigning attribute ID 1 to Merchant Category Code, ID 2 to Service Type Code, and ID 3 to Floor Limit Amount, the merchant would have attribute ID 1 with a value of 5521, attribute ID 2 with a value of F, and attribute ID 3 with a value of 15.00 for Master Card product.

These attributes will be organized under logical **Domains** and stored as key-value(s) pair for a merchant  and product combination. 

* Example of a **Domain**: feeAttr is a **domain** that groups all fields called as **Attributes** those defines how a fee will be processed. Example of some attributes associated with fee products are :
      * Frequency Indicator - Indicates whether is a monthly or daily fee 
      * Retail Date - When fee will be billed to merchant 

* **API section**: productAttributes
* **Table Name**: UMM.MERCHANT_PRODUCT_ATTRIBUTES 

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
* API field: platformCode
* Field Specification: See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)


<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |     40      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### PRDCT_CODE

* Description: Unique identifier assigned to a specific product .
* API field: productCode
* Field Specification: _< $ sample - to be updated/checked>_  See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)


<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |    100      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### UNIQUE_IDENTIFIER

* Description: This field serves as a unique identifier for a particular product
* API field: < _Not known / NA _ >
* Field Specification: _< $ sample - to be updated/checked>_  See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |     50      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### ATTRIBUTE_ID 

* _< $ sample - to be updated/checked>_
* Description: UMM defined attribute ID. See the query above for further details.
* API field: Not applicable - domain and attribute name along with respective descriptions are returned. Sample payload shows the domain  and the list of attributes under that domain.

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
* API field: values[0]  _< $ sample - to be updated/checked>_
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type     | Minimum Length | Max Length | Inquiry | Create | Update |
|----------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar  |      1       |    200     |   Available   |  Optional   |  Allowed   |

*  _< $ sample - to be updated/checked>_
  
<!-- type: tab-end -->

---

### Product Attributes

* See **Entitlements** attribute [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* See **Fees** attrubute [here](?path=docs/specification/merchant/productAttributes_fees.md)
* See **Value Added Services (VAS)** attribute [here](?path=docs/specification/merchant/productAttributes_VAS.md)
