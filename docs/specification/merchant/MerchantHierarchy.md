# Merchant Hierarchy
* **Description**: Stores essential information of management hierarchy for the merchant.
* **API schema**: `MerchantHierarchies` 
* **Table Name**: `UMM.merchant_hierarchy` 

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
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant. 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required  |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |  Required  | Required | Required |    NA     |

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
| String  | 5        |    9        |    Required     | Required     | Required |    Required     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     | 
| OMNIPAY26     |  Omnipay Backend ( GMA)      | 
| SOUTH     |     South  Backend | 
| OMNIPAY21     |    Omnipay ( Australia)    |      |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |  |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 9        |    9        |    Required     | NA     | NA |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |      

<!-- type: tab-end -->


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
| MEMBER     |     This identifies the actual processing Merchant assigned to a location in Omnipay  |
|  AGENT   |   AGENT hierarchy level (040)  in North   |
|  CHAIN   |   CHAIN hierarchy level (020)  in North   |
|  BANK   |    Bank  hierarchy level  (050) in North   |
|  BILL_TO_ADDR   | BILL_TO_ADDR hierarchy level (019)  in North   |
|  CORP   |   Corporation  hierarchy level (030)  in North    |
|  BUSINESS   |  Business hierarchy level (060)  in North     |
|  OUTLET   |    Outlet  hierarchy level (010)   in North  |  

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | NA   | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  AGENT   |   AGENT hierarchy level (040)  in North   |
|  CHAIN   |   CHAIN hierarchy level (020)  in North   |
|  BANK   |    Bank  hierarchy level  (050) in North   |
|  BILL_TO_ADDR   | BILL_TO_ADDR hierarchy level (019)  in North   |
|  CORP   |   Corporation  hierarchy level (030)  in North    |
|  BUSINESS   |  Business hierarchy level (060)  in North     |
|  OUTLET   |    Outlet  hierarchy level (010)   in North  |  

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 5        |    9        |    Available     | Required     | NA |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| GROUP     |     Highest level in Omnipay Hierarchy   | 
| SUB_GROUP     |     This represents the next level in Omnipay Hierarchy below Group level   | 
| MEMBER     |     This identifies the actual processing Merchant assigned to a location in Omnipay |

<!-- type: tab-end -->
---

### HIERARCHY_SEQ
* Description: Dynamic sequence depending  on hierarchy level for a merchant 
* API field: `hierarchySeq`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    5        |    Available     | NA     | NA |    NA |         |


<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA |         |


<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | NA     | NA |    NA |         |


<!-- type: tab-end -->
---


### HIERARCHY_MERCHANT_ID
* Description: Unique identifier assigned to a merchant within a hierarchical system - e.g. Business number associated with a specific merchant 
* API field: `hierarchyMerchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Available     | Required     | NA |    NA |    

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
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Available     | Required     | NA |    NA |   

<!-- type: tab-end -->
---

### HIERARCHY_NAME
* Description: Designated name of a specific level or position within a merchant organization.
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
 Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50        |    Available     | NA     | NA |    NA |    

<!-- type: tab-end -->
