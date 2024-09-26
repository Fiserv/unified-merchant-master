# Merchant Products

* **Table Name**: UMM.MERCHANT_PRODUCT  
* **Description**: Stores all the products a merchant has.
* **API section**: `products`

* Explore more about products [Here] (?path=?docs/specification/merchant/products.md)

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

* See supported Entitlements [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* See supported Value Added Services [here](?path=docs/specification/merchant/productAttributes_VAS.md)
* See supported Fees [here](?path=docs/specification/merchant/productAttributes_fees.md)
* See supported Equipments [here](?docs/specification/merchant/productAttributes_equipment.md)

Supported  Products  can be retrieved using Product Inquiry API Call.

```http

GET https://connect.fiservapis.com/unifiedmerchantmaster/internal/v1/products?platformCode=$platform&productCategory=$category HTTP/1.1
x-consumer-name: $consume-name
x-encrypted-data: true

$category can have below Values: 

          - ENTITLEMENT
          - VAS
          - EQUIPMENT
          - PAYMENT_FEATURE
          - FEE

$platform can have below Values: 

          - NORTH
          - OMAHA
          - SOUTH
          - OMNIPAY26
          - OMNIPAY21

```

OR Sample Query to fetch available products from snowflake:

```text

      select *  
      from umm.prdct_master 
      where is_active = 'Y'

```

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

* Description: This field serves as a unique identifier for a particular product. E.g. For equipment product, it will have Equipment#
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

---
