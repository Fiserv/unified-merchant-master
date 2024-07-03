# Merchant
* **Description**: Stores essential information about merchants, including contact details, business type, and contractual data, ensuring efficient transaction processing and management. Every merchant has an entry in this critical repository.
* **API section**: root 
* **Table Name**: UMM.MERCHANT 
## List of Fields:
### MERCHANT_ID
* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   |   Minimum Length   | Max Length | Inquiry  |  Create  |  Update  |    Delete    |
|--------|:------------------:|:----------:|:--------:|:--------:|:--------:|:------------:|
| String |  Back-end specific |     50     |          |          |          |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       12       |     50     | Required | Required | Not Required |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       8        |     50     | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->

---

### PLATFORM_CODE 
* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
|        |       -        |     -      |     -    |          |              |       NA     |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
|        |       -        |     -      | Required | Required | Not Required |       NA     |

<!-- type: tab--> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       8        |     50     | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->

### EFFECTIVE_START_DATE 
* Description: Effective date from when the user can start fetching the snapshot data for a particular merchant and platform using UMM DB
* API field: `effectiveStartDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
|        |       -        |     -      |     -    |          |              |       NA     |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create     |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:-------------:|:------------:|:------------:|
|        |       -        |     -      | Required | Not Required  | Not Required |       NA     |

<!-- type: tab--> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### HIERARCHY_LEVEL_CODE 
* Description: Indicates the hierarchy level of the merchant.
* API field: hierarchyLevelCode
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

- **Valid Values**:

  | Platform  |  Options   | Description     | 
  |:---------:|:----------:|:----------------|
  |   NORTH   |   OUTLET   | Outlet level    |
  |   NORTH   |   CHAIN    | Chain level     |
  |   NORTH   |    CORP    | Corporate level |
  |   NORTH   |   AGENT    | Agent level     |
  |   NORTH   |    BANK    | Bank level      |
  |   NORTH   |  BUSINESS  | Business level  |
  | OMNIPAY26 |   GROUP    | Group level     |
  | OMNIPAY26 |  SUBGROUP  | Sub-Group level |
  | OMNIPAY26 |   MEMBER   | Member level    |
  |   SOUTH   |    ROOT    | Root level      |
  |   SOUTH   |    CORP    | Corporate level |
  |   SOUTH   |   OUTLET   | Location level  |


<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

- **Valid Values**:
    
    | Options  | Description     | 
    |----------|:----------------|
    | OUTLET   | Outlet level    |
    | CHAIN    | Chain level     |
    | CORP     | Corporate level |
    | AGENT    | Agent level     |
    | BANK     | Bank level      |
    | BUSINESS | Business level  |

###### North Hierarchy Explained
 ![North Hierarchy!](/assets/images/NorthHierarchy.png "North Hierarchy")

<!-- type: tab--> 

##### South Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

- **Valid Values**:

|  Options   | Description     | 
|:----------:|:----------------|
|    ROOT    | Root level      |
|    CORP    | Corporate level |
|   OUTLET   | Location level  |

<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

- **Valid Values**:

|  Options   | Description     | 
|:----------:|:----------------|
|   GROUP    | Group level     |
|  SUBGROUP  | Sub-Group level |
|   MEMBER   | Member level    |

<!-- type: tab-end -->

### STATUS_CODE 
* Description: Indicates the status of the merchant.
* API field: statusCode
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
|North| Enum |      6       |     18     | Response | Required |  N/A   |       NA     |
|GMA| Enum |      3       |     3     | Response | Required |  N/A   |       NA     |

- **Valid Values**:


| Platform  |  Options   | Description     | 
|:---------:|:----------:|:----------------|
|NORTH|PENDING|PENDING|
|NORTH|CANCELLED_FRAUD|CANCELLED_FRAUD|
|NORTH|CANCELLED_CREDIT|CANCELLED_CREDIT|
|NORTH|CANCELLED_MERCHANT|CANCELLED_MERCHANT|
|NORTH|ACTIVE|ACTIVE|
|GMA|CANCELLED_CREDIT|CANCELLED_CREDIT|
|GMA|ACTIVE_BANKRUPT|ACTIVE_BANKRUPT|
|GMA|CANCELLED_MNGMTREQ|CANCELLED_MNGMTREQ|
|GMA|CANCELLED_NO_LONGER_ACC|CANCELLED_NO_LONGER_ACC|
|GMA|CANCELLED_DUPLICATE_ACCOUNT|CANCELLED_DUPLICATE_ACCOUNT|
|GMA|CANCELLED_NEW_OWN|CANCELLED_NEW_OWN|
|GMA|CANCELLED_BANKRUPT|CANCELLED_BANKRUPT|
|GMA|CANCELLED_BY_MERCHANT|CANCELLED_BY_MERCHANT|
|GMA|CANCELLED_APPLY_FEE|CANCELLED_APPLY_FEE|
|GMA|CANCELLED_TERMRTND|CANCELLED_TERMRTND|
|GMA|CANCELLED_SOLDBUSNS|CANCELLED_SOLDBUSNS|
|GMA|ACTIVE_HOLD_PAY|ACTIVE_HOLD_PAY|
|GMA|CANCELLED_MERCHANT_NO_REASON|CANCELLED_MERCHANT_NO_REASON|
|GMA|CANCELLED_MRCHCHBS|CANCELLED_MRCHCHBS|
|GMA|DORMANT|DORMANT|
|GMA|CANCELLED_FRAUD|CANCELLED_FRAUD|
|GMA|CANCELLED_DIS_SATISFACTION|CANCELLED_DIS_SATISFACTION|
|GMA|CANCELLED_RISK|CANCELLED_RISK|
|GMA|CANCELLED_EMERGENCY|CANCELLED_EMERGENCY|
|GMA|CANCELLED_PRTNRSPLT|CANCELLED_PRTNRSPLT|
|GMA|CANCELLED_BUSINESS_CLOSED|CANCELLED_BUSINESS_CLOSED|
|GMA|CANCELLED_POSTECISS|CANCELLED_POSTECISS|
|GMA|CANCELLED_NOACTONAC|CANCELLED_NOACTONAC|
|GMA|CANCELLED_BANKRPT|CANCELLED_BANKRPT|
|GMA|CANCELLED_DECEASED|CANCELLED_DECEASED|
|GMA|CANCELLED_REASON_UNKNOWN|CANCELLED_REASON_UNKNOWN|
|GMA|CANCELLED_LTRCLOSMR|CANCELLED_LTRCLOSMR|
|GMA|CANCELLED_POORSERV|CANCELLED_POORSERV|
|GMA|CANCELLED_ATREQEMS|CANCELLED_ATREQEMS|
|GMA|ACTIVE|ACTIVE|
|GMA|CANCELLED_PROBWSREP|CANCELLED_PROBWSREP|
|GMA|CANCELLED_CHANGE_OWNER|CANCELLED_CHANGE_OWNER|
|GMA|CANCELLED_ACNTNEVRQ|CANCELLED_ACNTNEVRQ|
|GMA|CANCELLED|CANCELLED|
|GMA|SUSPENDED|SUSPENDED|
