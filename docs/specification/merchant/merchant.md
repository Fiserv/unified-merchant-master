![image](https://github.com/Fiserv/unified-merchant-master/assets/173451067/3a00f6ea-4c4a-4333-a61b-7f8a536fb824)
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
| String |          12        |     50     |          |          |          |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       12       |     12     | Required | Required | Not Required |       NA     |

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
---

### HIERARCHY_LEVEL_CODE 
* Description: Unique identifier assigned to an outlet or a specific level within a hierarchical structure of a merchant's business. 
* API field: `hierarchyId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create     |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:-------------:|:------------:|:------------:|
|        |       -        |     -      | Required | Not Required  | Not Required |       NA     |


<!-- type: tab--> 

##### South Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |


<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| Enum |      N/A       |     10     | Response | Required |  N/A   |       NA     |

<!-- type: tab-end -->
---

### STORE_ID
* Description: Unique identifier of the merchant's store.
* API field: `storeId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create     |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:-------------:|:------------:|:------------:|
|        |       1        |    10      | Required |    Required   |    Required  |       NA     |


<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create     |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:-------------:|:------------:|:------------:|
|        |       1        |    8       | Required |    Required   |    Required  |       NA     |

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

### DBA_NAME
* Description: Official merchant name that the customer or authorities commonly recognizes.
* API field: `merchantName`
* Field Specification: 

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       10       |     40     | Required | Required |   Required   |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       3        |     24     | Required | Required |   Required   |       NA     |

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
### LEGAL_NAME
* Description: <Field description>
* API field: `legalBusinessName`
* Field Specification: Legal or official name of a merchant that is registered with government tax authorities. 
<br>Note: It must be entered exactly same as it appears in the legal tax documents for the merchant.

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       6        |     18     | Required | Required | Not Required |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       1        |     24     | Required | Required | Not Required |       NA     |

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
### TAX_FILING_NAME
* Description: Name that the merchant uses to file the taxes with the relevant tax authorities. 
* API field: `taxFilingName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       20       |    100     | Required | Required |   Required   |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       10       |     40     | Required | Required |   Required   |       NA     |

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
### BUSINESS_URL
* Description: Official website address (URL) associated with the merchant.
  <br>Note: The URL should be complete and accurate and it should start with the protocol (http:// or https://).
* API field: `websiteUrlText`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       34       |    240     | Required | Required | Not Required |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       34       |    240     | Required | Required | Not Required |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->
---

### BUSINESS_TYP_CODE
* Description: Code that indicates whether merchant can process payment in store or online.
  <br>Note: The following values indicate:
  - MOTO_ECOMM: Online payment method
  - RETAIL: In store payment method
* API field: `motoEcommerceCode`
* Field Specification: 

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   |   Minimum Length   | Max Length | Inquiry  |  Create  |  Update  |    Delete    |
|--------|:------------------:|:----------:|:--------:|:--------:|:--------:|:------------:|
| String |          6         |     10     | Required | Required | Required |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       1        |     1      | Required | Required |   Required   |       NA     |


 Values**:
|    Value     |     Description       |
|--------------|:---------------------:|
| MOTO_ECOMM   |   <description>       |
|  RETAIL      |   <description>       |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->

---
### MERCHANT_CATEGORY_CODE
* Description: Code that indicates the type of business.
* API field: `primaryMccCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       4        |     4      | Required | Required |    Required  |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       4        |     4      | Required | Required |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->
---
### STANDARD_INDUSTRY_CLASS_CODE
* Description: Code that indicates the classification of MC/VISA standard industry.
<br>Note: The code list is available upon request only.
* API field: `sicCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       4        |     4      | Required | Required |   Required   |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       4        |     4      | Required | Required |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->
---
### STATUS_CODE 
* Description: Code that indicates the status of a merchant.
  <br>Example:
  - PENDING : Pending Credit Approval
  - CANCELLED_FRAUD : Cancelled Due to Fraud
  - ACTIVE : Active - Monthly Stmt
  - CANCELLED_CREDIT : Cancelled By Credit
  - CANCELLED_MERCHANT : Cancelled By Merchant
* API field: `statusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       6        |     18     | Required | Required  |   Required   |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       1        |     2     | Required | Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      | Required | Required |   Required   |       NA     |

<!-- type: tab-end -->
---
### ACCT_OPEN_DATE
* Description: Date on which the merchant account was opened.
  <br>Format: CCYY-MM-DD
  <br>Example: 2024-05-15
  <br>Note: It can include a time component if required. 
* API field: `openDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |      Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     10     | Required | Not Required |    Required  |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |      Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     10     | Required | Not Required |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### ACCT_SUBMIT_DATE
* Description: Date on which the account was submitted.
* API field: `acctSubmitDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        -       |      -     | Required | Not Required | Not Required |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        -       |      -     | Required | Not Required | Not Required |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### LAST_STATUS_CHANGED_DATE
* Description: Date on which the last status of the merchant account was changed.
* API field: `lastStatusChangedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      | Required | Not Required | Not Required |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      | Required |    Required  |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### LAST_STATUS_CODE
* Description: Code to indicate the last status of the merchant account before a recent update.
* API field: `previousStatusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       6        |     18     | Required |    Required  |    Required  |       NA     |

  <!--   type: tab -->
----
##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     2      | Required |    Required  |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### ACCT_CLOSE_DATE
* Description: Date on which the account was closed.
* API field: `acctCloseDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     10     | Required | Not Required |   Required   |       NA     |

  <!--   type: tab -->
----
##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     10     | Required | Not Required |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### CLOSE_REASON_CODE
* Description: Code that indicates the reason of merchant account closure.
* API field: `closeReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     30     | Required |    Required  |    Required  |       NA     |

  <!--   type: tab -->
----
##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     3      | Required |    Required  |    Required  |       NA     |

**Valid Values**: 
|              Value                     |                    Description                 |
|----------------------------------------|:----------------------------------------------:|
|CD_OUT_BS_AC_INACT_O                    | CD-OUT BS-AC INACT-O|
|LP_HI_RISK_CLS_BANK                     | LP Hi Rsk cls at bnk|
|CUST_SERVICE                            | CUSTOMER SERVICE|
|DATA_CLEANUP                            | DATA CLEAN UP|
|CHANGE_LEGAL_ENTITY_OR_OWNER            | CHG LEGL ENTITY/OWNR|
|PCI_DSS_NON_COMPLIANT                   | PCI DSS NON-COMPLIAN|
|CD_IN_BS_AC_INACT_O                     | CD-IN BS-AC INACT-O|
|CD_IN_BS_NEW_OWNERSHIP                  | CD-IN BS-NEW OWNRSHP|
|LP_HI_RISK_CASH_ADV                     | LP-HI RSK-CASH ADV|
|LP_HI_RISK_ID_THEFT                     | LP-HI RISK-I.D.THEFT|
|LP_HI_RISK_AGENT_MISRPR                 | LP-HI RSK-AGT MISRPR|
|CLOSED_COLL_NO_REOPEN                   | Clsd Coll No Reopen|
|CD_IN_BS_COLLECT_PR                     | CD IN BS Collect PR|
|CD_AG_SVC_SEASONAL_LOW                  | CD-AG SVC-SEASNL/LOW|
|CD_IN_BS_RFS_TO_PY_C                    | CD-IN BS-RFS TO PY C|
|CD_IN_BS_NO_PY_OF_R                     | CD IN BS No Py of R|
|CEASED_TRADING                          | CEASED TRADING|
|CD_IN_BS_IN_LITIGATION                  | CD-IN BS-IN LTIGTION|
|CD_IN_BS_XCS_STATEMENT_FEE              | CD-IN BS-XCS STMT FE|
|CD_OUT_BS_CHECKING_ACCT                 | CD-OUT BS-CHKNG ACCT|
|CD_IN_BS_CHECKING                       | CD IN BS Checking                    |
|CD_OUT_BS_CANT_CONTACT                  | CD-OUT BS-CANT CNTCT|
|CD_OUT_BUSINESS_CLOSE                   | CD-OUT BUS-BSNS CLOS|
|CD_HI_RISK_BANKRUPTCY                   | CD-HI RISK-BNKRUPTCY|
|MAPPED_AS_OPEN                          | Mapped over as open|
|SHOULB_BE_CLOSED                        | Should have been closed|
|SALES_REP_PROBLEM                       | Problem with sales rep|
|PER_MERCHANT_LETTER                     | Per merchant letter|
|PARTNERSHIP_SPLIT                       | Partnership split|
|NO_ACTIVITY_ON_ACCT                     | No activity on account|
|NEVER_WANTED_ACCT                       | Never wanted account|
|USE_DIFF_PROCESSOR                      | Use different processor|
|NO_REASON                               | No reason given|
|SERVICE_PROB_INV_REF                    | Service problem (Inv/Ref)|
|NOT_ACCEPT_MCVI                         | No longer acceptes MC/VI|
|MIGRATED_AGENT_BANK                     | Migrated with agent bank|
|MIGRATED_OVER_6_MON                     | Migrated over 6 months|
|DUPLICATE_ACCT                          | Duplicate Account|
|DISSATISFIED_WITH_FEES                  | Dissatisfied with Fees|
|BUSINESS_CLOSED                         | Business Closed|
|REASON_UNKNOWN                          | Reason Unkown|
|NONE                                    | None|
|2009_PRICE_INCREASE                     | Pricing increase 2009|
|TERMINAL_COMPANY_SVC                    | TERMINL COMPNY-SVC|
|REI                                     | REI|
|FRAUD_OR_BAD_DEBIT                      | FRAUD / BAD DEBT|
|DORMANCY                                | DORMANCY|
|COMPETITOR_NEW_PRDCT                    | COMPETITOR/NEW PRDC|
|COMPETITR_PROPSITION                    | COMPETITR/PROPSITION|
|COMPETITOR_SERVICE                      | COMPETITOR / SERVICE|
|COMPETITOR_FEES                         | COMPETITOR / FEES|
|TERMINAL_COMPANY_PRDCT                  | TERMINL COMPNY-PRDCT|
|RATE_INCREASE_20XX                      | Rate increase 20XX|
|OWNERSHIP_CHANGE                        | Change of ownership|
|IR2005_PRICE_INCREASE                   | IR 2005 Pricing increase|
|TEST_ACCT                               | Test Account|
|SYS_RECORD                              | System Record|
|SOLD_BUSINESS                           | Sold business|
|SERVICE_PROB_TER_SYS                    | Service problem (Ter/Sys)|
|SERVICE_PROB_STM_FUN                    | Service problem(Stm/Fun)|
|RA_DBA_TEMP_CLOSED                      | RA DBA Temp Closure|
|IR_AGENT_STY_W_CUR_PRC                  | IR AGT Sty W Cur Prc|
|IR_CSI_POOR_SERVICE                     | IR CSI Poor Service|
|IR_CSI_SS_NUM_MISMATCH                  | IR CSI SS Num Mismatch|
|IR_CSI_LOST_OR_STOLEN_TERMINAL          | IR CSI Lost/Stolen Terml|
|IR_CSI_BANKRUPTCY                       | IR CSI Bankruptcy|
|IR_CSI_UBL_TO_CT_MER                    | IR CSI Ubl To Ct Mer|
|IR_AGENT_EQUIPMENT_NT_COMPAT            | IR AGT Eqp Nt Compat|
|IR_SALES_REP_FRAUD                      | IR SALES REP FRAUD|
|END_OF_TERM                             | END OF TERM|
|MEDICAL_RELATED                         | MEDICAL RELATED|
|IR_CSI_CHK_GUAR_DECLINE                 | IR CSI Chk Guar Decline|
|RA_DBA_CONTRACT_VIOLATION               | RA DBA Contrct Viloation|
|DEROGATORY                              | Derogatory|
|DOESNOT_MEET_SETTLEMENT_REQ             | Doesnt meet settl reqmts|
|IR_PND_INFO_SLS_SUPT                    | IR-PND INFO SLS SUPT|
|CLOSED_CREDIT_NO_REOPEN                 | Closed credit no reopen|
|CLOSED_CREDIT_NO_REOPEN                 | CLSD CRED NO REOPEN|
|PAYMENT_NETWORK_UPDATED                 | PAYMENT NETWORK UPD|
|DDA_ACCT_CLOSED                         | DDA Acct Closed|
|DONT_REOPEN_CONVERTED                   | Dont reopen converted|
|IR_AGENT_SVC_LEAS_DESC                  | IR-AGT SVC-LEAS DECL|
|IR_DEATH                                | IR-DEATH|
|IR_IN_BS_R_INC_CS_F                     | IR-IN  BS-R INC CS F|
|IR_AGENT_SVC_NON_INSTL                  | IR-AGT SVC-NON-INSTL|
|IR_IN_BS_RT_INC_LOW                     | IR-IN  BS-RT INC LOW|
|IR_AVG_SV_REFUS_INST                    | IR-AGT SV-REFUS INST|
|IR_SEASONAL_MERCHANT                    | IR- SEASONAL MERCHNT|
|IR_IN_BS_SLD_BS_NEW                     | IR-IN  BS-SLD BS/NEW|
|IR_AGENT_SVC_MISREP_FEE                 | IR AGT Svc Misrep Fee|
|IR_AGENT_SVC_MISREP_APP                 | IR AGT Svc Misrep App|
|LP_HI_RISK_CNTRFT_PN                    | LP-HI RSK-CNTRFT PN|
|IR_IN_BS_FRN_CHSE_DI                    | IR-IN BS-FRN CHSE DI|
|IR_IN_BS_FEES_NT_CMP                    | IR-IN BS-FEES NT CMP|
|IR_CSI_SVC_EQUIPMENT_TEC                | IR-CSI SVC-EQPMT/TEC|
|IR_CSI_SVC_DSC_RM_RP                    | IR CSI Svc Dsc Rm Rp|
|IR_CSI_SVC_DSC_LP_RP                    | IR CSI Svc Dsc Lp Rp|
|IR_AGENT_SVC_TMP_CLOSR                  | IR-AGT SVC-TMP CLOSR|
|IR_AGENT_CONVERSATION_DAILY             | IR AGT Conversion Daily|
|IR_AGENT_INSTALL_DAILY                  | IR AGT Install Daily|
|LP_HI_RISK_CLOSED_PR_WA                 | LP-HI RSK-CLSD PR WA|
|LP_HI_RISK_MC_8_PCT_VIOLATION           | LP-HI RSK-M/C 8% VIO|
|LP_HI_RISK_INACURATE_ME2                | LP-HI RSK-INACRTE ME|
|LP_HI_RISK_PENDING_INVESTMENT           | LP-HI RSK-PND INVST|
|LP_HI_RISK_SECURITY_RISK                | LP Hi Rsk secty rsk|
|LP_HI_RISK_STL_CD_FRAUD                 | LP-HI RSK-STL CD FRD|
|LP_HI_RISK_TMF_MATCH                    | LP-HI RSK-TMF MATCH|
|LP_HI_RISK_EXCESS_CHARGEBACK            | LP-HI RSK-XCES CHGBK|
|LP_HI_RISK_INACURATE_ME3                | LP-HI RSK-INACRTE ME|
|LP_SALES_REP_FRAUD                      | LP SALES REP FRAUD|
|LP_HI_RISK_NO_ACTIVITY                  | LP-HI RSK-NO ACTVTY|
|LP_HI_RISK_MER_INTRNE                   | LP-HI RSK-MER INTRNE|
|LP_HI_RISK_INACURATE_ME1                | LP-HI RSK-INACRTE ME|
|LP_HI_RISK_FACTOR_PEND                  | LP-HI RSK-FACTR PEND|
|LP_HI_RISK_CONTRACT_VIOLATION           | LP-HI RK-CNTRCT VIOL|
|IR_CSI_SVC_DSC_CS_RP                    | IR CSI Svc Dsc Cs Rp|
|IR_CSI_SVC_DSC_CD_RP                    | IR CSI Svc Dsc Cd Rp|
|IR_AGENT_SERVICE_DEFAULTED_ON           | IR-AGT SVC-DFLTED ON|
|IR_OUT_BUSINESS_CLOSE                   | IR-OUT BUS-BSNS CLOS|
|IR_AGT_SERVICE_AGENT_FRAUD              | IR-AGT SVC-AGENT FRD|

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### FRANCHISE_INDICATOR
* Description: Value that indicates the merchat is a franchise or not.
* API field: `franchiseIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   |   Minimum Length   | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:------------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |         3          |     3      | Required | Required | Not Required |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     1      | Required |    Required  | Not Required |       NA     |

**Valid Values**: 
|          Value             |                    Description                 |
|----------------------------|:----------------------------------------------:|
|            YES             |  Merchant is a franchise.                      |
|            NO              |  Merchant is not a franchise.                  |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### SEASONAL_INDICATOR
* Description: Value that indicates the merchat is a seasonal or not.
* API field: `seasonalIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |    Required  | Not Required |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     1      | Required |    Required  | Not Required |       NA     |

**Valid Values**: 
|          Value             |                    Description                 |
|----------------------------|:----------------------------------------------:|
|            YES             |  <i>description to some here</i>               |
|            NO              |  <i>description to some here</i>               |


<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### SALESMAN_CODE
* Description: Code that indicates the salesman associated with a merchant.
<br>Note: The code list is available upon request only.
* API field: `salesmanCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |     7      | Required |    Required  |    Required  |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |     4      | Required |    Required  |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### RELATIONSHIP_MGR_CODE
* Description: Code that indicates a relationship manager who is responsible for managing the merchant's account.
* API field: `relationshipMgrCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   |   Minimum Length   | Max Length | Inquiry  |  Create  |  Update  |    Delete    |
|--------|:------------------:|:----------:|:--------:|:--------:|:--------:|:------------:|
| String |          3         |     3      |          |          |          |       NA     |

 <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |    Required  |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### RELATIONSHIP_MGR_CODE
* Description: Code that indicates a relationship manager who is responsible for managing the merchant's account.
* API field: `relationshipManagerCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |   Required   |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |   Required   |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### MARKER_BANK_CODE
* Description: Code that indicates the bank associated with a maker or client.
* API field: `markerBankCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     10     | Required |   Required   |    Required  |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3     | Required |   Required   |    Required  |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### CLEARING_BANK_CODE
* Description: Code that indicates the clearing bank associated with a merchant. 
<br>Note: The valid list is available on request only.
* API field: `clearingBankCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     1      | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |    Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### BUSINESS_START_DATE
* Description: Date on which the business was started.
* API field: `businessStartDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |      -     | Required | Not Required | Not Required |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      | Required |    Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### PRICING_TYPE_CODE
* Description: Code that indicates the pricing type for interchange calculations.
* API field: `pricingTypeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       30       |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |      3     | Required |    Required  |   Required   |       NA     |

**Valid Values**:
|    Value                     |     Description       |
|------------------------------|:----------------------:|
| DC_COURT_FINE_GOVT_SERVICE   |   <description>       |
|        CHARITY               |   <description>       |

DC_COURT_FINE_GOVT_SERVICE, CHARITY, RG_EMERGING_MARKET, RG_SMT, RETAIL_OR_SMT, RECR_BILL_PAY, RG_DC_RETAIL_OR_SMT, DC_SUPERMARKET, RG_DC_CONV_STORE, MOTO_NO_AVS, HC_MOTO, DC_RETAIL_OR_SMT, EPS_QPS_NO_AUTH, BAR_CATERER_RETAIL, DC_EMERGIN_MKT, HC_MOTO, HOTEL, RETAIL_KEY_ENTRY1, T&E_MOTO, DC_HOTEL, RG_MOTO_NON_AVS, RG_DC_CAR, PR_EMERGING_MKT, DC_INS, EDUCATIONAL_MOTO, PR_T&E_CP, EDU_RETAIL, DC_RESTAURANT, DC_EMERGING_MARKET_GOVT_EDU, RG_CONV_STORE, RG_CAR, PR_PETRO_AFD, RG_DC_EMERGING_MARKET, T&E_MOTO, DC_RETAIL, DC_ECOMM_PREF, RG_DC_SERVICE_STATIONS, B2B_PUR_CARD_LEVEL3, ECOMM_BASIC, EDU_MOTO, DC_SERVICE_STATION, T&E_RETAIL, PR_T&E_CNP, COMM_B2B_TAX_EXMP, PR_MOTO, INSURANCE, GU_RETAIL, RG_REATIL_OR_SMT, RG_DC_SMT, GU_ECOMM, DC_FILL_UCAF, RG_DC_COURT_FINE_GOVT_SERV, COMM_RETAL_TAX_EXMP, RETAIL, HC_MOTO, RG_RETAIL, RG_DC_HOTEL, FUEL_DISP, RG_AUTOMATED_FUEL_DISP, MERIT_1_DAYCARE, RG_DC_QSR_THTR_TAXI_LIMO, AUTOMATED_FULEL_DISP, HC_RETAIL, EDUCATIONAL_MOTO, FULL_UCAF, RG_REST_OR_FAST_FOOD, SMALL_TICKET, SUPERMARKET, T&E_RETAIL, DC_AOTOMATED_FUEL_DISP, BAR_CATERER_MOTO, RG_DC_AUTO_FUEL_DISP, EMERGING_MARKET, RETAIL_KEY_ENTRY2, RH_COMM_RETAIL_TAX_EXMP, T&E_MOTO, RG_DC_MOTO, COMM_CNP_TAX_EXMP, RG_INS, RG_DC_PUBLIC_SECTOR, T&E_RETAIL, GU_MOTO, RG_COMM_B2B_TAX_EXMP, EDUCATIONAL_RETAIL, DC_UTILITY, DC_RETAIL_2, RG_ECOMM_BASIC, RG_DC_ECOMM_BASIC, UTILITY, T&E_RETAIL, EDUCATIONAL_RETAIL, RG_DC_RETAIL_2, RETAIL_2, HC_RETAIL, RG_DC_FULL_UCAF, VI_RETAIL, QSR_THEATER_TAXI_LIMO, RG_B2B_PRCH_CARD, RG_DC_ACCT_FUNDING, EMERGING_MKT_GOVT_EDU, EDUCATION_MOTO, RG_MOTO, RG_CHARITY, HOTEL_CARRENTAL, SERVICE_STATION, DC_CAR, HC_RETAIL, CAR_RENTAL_CNP, RG_COMM_CNP_TAX_EXMP, VI_ECOMM, RG_ACCT_FUNDING, DC_ECOMM_BASIC, DEC_RETAIL_KE, RG_ECOMM_PREF, RG_DC_MOTO_NON_AVS, RG_DC_INS, HC_RETAIL, RG_SERVICE_STATIONS, PR_SUPERMARKET, CASH_ADV, RG_B2B_PRCH_CARD_LEVEL3, RG_DC_RETAIL, DC_MOTO, DC_SMT, B2B_PURC_CARD, RG_DC_SUPERMARKET, DC_CHARITY, DC_PUBLIC_SECTOR, RG_PAPER, DEFAULT, RG_UTILITY, RG_QSR_THTR_TAXI_LIMO, DC_ACCT_FUNDING, QSR_THEATER_SMT, RECR_BILL_PAY, RG_DC_RETAIL_OR_SMT, RG_HOTEL, RG_RETAIL_KEY_ENTRY, RG_COURT_FINE_GOVT_SERV, INTERNET, DC_MOTO_NON_AVS, RG_CASH_ADV, RG_PUBLIC_SECTOR, PAPER, DC_CONV_STORES, PR_PETRO_SVC_STATION, DC_QSR_THTR_TAXI_LIMO, EDUCATIONAL_RETAIL, RG_RETAIL_2, RESTAURANT, RG_DC_ECOMM_PREF, RG_FULL_UCAF, RG_SUPERMARKET, ECOMM_PREF, PR_RETAIL, HC_MOTO, CAR, T&E_MOTO, RG_DC_REST_OR_FAST_FOOD, RG_DC_UTILITY, COURT_FINES_GOVT_SERV, ACCT_FUNDING, PUBLIC_SECTOR, VI_MOTO, MOTO, RG_DC_RETAIL_KEY_ENTRY, CONV_STORES
<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### INTL_TAX_EXEMPT_INDICATOR
* Description: Value that indicates the international tax exempt is applicable to North MSIP. 
* API field: `internationalTaxExemptIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        2       |     3     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        1       |     1     | Required |    Required  |   Required   |       NA     |

**Valid Values**:
|    Value                     |     Description       |
|------------------------------|:----------------------:|
|             YES              |   <description>       |
|             NO               |   <description>       |
<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### ANNUAL_CARD_AMOUNT
* Description: Amount of the annual card in decimal format.
* API field: `annualCardAmount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      | Required | Not Required | Not Required |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      | Required | Not Required | Not Required |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### LANGUAGE_CODE
* Description: Code that indicates the language for communication with the merchant.
* API field: `languageCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     10     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       0        |      0     | Required |    Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
### TAX_ID_TYPE_CODE
* Description: Code that indicates the type of tax identifier.
* API field: `taxIdTypeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |      7     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |      1     | Required |    Required  |   Required   |       NA     |

**Valid Values**:
|    Value                     |     Description       |
|------------------------------|:----------------------:|
|             EIN              |   <description>       |
|           REFUSED            |   <description>       |
|             SSN              |   <description>       |
|            OTHER             |   <description>       |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### TAX_ID
* Description: Unique identifier of the merchat tax.
* API field: `taxId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       20       |     50     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        9       |     20     | Required |    Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### MULTI_CURRENCY_INDICATOR
* Description: Value that indicates whether a merchant conducts currency conversion at the point of sale.
* API field: `multiCurrencyIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     18     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     1      | Required |    Required  |   Required   |       NA     |

**Valid Values**:
|    Value                     |     Description       |
|------------------------------|:----------------------:|
|           CURR_CONV          |   <description>       |
|            DCC_GMA           |   <description>       |
|       FOREIGN_PROCESSING     |   <description>       |
|            INDIA             |   <description>       |
|        GLOBAL_EPRICING       |   <description>       |
|         NO_CURR_CONV         |   <description>       |
|             TAI              |   <description>       |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### SUB_PLATFORM
* Description: Code that indicates the alliance pratform.
* API field: `alliancePlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     22     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     1      | Required |    Required  |   Required   |       NA     |

**Valid Values**:
|            Value                     |     Description       |
|--------------------------------------|:---------------------:|
|           MSIP                       |   <description>       |
|           SUNTRUST_THREE             |   <description>       |
|           NOVUS                      |   <description>       |
|           IPAYMENT                   |   <description>       |
|           FISERV_BAMS                |   <description>       |
|           BANK_OF_HAWAII             |   <description>       |
|           WELLS_WEST                 |   <description>       |
|           SANTANDER                  |   <description>       |
|           SUNTRUST_ONE               |   <description>       |
|           PNC                        |   <description>       |
|           WALMART                    |   <description>       |
|           CORE_BUSINESS_RULES        |   <description>       |
|           FISERV_CHASE               |   <description>       |
|           RSA_PLATFORM_S             |   <description>       |
|           SUNTRUST_TWO               |   <description>       |
|           RSA_PLATFORM_T             |   <description>       |
|           HUNTINGTON                 |   <description>       |
|           WELLS_EAST                 |   <description>       |
|           FISERV_BANK_OF_AMERICA     |   <description>       |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### CORPORATE_NAME
* Description: Official name of the merchant as it appears in legal and corporate documents.
* API field: `corporateName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     24     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     24     | Required |    Required  |   Required   |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->
---
