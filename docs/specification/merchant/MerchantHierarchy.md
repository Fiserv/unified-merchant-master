# Merchant Hierarchy
* **Description**: Stores essential information of management hierarchy for the merchant.
* **API section**: root 
* **Table Name**: UMM.MERCHANT 

## List of Fields:

### MERCHANT_ID
* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 34        |    50        |    NA     | Required     | Required |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | NA   | Required   | Required   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### PLATFORM_CODE
* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 5        |    50        |    NA     | NA     | Required |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | NA   | NA   | Required   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### HIERARCHY_LEVEL_CODE
* Description: Unique identifier of the merchant to represent the management hierarchy.
* API field: `hierarchyLevelCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    12        |    Available     | Required     | NA |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| GROUP     |     Highest level in Omnipay Hierarchy   | 
| SUB_GROUP     |     This represents the next level in Omnipay Hierarchy below Group level   | 
| OUTLET     |     North backend's 010-OUTLET hierarchy level   | 
| BILL_TO_ADDR     |     North backend's 019-BILL_TO_ADDR hierarchy level   | 
| CHAIN     |     North backend's 020-CHAIN hierarchy level   | 
| AGENT     |     North backend's 040-AGENT hierarchy level   | 
| PRIN     |     North backend's 050-PRIN hierarchy level   | 
| MEMBER     |     This identifies the actual processing Merchant assigned to a location   | 
| SYSTEM     |     North backend's 060-SYSTEM hierarchy level   | 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | NA   | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| GROUP     |     Highest level in Omnipay Hierarchy   | 
| SUB_GROUP     |     This represents the next level in Omnipay Hierarchy below Group level   | 
| OUTLET     |     North backend's 010-OUTLET hierarchy level   | 
| BILL_TO_ADDR     |     North backend's 019-BILL_TO_ADDR hierarchy level   | 
| CHAIN     |     North backend's 020-CHAIN hierarchy level   | 
| AGENT     |     North backend's 040-AGENT hierarchy level   | 
| PRIN     |     North backend's 050-PRIN hierarchy level   | 
| MEMBER     |     This identifies the actual processing Merchant assigned to a location   | 
| SYSTEM     |     North backend's 060-SYSTEM hierarchy level   | 

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### HIERARCHY_MERCHANT_ID
* Description: Unique identifier assigned to a merchant within a hierarchical system.
* API field: `hierarchyMerchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    100        |    Available     | Required     | NA |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### HIERARCHY_NAME
* Description: Designated name of a specific level or position within a merchant organizational.
* API field: `hierarchyName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50        |    Available     | Required     | NA |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
