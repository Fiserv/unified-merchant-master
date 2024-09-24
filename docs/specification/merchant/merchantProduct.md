# Merchant Products

* **Description**: Merchant may have a variety of products. In UMM Fee, Equipment , Entitlement and Value added service everything is csondidered as a product. Products are grouped  into four different categories :

  * Equipment: Includes processing devices owned by the merchant, denoted by the product code prefix "EQ". See supported Equipments [here](?path=docs/specification/products_equipments.md)
  * Entitlement: Encompasses the range of cards supported by the merchant, identified by the product code prefix "ENTL". See supported Entitlements [here](?path=docs/specification/products_entitlements.md)
  * Value Added Services (VAS): Consists of additional services consumed by the merchant, such as Transarmor, distinguished by the product code prefix "VAS". See supported Value Added Services [here](?path=docs/specification/products_vas.md)
  * Fee: Represents the fees that apply to the merchant, labeled with the product code prefix "F". Se supported Fees [here](?path=docs/specification/products_fees.md)

Every product is defined by a group of attributes, with each attribute representing a specific aspect of the product.For instance, a merchant could have a Mastercard product with  Merchant Category Code  5521, Service Type Code 'F', and Floor Limit Amount 15.00. When we assign attribute ID 1 to the Merchant Category Code, ID 2 to the Service Type Code, and ID 3 to the Floor Limit Amount, Merchant will have attribute ID 1 set to 5521, attribute ID 2 set to 'F', and attribute ID 3 set to 15.00 for the Mastercard product. This means, product attributes are stored as key-value pairs for that specific Merchant and product combination.

Further, these attributes will be organized under logical **Domains**. Refer to the list of Domains with attribrutes [here](?path=docs/specification/domain_attribute_list.md)

* Example of a **Domain**: `feeAttr` is a **domain** that groups all  **Attributes** related to a fee product.

Here are some attributes linked to fee product:

* Frequency Indicator - Indicates whether is a monthly or daily fee
* Retail Date - When fee will be billed to merchant

* **How to Retrieve product & associated attributes from Snowflake Data tables?**:
  * Master Tables: Attributes are defined using below Master tables in UMM
    * UMM.DOMAIN_MASTER : Contains the definition of the Domain
    * UMM.ATTRIBUTE_MASTER: Contains the definition of the attributes and tied to Domain
    * UMM.PRDCT_MASTER: Contains the definition of products
    * umm.PRDCT_ATTRIBUTE_MASTER: Contains the associated attributes for a product
  * UMM.MERCHANT_PRODUCT: Contains available products for a merchant 
  * UMM.MERCHANT_PRODUCT_ATTRIBUTES: Contains the ID of the UMM.ATTRIBUTE_MASTER for each merchant and product
  
  * Sample Query to pull the attributes:

* Sample Query to pull all products for a merchant :

```text

    select *
    from umm.merchant_product p 
    where effective_end_date is null 
    and merchant_id = '302246063994' 
    and status = 'Y'

```

* Sample Query to fetch available products in UMM:

```text

      select *  
      from umm.prdct_master 
      where is_active = 'Y'

```

* **Table Name**: UMM.MERCHANT_PRODUCT  
* **Description**: Stores all the products a merchant has.
* **API section**: `products`

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required  |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       12       |      12    |    Required    | Required   | Required   | Required  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required |    NA     |

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
* API field: `productCode`
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type   | Minimum Length | Max Length | Inquiry | Create | Update | Delete |
|--------|:--------------:|:----------:|:-------:|:------:|:------:|:------:|
| Enum   |   NA   |   NA  |  Available |  Required   |     Required      |   Required   |

** PRDCT_CODE is required to update or delete corresponding product 

* See supported Entitlements [here](?path=docs/specification/products_entitlements.md)
* See supported Value Added Services [here](?path=docs/specification/products_vas.md)
* See supported Fees [here](?path=docs/specification/products_fees.md)
* See supported Equipments [here](?path=docs/specification/products_equipments.md)

<!-- type: tab-end -->
---

### STATUS

* Description: This field indicates whether the product is active or not.
* API field: `isActive`
* Field Specification:

<!-- type: tab 
titles: UMM 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:

|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| N | Flag to indicate that product is inactive |
| Y | Flag to indicate that product is active |

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
| String  | 1        |    50        |    Available     | NA     |      Allowed       |    NA         |


<!-- type: tab-end -->
---

### FEE_TABLE_ID

* Description: TBD
* API field: `feeTableId`
* Field Specification:

<!-- type: tab 
titles: UMM 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |


<!-- type: tab-end -->
---

### WHOLESALE_CHARGE

* Description: TBD
* API field: `wholesaleAmountOrPercent`
* Field Specification: Wholesale charge associated with a Fee product.

<!-- type: tab 
titles: UMM
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |


<!-- type: tab-end -->
---

### RETAIL_CHARGE

* Description: TBD
* API field: `retailAmountOrPercent`
* Field Specification: Retail  charge associated with a Fee product.

<!-- type: tab 
titles: UMM
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |


<!-- type: tab-end -->
