# Merchant Products

* **Description**:
* **API section**: `products`
* **Table Name**: UMM.MERCHANT_PRODUCT

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

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required  |

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

<!-- type: tab 
titles: UMM 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

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

### STATUS

* Description: This field indicates whether the product is active or not.
* API field: `isActive`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| N | Flag to indicate that product is inactive |
| Y | Flag to indicate that product is active |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Boolean  |    4     |    5    |    Available     |   Required     |  Allowed |     NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| N | Flag to indicate that product is inactive |
| Y | Flag to indicate that product is active |

<!-- type: tab-end -->
---

### UNIQUE_IDENTIFIER

* Description: This field serves as a unique identifier for a particular product
* API field: Not Available
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab-end -->
---

### FEE_TABLE_ID

* Description: TBD
* API field: `feeTableId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab-end -->
---

### WHOLESALE_CHARGE

* Description: TBD
* API field: `wholesaleAmountOrPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | Optional  |  Allowed   |        NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        4       |    11    |    Available    |      NA      |       NA     |  NA     |

<!-- type: tab-end -->
---

### RETAIL_CHARGE

* Description: TBD
* API field: `retailAmountOrPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | NA  |  NA   |    NA        |

<!-- type: tab-end -->