# Merchant
* **Description**: Stores basic but critical information about the merchant. Any merchant in UMM will always have this entity.
* **API section**: root 
* **Table Name**: UMM.MERCHANT 
## List of Fields:
### MERCHANT_ID
* Description: Backend unique identifier for a merchant.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |  Update  |
|--------|:--------------:|:----------:|:--------:|:--------:|:--------:|
| String |  BE specific   |     50     | Required | Required | Required |

<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |  Update  |
|--------|:--------------:|:----------:|:--------:|:--------:|:--------:|
| String |       12       |     12     | Required | Required | Required |

<!-- type: tab--> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |  Update  |
|--------|:--------------:|:----------:|:--------:|:--------:|:--------:|
| String |       11       |     11     | Required | Required | Required |

<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |  Update  |
|--------|:--------------:|:----------:|:--------:|:--------:|:--------:|
| String |       11       |     11     | Required | Required | Required |

<!-- type: tab-end -->

---

### PLATFORM_CODE 
* Description: Backend platform identifier e.g. North, South etc.
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

##### UMM Specification
| Type | Minimum Length | Max Length | Inquiry  |  Create  |  Update  |
|------|:--------------:|:----------:|:--------:|:--------:|:--------:|
| ENUM |      N/A       |     40     | Returned | Required | Required |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)
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
| Type | Minimum Length | Max Length | Inquiry  |  Create  | Update |
|------|:--------------:|:----------:|:--------:|:--------:|:------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |

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
| Type | Minimum Length | Max Length | Inquiry  |  Create  | Update |
|------|:--------------:|:----------:|:--------:|:--------:|:------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |

- **Valid Values**:
    
    | Options  | Description     | 
    |----------|:----------------|
    | OUTLET   | Outlet level    |
    | CHAIN    | Chain level     |
    | CORP     | Corporate level |
    | AGENT    | Agent level     |
    | BANK     | Bank level      |
    | BUSINESS | Business level  |

 ![North Hierarchy!](/assets/images/NorthHierarchy.png "North Hierarchy")

<!-- type: tab--> 

##### South Specification
| Type | Minimum Length | Max Length | Inquiry  |  Create  | Update |
|------|:--------------:|:----------:|:--------:|:--------:|:------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |

- **Valid Values**:

|  Options   | Description     | 
|:----------:|:----------------|
|    ROOT    | Root level      |
|    CORP    | Corporate level |
|   OUTLET   | Location level  |

<!-- type: tab-->

##### GMA Specification
| Type | Minimum Length | Max Length | Inquiry  |  Create  | Update |
|------|:--------------:|:----------:|:--------:|:--------:|:------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |

- **Valid Values**:

|  Options   | Description     | 
|:----------:|:----------------|
|   GROUP    | Group level     |
|  SUBGROUP  | Sub-Group level |
|   MEMBER   | Member level    |

<!-- type: tab-end -->