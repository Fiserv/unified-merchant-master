# Merchant

* **Description**: Stores essential information about merchant -   demographic information,merchant status , business type, and contractual data, ensuring efficient transaction processing and management. Every merchant has an entry in this critical repository.
* **API Schema**: `Merchant`
* **Table Name**: `UMM.MERCHANT`

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

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Required     | Required     | Required |    Required     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     |
| OMNIPAY26     |  Omnipay Backend ( GMA)      |
| SOUTH     |     South  Backend |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum |     NA          |     NA     | Required   | Required   | Required   | Required     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Required     | Required     | Required |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->
---

### EFFECTIVE_START_DATE

* Description:  Date on which record got added.
* API field: `effectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Optional     | NA     | NA |    NA     |

* Effective date is required to perform snapshot query on a specific merchant

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Optional     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Optional     | NA     | NA |    NA     |

<!-- type: tab-end -->
---

### EFFECTIVE_END_DATE

* Description: This date specifies validity of the record.
* API field: effectiveStartDate
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    NA     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    NA     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   Date   |       10       |    10      |    NA    |      NA      |       NA     |       NA   |

<!-- type: tab-end -->
---

### HIERARCHY_LEVEL_CODE

* Description: Unique identifier assigned to an outlet or a specific level within a hierarchical structure of a merchant's business.
* API field: `hierarchyLevelCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | NA |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  AGENT   |   AGENT hierarchy level     |
|  CHAIN   |   CHAIN hierarchy level     |
|  BANK   |    Bank  hierarchy level     |
|  BILL_TO_ADDR   | BILL_TO_ADDR hierarchy level (019)    |
|  CORP   |   Corporation  hierarchy level     |
|  BUSINESS   |  Business hierarchy level       |
|  OUTLET   |   Outlet  hierarchy level     |
| GROUP     |     Highest level in Omnipay Hierarchy   |
| SUB_GROUP |     This represents the next level in Omnipay Hierarchy below Group level   |
| MEMBER    |     This identifies the actual processing Merchant assigned to a location in Omnipay |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |       NA        |    NA      |    Available     | Required     | NA |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  AGENT   |   AGENT hierarchy level (040)     |
|  CHAIN   |   CHAIN hierarchy level (020)    |
|  BANK   |    Bank  hierarchy level  (050)   |
|  BILL_TO_ADDR   | BILL_TO_ADDR hierarchy level (019)    |
|  CORP   |   Corporation  hierarchy level (030)     |
|  BUSINESS   |  Business hierarchy level (060)      |
|  OUTLET   |    Outlet  hierarchy level (010)    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA       |    NA        |    Available     | Required     | NA |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| GROUP     |     Highest level in Omnipay Hierarchy   |
| SUB_GROUP |     This represents the next level in Omnipay Hierarchy below Group level   |
| MEMBER    |     This identifies the actual processing Merchant assigned to a location in Omnipay |

<!-- type: tab-end -->
---

### STORE_ID

* Description: Unique identifier of the merchant's store.
* API field: `storeId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    8        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      1        |   8        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### DBA_NAME

* Description: Official merchant name that the customer or authorities commonly recognizes.
* API field: `dbaName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    24        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    24        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    22        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab-end -->
---

### LEGAL_NAME

* Description: Legal or official name of a merchant that is registered with government tax authorities.
* API field: `legalName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    24        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab-end -->
---

### TAX_FILING_NAME

* Description: Name that the merchant uses to file the taxes with the relevant tax authorities.
* API field: `taxFilingName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    40        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    40        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### BUSINESS_URL

* Description: Official website address (URL) associated with the merchant.
* API field: `businessUrl`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    240        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 34        |    240        |    Available     | Required     | Allowed |    NA     |

* Max 70 chars for North

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10       |    76        |    Available     | Optional     | TBD |    NA      |

<!-- type: tab-end -->
---

### BUSINESS_TYP_CODE

* Description: Code that indicates whether merchant can process payment in store or online.
* API field: `businessTypCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|RETAIL | Merchant supporting sale of products in stores, person-to-person, or through direct mail|
|ECOMM | Merchant supporting sale of products solely through the Internet|
|BOTH | Merchant supporting both retail and ecomm sales|
|MOTO_ECOMM | Merchant cannot process in store payment|
|MOTO | Mail order and Telephone order|
|NONE | None|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |       NA        |    NA       |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| MOTO_ECOMM     |Merchant cannot process in store payment   |
| RETAIL     |Merchant can process in store payment   |
| NONE | None|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|RETAIL | Merchant supporting sale of products in stores, person-to-person, or through direct mail|
|ECOMM | Merchant supporting sale of products solely through the Internet|
|BOTH | Merchant supporting both retail and ecomm sales|

<!-- type: tab-end -->
---

### MERCHANT_CATEGORY_CODE

* Description: Code that indicates the type of business  in which a merchant is engaged.
* API field: `merchantCategoryCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab-end -->
---

### STANDARD_INDUSTRY_CLASS_CODE

* Description: Code that indicates the classification of MC/VISA standard industry.
* API field: `standardIndustryClassCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### STATUS_CODE

* Description: Code that indicates the status of a merchant.
* API field: `statusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| PENDING     |Pending Credit Approval   |
| CANCELLED_FRAUD     |Cancelled Due to Fraud   |
| CANCELLED_CREDIT     |Cancelled By Credit   |
| CANCELLED_MERCHANT     |Cancelled By Merchant   |
| ACTIVE     |Active - Monthly Stmt   |
| ACTIVE_STTLS_WKLY_FRI | Active Weekly Friday |
| ACTIVE_STTLS_LAST_FRI | Active Last Friday |
| ACTIVE_DIRECT_PAYMENT | Active Direct Payment |
| CANCELLED_LTRCLOSMR | CLOSED-LTRCLOSMR |
| CANCELLED_POORSERV | Closed-Poorserv |
| CANCELLED_REASON_UNKNOWN | CLOSED-REASUNKW |
| CANCELLED_DECEASED | Closed (Deceased) |
| CANCELLED_ACNTNEVRQ | CLOSED-ACNTNEVRQ |
| CANCELLED_MRCHCHBS | CLOSED-MRCHCHBS |
| CANCELLED_POSTECISS | Closed-Posteciss |
| ACTIVE_HOLD_PAY | Active (Hold Pay) |
| CANCELLED_PRTNRSPLT | CLOSED-PRTNRSPLT |
| CANCELLED_DUPLICATE_ACCOUNT | CLOSED-DUPLACCNT |
| ACTIVE_BANKRUPT | Active (Bankrupt) |
| CANCELLED_BUSINESS_CLOSED | CLOSED-BSNSCLOSD |
| CANCELLED_ATREQEMS | CLOSED-ATREQEMS  |
| CANCELLED_BANKRUPT | CLOSED-BANKRUPT  |
| CANCELLED_TERMRTND | Closed-Termrtnd |
| CANCELLED_BANKRPT | Closed (Bankrupt) |
| CANCELLED_NO_LONGER_ACC | CLOSED-NOLONGACC |
| DORMANT | Dormant |
| CANCELLED_APPLY_FEE | Closed Apply Fee |
| CANCELLED_NEW_OWN | Closed (New Own) |
| CANCELLED_RISK | Closed-Risk |
| CANCELLED_EMERGENCY | Closed (Emergency) |
| CANCELLED_FRAUD | CLOSED-FRAUD     |
| CANCELLED_PROBWSREP | CLOSED-PROBWSREP |
| CANCELLED_SOLDBUSNS | CLOSED-SOLDBUSNS |
| CANCELLED_DIS_SATISFACTION | CLOSED-DISATFEES |
| CANCELLED_MNGMTREQ | Closed-Mngmtreq |
| CANCELLED | Closed |
| CANCELLED_CHANGE_OWNER | CLOSED-CHNGEOWNR |
| SUSPENDED | Suspended |
| CANCELLED_MERCHANT_NO_REASON | CLOSED-MRCNOREAS |
| CANCELLED_CREDIT | Closed by Credit |
| CANCELLED_BY_MERCHANT | Closed by Merchant |
| CANCELLED_NOACTONAC | CLOSED-NOACTONAC |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |        NA       |   NA       |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| PENDING     |Pending Credit Approval  ( 01)  |
| CANCELLED_FRAUD     |Cancelled Due to Fraud  ( 02)  |
| CANCELLED_CREDIT     |Cancelled By Credit  (03)  |
| CANCELLED_MERCHANT     |Cancelled By Merchant (13)  |
| ACTIVE     | Active with Monthly Stmt (16)   |
| ACTIVE_STTLS_WKLY_FRI | Active Weekly Friday |
| ACTIVE_STTLS_LAST_FRI | Active Last Friday |
| ACTIVE_DIRECT_PAYMENT | Active Direct Payment |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | NA     |   Allowed  |        NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| CANCELLED_LTRCLOSMR | CLOSED-LTRCLOSMR |
| CANCELLED_POORSERV | Closed-Poorserv |
| CANCELLED_REASON_UNKNOWN | CLOSED-REASUNKW |
| CANCELLED_DECEASED | Closed (Deceased) |
| ACTIVE | Active |
| CANCELLED_ACNTNEVRQ | CLOSED-ACNTNEVRQ |
| CANCELLED_MRCHCHBS | CLOSED-MRCHCHBS |
| CANCELLED_POSTECISS | Closed-Posteciss |
| ACTIVE_HOLD_PAY | Active (Hold Pay) |
| CANCELLED_PRTNRSPLT | CLOSED-PRTNRSPLT |
| CANCELLED_DUPLICATE_ACCOUNT | CLOSED-DUPLACCNT |
| ACTIVE_BANKRUPT | Active (Bankrupt) |
| CANCELLED_BUSINESS_CLOSED | CLOSED-BSNSCLOSD |
| CANCELLED_ATREQEMS | CLOSED-ATREQEMS  |
| CANCELLED_BANKRUPT | CLOSED-BANKRUPT  |
| CANCELLED_TERMRTND | Closed-Termrtnd |
| CANCELLED_BANKRPT | Closed (Bankrupt) |
| CANCELLED_NO_LONGER_ACC | CLOSED-NOLONGACC |
| DORMANT | Dormant |
| CANCELLED_APPLY_FEE | Closed Apply Fee |
| CANCELLED_NEW_OWN | Closed (New Own) |
| CANCELLED_RISK | Closed-Risk |
| CANCELLED_EMERGENCY | Closed (Emergency) |
| CANCELLED_FRAUD | CLOSED-FRAUD     |
| CANCELLED_PROBWSREP | CLOSED-PROBWSREP |
| CANCELLED_SOLDBUSNS | CLOSED-SOLDBUSNS |
| CANCELLED_DIS_SATISFACTION | CLOSED-DISATFEES |
| CANCELLED_MNGMTREQ | Closed-Mngmtreq |
| CANCELLED | Closed |
| CANCELLED_CHANGE_OWNER | CLOSED-CHNGEOWNR |
| SUSPENDED | Suspended |
| CANCELLED_MERCHANT_NO_REASON | CLOSED-MRCNOREAS |
| CANCELLED_CREDIT | Closed by Credit |
| CANCELLED_BY_MERCHANT | Closed by Merchant |
| CANCELLED_NOACTONAC | CLOSED-NOACTONAC |

<!-- type: tab-end -->
---

### PRODUCTS_SOLD

* Description: NA for North ( TBD)
* API field: `productsSold`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| STRING  | 1        |    23        |    Available     | Required     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| STRING  |      NA       |    NA      |    Available     | Required     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ACCT_OPEN_DATE

* Description: Date on which the merchant account was opened.
* API field: `acctOpenDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String | 10        |    10        |    Available     | Required     | NA     |    NA         |

<!-- type: tab-end -->
---

### ACCT_SUBMIT_DATE

* Description: Date on which the account was submitted.
* API field: `acctSubmitDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### LAST_STATUS_CHANGED_DATE

* Description: Date on which the last status of the merchant account was changed.
* API field: `lastStatusChangedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### LAST_STATUS_CODE

* Description: Code to indicate the last status of the merchant account before a recent update.
* API field: `lastStatusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 6        |    18        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      6        |    18        |    Available     | NA     |    NA     |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ACCT_CLOSE_DATE

* Description: Date on which the account was closed.
* API field: `acctCloseDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CLOSE_REASON_CODE

* Description: Code that indicates the reason of merchant account closure.
* API field: `closeReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | NA     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| LP_SALES_REP_FRAUD     |LP SALES REP FRAUD   |
| IR_IN_BS_SLD_BS_NEW     |IR-IN  BS-SLD BS/NEW   |
| IR_PND_INFO_SLS_SUPT     |IR-PND INFO SLS SUPT   |
| LP_HI_RISK_CONTRACT_VIOLATION     |LP-HI RK-CNTRCT VIOL   |
| CD_IN_BS_COLLECT_PR     |CD IN BS Collect PR   |
| IR_SEASONAL_MERCHANT     |IR- SEASONAL MERCHNT   |
| SYS_RECORD     |System Record   |
| PCI_DSS_NON_COMPLIANT     |PCI DSS NON-COMPLIAN   |
| CLOSED_COLL_NO_REOPEN     |Clsd Coll No Reopen   |
| LP_HI_RISK_NO_ACTIVITY     |LP-HI RSK-NO ACTVTY   |
| TEST_ACCT     |Test Account   |
| TERMINAL_COMPANY_SVC     |TERMINL COMPNY-SVC   |
| SERVICE_PROB_STM_FUN     |Service problem(Stm/Fun)   |
| SERVICE_PROB_INV_REF     |Service problem (Inv/Ref)   |
| LP_HI_RISK_MER_INTRNE     |LP-HI RSK-MER INTRNE   |
| CD_OUT_BS_AC_INACT_O     |CD-OUT BS-AC INACT-O   |
| LP_HI_RISK_INACURATE_ME3     |LP-HI RSK-INACRTE ME   |
| LP_HI_RISK_SECURITY_RISK     |LP Hi Rsk secty rsk   |
| IR_CSI_SVC_EQUIPMENT_TEC     |IR-CSI SVC-EQPMT/TEC   |
| IR_CSI_POOR_SERVICE     |IR CSI Poor Service   |
| IR_AGENT_SERVICE_DEFAULTED_ON     |IR-AGT SVC-DFLTED ON   |
| IR_IN_BS_FEES_NT_CMP     |IR-IN BS-FEES NT CMP   |
| DDA_ACCT_CLOSED     |DDA Acct Closed   |
| CLOSED_CREDIT_NO_REOPEN     |Closed credit no reopen   |
| CD_IN_BS_IN_LITIGATION     |CD-IN BS-IN LTIGTION   |
| IR_AGENT_SVC_MISREP_APP     |IR AGT Svc Misrep App   |
| IR_DEATH     |IR-DEATH   |
| LP_HI_RISK_MC_8_PCT_VIOLATION     |LP-HI RSK-M/C 8% VIO   |
| DORMANCY     |DORMANCY   |
| IR2005_PRICE_INCREASE     |IR 2005 Pricing increase   |
| CD_AG_SVC_SEASONAL_LOW     |CD-AG SVC-SEASNL/LOW   |
| DATA_CLEANUP     |DATA CLEAN UP   |
| IR_CSI_LOST_OR_STOLEN_TERMINAL     |IR CSI Lost/Stolen Terml   |
| LP_HI_RISK_TMF_MATCH     |LP-HI RSK-TMF MATCH   |
| IR_OUT_BUSINESS_CLOSE     |IR-OUT BUS-BSNS CLOS   |
| DISSATISFIED_WITH_FEES     |Dissatisfied with Fees   |
| DONT_REOPEN_CONVERTED     |Dont reopen converted   |
| CD_IN_BS_RFS_TO_PY_C     |CD-IN BS-RFS TO PY C   |
| TERMINAL_COMPANY_PRDCT     |TERMINL COMPNY-PRDCT   |
| END_OF_TERM     |END OF TERM   |
| IR_AGENT_SVC_NON_INSTL     |IR-AGT SVC-NON-INSTL   |
| CD_IN_BS_CHECKING     |CD IN BS Checking    |
| REI     |REI   |
| MAPPED_AS_OPEN     |Mapped over as open   |
| CD_IN_BS_XCS_STATEMENT_FEE     |CD-IN BS-XCS STMT FE   |
| MIGRATED_AGENT_BANK     |Migrated with agent bank   |
| IR_AGT_SERVICE_AGENT_FRAUD     |IR-AGT SVC-AGENT FRD   |
| LP_HI_RISK_EXCESS_CHARGEBACK     |LP-HI RSK-XCES CHGBK   |
| IR_AGENT_SVC_MISREP_FEE     |IR AGT Svc Misrep Fee   |
| 2009_PRICE_INCREASE     |Pricing increase 2009   |
| CD_OUT_BS_CHECKING_ACCT     |CD-OUT BS-CHKNG ACCT   |
| IR_CSI_SS_NUM_MISMATCH     |IR CSI SS Num Mismatch   |
| NOT_ACCEPT_MCVI     |No longer acceptes MC/VI   |
| LP_HI_RISK_AGENT_MISRPR     |LP-HI RSK-AGT MISRPR   |
| FRAUD_OR_BAD_DEBIT     |FRAUD / BAD DEBT   |
| LP_HI_RISK_ID_THEFT     |LP-HI RISK-I.D.THEFT   |
| LP_HI_RISK_CLOSED_PR_WA     |LP-HI RSK-CLSD PR WA   |
| LP_HI_RISK_CASH_ADV     |LP-HI RSK-CASH ADV   |
| LP_HI_RISK_STL_CD_FRAUD     |LP-HI RSK-STL CD FRD   |
| DOESNOT_MEET_SETTLEMENT_REQ     |Doesnt meet settl reqmts   |
| PARTNERSHIP_SPLIT     |Partnership split   |
| RATE_INCREASE_20XX     |Rate increase 20XX   |
| IR_AGENT_INSTALL_DAILY     |IR AGT Install Daily   |
| IR_AGENT_STY_W_CUR_PRC     |IR AGT Sty W Cur Prc   |
| IR_AGENT_SVC_TMP_CLOSR     |IR-AGT SVC-TMP CLOSR   |
| IR_IN_BS_FRN_CHSE_DI     |IR-IN BS-FRN CHSE DI   |
| IR_SALES_REP_FRAUD     |IR SALES REP FRAUD   |
| IR_IN_BS_R_INC_CS_F     |IR-IN  BS-R INC CS F   |
| MEDICAL_RELATED     |MEDICAL RELATED   |
| NEVER_WANTED_ACCT     |Never wanted account   |
| PER_MERCHANT_LETTER     |Per merchant letter   |
| SERVICE_PROB_TER_SYS     |Service problem (Ter/Sys)   |
| LP_HI_RISK_FACTOR_PEND     |LP-HI RSK-FACTR PEND   |
| OWNERSHIP_CHANGE     |Change of ownership   |
| NO_REASON     |No reason given   |
| DUPLICATE_ACCT     |Duplicate Account   |
| LP_HI_RISK_CLS_BANK     |LP Hi Rsk cls at bnk   |
| USE_DIFF_PROCESSOR     |Use different processor   |
| CD_HI_RISK_BANKRUPTCY     |CD-HI RISK-BNKRUPTCY   |
| CUST_SERVICE     |CUSTOMER SERVICE   |
| PAYMENT_NETWORK_UPDATED     |PAYMENT NETWORK UPD   |
| CEASED_TRADING     |CEASED TRADING   |
| COMPETITR_PROPSITION     |COMPETITR/PROPSITION   |
| SOLD_BUSINESS     |Sold business   |
| CD_OUT_BUSINESS_CLOSE     |CD-OUT BUS-BSNS CLOS   |
| IR_AGENT_SVC_LEAS_DESC     |IR-AGT SVC-LEAS DECL   |
| SALES_REP_PROBLEM     |Problem with sales rep   |
| NONE     |None   |
| LP_HI_RISK_PENDING_INVESTMENT     |LP-HI RSK-PND INVST   |
| BUSINESS_CLOSED     |Business Closed   |
| IR_IN_BS_RT_INC_LOW     |IR-IN  BS-RT INC LOW   |
| CLOSED_CREDIT_NO_REOPEN     |Closed credit no reopen   |
| IR_AVG_SV_REFUS_INST     |IR-AGT SV-REFUS INST   |
| COMPETITOR_SERVICE     |COMPETITOR / SERVICE   |
| COMPETITOR_FEES     |COMPETITOR / FEES   |
| NO_ACTIVITY_ON_ACCT     |No activity on account   |
| CD_IN_BS_AC_INACT_O     |CD-IN BS-AC INACT-O   |
| IR_CSI_UBL_TO_CT_MER     |IR CSI Ubl To Ct Mer   |
| CHANGE_LEGAL_ENTITY_OR_OWNER     |CHG LEGL ENTITY/OWNR   |
| LP_HI_RISK_CNTRFT_PN     |LP-HI RSK-CNTRFT PN   |
| IR_AGENT_CONVERSATION_DAILY     |IR AGT Conversion Daily   |
| RA_DBA_CONTRACT_VIOLATION     |RA DBA Contrct Viloation   |
| IR_AGENT_EQUIPMENT_NT_COMPAT     |IR AGT Eqp Nt Compat   |
| IR_CSI_BANKRUPTCY     |IR CSI Bankruptcy   |
| CD_OUT_BS_CANT_CONTACT     |CD-OUT BS-CANT CNTCT   |
| DEROGATORY     |Derogatory   |
| CD_IN_BS_NEW_OWNERSHIP     |CD-IN BS-NEW OWNRSHP   |
| RA_DBA_TEMP_CLOSED     |RA DBA Temp Closure   |
| COMPETITOR_NEW_PRDCT     |COMPETITOR/NEW PRDC   |
| CD_IN_BS_NO_PY_OF_R     |CD IN BS No Py of R   |
| REASON_UNKNOWN     |Reason Unkown   |
| LP_HI_RISK_INACURATE_ME1     |LP-HI RSK-INACRTE ME   |
| SHOULB_BE_CLOSED     |Should have been closed   |
|  LP_HI_RISK_OUT_OF_BUS|  LP_HI_RISK_OUT_OF_BUS  |
|LP_HI_RISK_EXCESS_RTV_RQ|LP_HI_RISK_EXCESS_RTV_RQ|
|IR_CONSD_OF_MER_OUTL|IR_CONSD_OF_MER_OUTL|
|EQPMNT_CONVERSION|EQPMNT_CONVERSION|
|IR_NO_LNGR_TK_CR_CAR|IR_NO_LNGR_TK_CR_CAR|
|IR_ACCNT_OPND_IN_ERR|IR_ACCNT_OPND_IN_ERR|
|IR_NOT_ENGH_CR_CD_VO|IR_NOT_ENGH_CR_CD_VO|
|CHANGE_IN_TERMS_CIT|CHANGE_IN_TERMS_CIT|
|RTML_UNABLE_CONTACT|RTML_UNABLE_CONTACT|
|QTR_CANCELLATION|QTR_CANCELLATION|
|BLANK|BLANK|
|QTR_ CANCELLATION|QTR_ CANCELLATION|
|611_FOR_FUTURE_USE|611_FOR_FUTURE_USE|
|612_FOR_FUTURE_USE|612_FOR_FUTURE_USE|
|613_FOR_FUTURE_USE|613_FOR_FUTURE_USE|
|614_FOR_FUTURE_USE|614_FOR_FUTURE_USE|
|615_FOR_FUTURE_USE|615_FOR_FUTURE_USE|
|616_FOR_FUTURE_USE|616_FOR_FUTURE_USE|
|617_FOR_FUTURE_USE|617_FOR_FUTURE_USE|
|618_FOR_FUTURE_USE|618_FOR_FUTURE_USE|
|619_FOR_FUTURE_USE|619_FOR_FUTURE_USE|
|620_FOR_FUTURE_USE|620_FOR_FUTURE_USE|
|621_FOR_FUTURE_USE|621_FOR_FUTURE_USE|
|622_FOR_FUTURE_USE|622_FOR_FUTURE_USE|
|623_FOR_FUTURE_USE|623_FOR_FUTURE_USE|
|624_FOR_FUTURE_USE|624_FOR_FUTURE_USE|
|625_FOR_FUTURE_USE|625_FOR_FUTURE_USE|
|626_FOR_FUTURE_USE|626_FOR_FUTURE_USE|
|627_FOR_FUTURE_USE|627_FOR_FUTURE_USE|
|628_FOR_FUTURE_USE|628_FOR_FUTURE_USE|
|629_FOR_FUTURE_USE|629_FOR_FUTURE_USE|
|630_FOR_FUTURE_USE|630_FOR_FUTURE_USE|
|631_FOR_FUTURE_USE|631_FOR_FUTURE_USE|
|632_FOR_FUTURE_USE|632_FOR_FUTURE_USE|
|633_FOR_FUTURE_USE|633_FOR_FUTURE_USE|
|634_FOR_FUTURE_USE|634_FOR_FUTURE_USE|
|635_FOR_FUTURE_USE|635_FOR_FUTURE_USE|
|636_FOR_FUTURE_USE|636_FOR_FUTURE_USE|
|637_FOR_FUTURE_USE|637_FOR_FUTURE_USE|
|638_FOR_FUTURE_USE|638_FOR_FUTURE_USE|
|639_FOR_FUTURE_USE|639_FOR_FUTURE_USE|
|640_FOR_FUTURE_USE|640_FOR_FUTURE_USE|
|641_FOR_FUTURE_USE|641_FOR_FUTURE_USE|
|642_FOR_FUTURE_USE|642_FOR_FUTURE_USE|
|643_FOR_FUTURE_USE|643_FOR_FUTURE_USE|
|644_FOR_FUTURE_USE|644_FOR_FUTURE_USE|
|645_FOR_FUTURE_USE|645_FOR_FUTURE_USE|
|646_FOR_FUTURE_USE|646_FOR_FUTURE_USE|
|647_FOR_FUTURE_USE|647_FOR_FUTURE_USE|
|648_FOR_FUTURE_USE|648_FOR_FUTURE_USE|
|649_FOR_FUTURE_USE|649_FOR_FUTURE_USE|
|650_FOR_FUTURE_USE|650_FOR_FUTURE_USE|
|651_FOR_FUTURE_USE|651_FOR_FUTURE_USE|
|652_FOR_FUTURE_USE|652_FOR_FUTURE_USE|
|653_FOR_FUTURE_USE|653_FOR_FUTURE_USE|
|654_FOR_FUTURE_USE|654_FOR_FUTURE_USE|
|655_FOR_FUTURE_USE|655_FOR_FUTURE_USE|
|656_FOR_FUTURE_USE|656_FOR_FUTURE_USE|
|657_FOR_FUTURE_USE|657_FOR_FUTURE_USE|
|658_FOR_FUTURE_USE|658_FOR_FUTURE_USE|
|659_FOR_FUTURE_USE|659_FOR_FUTURE_USE|
|660_FOR_FUTURE_USE|660_FOR_FUTURE_USE|
|661_FOR_FUTURE_USE|661_FOR_FUTURE_USE|
|662_FOR_FUTURE_USE|662_FOR_FUTURE_USE|
|663_FOR_FUTURE_USE|663_FOR_FUTURE_USE|
|664_FOR_FUTURE_USE|664_FOR_FUTURE_USE|
|665_FOR_FUTURE_USE|665_FOR_FUTURE_USE|
|666_FOR_FUTURE_USE|666_FOR_FUTURE_USE|
|667_FOR_FUTURE_USE|667_FOR_FUTURE_USE|
|668_FOR_FUTURE_USE|668_FOR_FUTURE_USE|
|669_FOR_FUTURE_USE|669_FOR_FUTURE_USE|
|670_FOR_FUTURE_USE|670_FOR_FUTURE_USE|
|671_FOR_FUTURE_USE|671_FOR_FUTURE_USE|
|672_FOR_FUTURE_USE|672_FOR_FUTURE_USE|
|673_FOR_FUTURE_USE|673_FOR_FUTURE_USE|
|674_FOR_FUTURE_USE|674_FOR_FUTURE_USE|
|675_FOR_FUTURE_USE|675_FOR_FUTURE_USE|
|676_FOR_FUTURE_USE|676_FOR_FUTURE_USE|
|677_FOR_FUTURE_USE|677_FOR_FUTURE_USE|
|678_FOR_FUTURE_USE|678_FOR_FUTURE_USE|
|679_FOR_FUTURE_USE|679_FOR_FUTURE_USE|
|680_FOR_FUTURE_USE|680_FOR_FUTURE_USE|
|681_FOR_FUTURE_USE|681_FOR_FUTURE_USE|
|682_FOR_FUTURE_USE|682_FOR_FUTURE_USE|
|683_FOR_FUTURE_USE|683_FOR_FUTURE_USE|
|684_FOR_FUTURE_USE|684_FOR_FUTURE_USE|
|685_FOR_FUTURE_USE|685_FOR_FUTURE_USE|
|686_FOR_FUTURE_USE|686_FOR_FUTURE_USE|
|687_FOR_FUTURE_USE|687_FOR_FUTURE_USE|
|688_FOR_FUTURE_USE|688_FOR_FUTURE_USE|
|689_FOR_FUTURE_USE|689_FOR_FUTURE_USE|
|690_FOR_FUTURE_USE|690_FOR_FUTURE_USE|
|691_FOR_FUTURE_USE|691_FOR_FUTURE_USE|
|692_FOR_FUTURE_USE|692_FOR_FUTURE_USE|
|693_FOR_FUTURE_USE|693_FOR_FUTURE_USE|
|694_FOR_FUTURE_USE|694_FOR_FUTURE_USE|
|695_FOR_FUTURE_USE|695_FOR_FUTURE_USE|
|696_FOR_FUTURE_USE|696_FOR_FUTURE_USE|
|697_FOR_FUTURE_USE|697_FOR_FUTURE_USE|
|698_FOR_FUTURE_USE|698_FOR_FUTURE_USE|
|699_FOR_FUTURE_USE|699_FOR_FUTURE_USE|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | NA     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| LP_SALES_REP_FRAUD     |LP SALES REP FRAUD   |
| IR_IN_BS_SLD_BS_NEW     |IR-IN  BS-SLD BS/NEW   |
| IR_PND_INFO_SLS_SUPT     |IR-PND INFO SLS SUPT   |
| LP_HI_RISK_CONTRACT_VIOLATION     |LP-HI RK-CNTRCT VIOL   |
| CD_IN_BS_COLLECT_PR     |CD IN BS Collect PR   |
| IR_SEASONAL_MERCHANT     |IR- SEASONAL MERCHNT   |
| SYS_RECORD     |System Record   |
| PCI_DSS_NON_COMPLIANT     |PCI DSS NON-COMPLIAN   |
| CLOSED_COLL_NO_REOPEN     |Clsd Coll No Reopen   |
| LP_HI_RISK_NO_ACTIVITY     |LP-HI RSK-NO ACTVTY   |
| TEST_ACCT     |Test Account   |
| TERMINAL_COMPANY_SVC     |TERMINL COMPNY-SVC   |
| SERVICE_PROB_STM_FUN     |Service problem(Stm/Fun)   |
| SERVICE_PROB_INV_REF     |Service problem (Inv/Ref)   |
| LP_HI_RISK_MER_INTRNE     |LP-HI RSK-MER INTRNE   |
| CD_OUT_BS_AC_INACT_O     |CD-OUT BS-AC INACT-O   |
| LP_HI_RISK_SECURITY_RISK     |LP Hi Rsk secty rsk   |
| IR_CSI_SVC_EQUIPMENT_TEC     |IR-CSI SVC-EQPMT/TEC   |
| IR_CSI_POOR_SERVICE     |IR CSI Poor Service   |
| IR_AGENT_SERVICE_DEFAULTED_ON     |IR-AGT SVC-DFLTED ON   |
| IR_IN_BS_FEES_NT_CMP     |IR-IN BS-FEES NT CMP   |
| DDA_ACCT_CLOSED     |DDA Acct Closed   |
| CLOSED_CREDIT_NO_REOPEN     |Closed credit no reopen   |
| CD_IN_BS_IN_LITIGATION     |CD-IN BS-IN LTIGTION   |
| IR_AGENT_SVC_MISREP_APP     |IR AGT Svc Misrep App   |
| IR_DEATH     |IR-DEATH   |
| LP_HI_RISK_MC_8_PCT_VIOLATION     |LP-HI RSK-M/C 8% VIO   |
| DORMANCY     |DORMANCY   |
| IR2005_PRICE_INCREASE     |IR 2005 Pricing increase   |
| CD_AG_SVC_SEASONAL_LOW     |CD-AG SVC-SEASNL/LOW   |
| DATA_CLEANUP     |DATA CLEAN UP   |
| IR_CSI_LOST_OR_STOLEN_TERMINAL     |IR CSI Lost/Stolen Terml   |
| LP_HI_RISK_TMF_MATCH     |LP-HI RSK-TMF MATCH   |
| IR_OUT_BUSINESS_CLOSE     |IR-OUT BUS-BSNS CLOS   |
| DISSATISFIED_WITH_FEES     |Dissatisfied with Fees   |
| DONT_REOPEN_CONVERTED     |Dont reopen converted   |
| CD_IN_BS_RFS_TO_PY_C     |CD-IN BS-RFS TO PY C   |
| TERMINAL_COMPANY_PRDCT     |TERMINL COMPNY-PRDCT   |
| END_OF_TERM     |END OF TERM   |
| IR_AGENT_SVC_NON_INSTL     |IR-AGT SVC-NON-INSTL   |
| CD_IN_BS_CHECKING     |CD IN BS Checking    |
| REI     |REI   |
| MAPPED_AS_OPEN     |Mapped over as open   |
| CD_IN_BS_XCS_STATEMENT_FEE     |CD-IN BS-XCS STMT FE   |
| MIGRATED_AGENT_BANK     |Migrated with agent bank   |
| IR_AGT_SERVICE_AGENT_FRAUD     |IR-AGT SVC-AGENT FRD   |
| LP_HI_RISK_EXCESS_CHARGEBACK     |LP-HI RSK-XCES CHGBK   |
| IR_AGENT_SVC_MISREP_FEE     |IR AGT Svc Misrep Fee   |
| 2009_PRICE_INCREASE     |Pricing increase 2009   |
| CD_OUT_BS_CHECKING_ACCT     |CD-OUT BS-CHKNG ACCT   |
| IR_CSI_SS_NUM_MISMATCH     |IR CSI SS Num Mismatch   |
| NOT_ACCEPT_MCVI     |No longer acceptes MC/VI   |
| LP_HI_RISK_AGENT_MISRPR     |LP-HI RSK-AGT MISRPR   |
| FRAUD_OR_BAD_DEBIT     |FRAUD / BAD DEBT   |
| LP_HI_RISK_ID_THEFT     |LP-HI RISK-I.D.THEFT   |
| LP_HI_RISK_CLOSED_PR_WA     |LP-HI RSK-CLSD PR WA   |
| LP_HI_RISK_CASH_ADV     |LP-HI RSK-CASH ADV   |
| LP_HI_RISK_STL_CD_FRAUD     |LP-HI RSK-STL CD FRD   |
| DOESNOT_MEET_SETTLEMENT_REQ     |Doesnt meet settl reqmts   |
| PARTNERSHIP_SPLIT     |Partnership split   |
| RATE_INCREASE_20XX     |Rate increase 20XX   |
| IR_AGENT_INSTALL_DAILY     |IR AGT Install Daily   |
| IR_AGENT_STY_W_CUR_PRC     |IR AGT Sty W Cur Prc   |
| IR_AGENT_SVC_TMP_CLOSR     |IR-AGT SVC-TMP CLOSR   |
| IR_IN_BS_FRN_CHSE_DI     |IR-IN BS-FRN CHSE DI   |
| IR_SALES_REP_FRAUD     |IR SALES REP FRAUD   |
| IR_IN_BS_R_INC_CS_F     |IR-IN  BS-R INC CS F   |
| MEDICAL_RELATED     |MEDICAL RELATED   |
| NEVER_WANTED_ACCT     |Never wanted account   |
| PER_MERCHANT_LETTER     |Per merchant letter   |
| SERVICE_PROB_TER_SYS     |Service problem (Ter/Sys)   |
| LP_HI_RISK_FACTOR_PEND     |LP-HI RSK-FACTR PEND   |
| OWNERSHIP_CHANGE     |Change of ownership   |
| LP_HI_RISK_INACURATE_ME2     |LP-HI RSK-INACRTE ME   |
| NO_REASON     |No reason given   |
| DUPLICATE_ACCT     |Duplicate Account   |
| LP_HI_RISK_CLS_BANK     |LP Hi Rsk cls at bnk   |
| USE_DIFF_PROCESSOR     |Use different processor   |
| CD_HI_RISK_BANKRUPTCY     |CD-HI RISK-BNKRUPTCY   |
| CUST_SERVICE     |CUSTOMER SERVICE   |
| PAYMENT_NETWORK_UPDATED     |PAYMENT NETWORK UPD   |
| CEASED_TRADING     |CEASED TRADING   |
| COMPETITR_PROPSITION     |COMPETITR/PROPSITION   |
| SOLD_BUSINESS     |Sold business   |
| CD_OUT_BUSINESS_CLOSE     |CD-OUT BUS-BSNS CLOS   |
| IR_AGENT_SVC_LEAS_DESC     |IR-AGT SVC-LEAS DECL   |
| SALES_REP_PROBLEM     |Problem with sales rep   |
| NONE     |None   |
| LP_HI_RISK_PENDING_INVESTMENT     |LP-HI RSK-PND INVST   |
| BUSINESS_CLOSED     |Business Closed   |
| IR_IN_BS_RT_INC_LOW     |IR-IN  BS-RT INC LOW   |
| CLOSED_CREDIT_NO_REOPEN     |Closed credit no reopen   |
| IR_AVG_SV_REFUS_INST     |IR-AGT SV-REFUS INST   |
| COMPETITOR_SERVICE     |COMPETITOR / SERVICE   |
| COMPETITOR_FEES     |COMPETITOR / FEES   |
| NO_ACTIVITY_ON_ACCT     |No activity on account   |
| CD_IN_BS_AC_INACT_O     |CD-IN BS-AC INACT-O   |
| IR_CSI_UBL_TO_CT_MER     |IR CSI Ubl To Ct Mer   |
| CHANGE_LEGAL_ENTITY_OR_OWNER     |CHG LEGL ENTITY/OWNR   |
| LP_HI_RISK_CNTRFT_PN     |LP-HI RSK-CNTRFT PN   |
| IR_AGENT_CONVERSATION_DAILY     |IR AGT Conversion Daily   |
| RA_DBA_CONTRACT_VIOLATION     |RA DBA Contrct Viloation   |
| IR_AGENT_EQUIPMENT_NT_COMPAT     |IR AGT Eqp Nt Compat   |
| IR_CSI_BANKRUPTCY     |IR CSI Bankruptcy   |
| CD_OUT_BS_CANT_CONTACT     |CD-OUT BS-CANT CNTCT   |
| DEROGATORY     |Derogatory   |
| CD_IN_BS_NEW_OWNERSHIP     |CD-IN BS-NEW OWNRSHP   |
| RA_DBA_TEMP_CLOSED     |RA DBA Temp Closure   |
| COMPETITOR_NEW_PRDCT     |COMPETITOR/NEW PRDC   |
| CD_IN_BS_NO_PY_OF_R     |CD IN BS No Py of R   |
| REASON_UNKNOWN     |Reason Unkown   |
| LP_HI_RISK_INACURATE_ME1     |LP-HI RSK-INACRTE ME   |
| SHOULB_BE_CLOSED     |Should have been closed   |
|  LP_HI_RISK_OUT_OF_BUS|  LP_HI_RISK_OUT_OF_BUS  |
|LP_HI_RISK_EXCESS_RTV_RQ|LP_HI_RISK_EXCESS_RTV_RQ|
|IR_CONSD_OF_MER_OUTL|IR_CONSD_OF_MER_OUTL|
|EQPMNT_CONVERSION|EQPMNT_CONVERSION|
|IR_NO_LNGR_TK_CR_CAR|IR_NO_LNGR_TK_CR_CAR|
|IR_ACCNT_OPND_IN_ERR|IR_ACCNT_OPND_IN_ERR|
|IR_NOT_ENGH_CR_CD_VO|IR_NOT_ENGH_CR_CD_VO|
|CHANGE_IN_TERMS_CIT|CHANGE_IN_TERMS_CIT|
|RTML_UNABLE_CONTACT|RTML_UNABLE_CONTACT|
|QTR_CANCELLATION|QTR_CANCELLATION|
|BLANK|BLANK|
|QTR_ CANCELLATION|QTR_ CANCELLATION|
|611_FOR_FUTURE_USE|611_FOR_FUTURE_USE|
|612_FOR_FUTURE_USE|612_FOR_FUTURE_USE|
|613_FOR_FUTURE_USE|613_FOR_FUTURE_USE|
|614_FOR_FUTURE_USE|614_FOR_FUTURE_USE|
|615_FOR_FUTURE_USE|615_FOR_FUTURE_USE|
|616_FOR_FUTURE_USE|616_FOR_FUTURE_USE|
|617_FOR_FUTURE_USE|617_FOR_FUTURE_USE|
|618_FOR_FUTURE_USE|618_FOR_FUTURE_USE|
|619_FOR_FUTURE_USE|619_FOR_FUTURE_USE|
|620_FOR_FUTURE_USE|620_FOR_FUTURE_USE|
|621_FOR_FUTURE_USE|621_FOR_FUTURE_USE|
|622_FOR_FUTURE_USE|622_FOR_FUTURE_USE|
|623_FOR_FUTURE_USE|623_FOR_FUTURE_USE|
|624_FOR_FUTURE_USE|624_FOR_FUTURE_USE|
|625_FOR_FUTURE_USE|625_FOR_FUTURE_USE|
|626_FOR_FUTURE_USE|626_FOR_FUTURE_USE|
|627_FOR_FUTURE_USE|627_FOR_FUTURE_USE|
|628_FOR_FUTURE_USE|628_FOR_FUTURE_USE|
|629_FOR_FUTURE_USE|629_FOR_FUTURE_USE|
|630_FOR_FUTURE_USE|630_FOR_FUTURE_USE|
|631_FOR_FUTURE_USE|631_FOR_FUTURE_USE|
|632_FOR_FUTURE_USE|632_FOR_FUTURE_USE|
|633_FOR_FUTURE_USE|633_FOR_FUTURE_USE|
|634_FOR_FUTURE_USE|634_FOR_FUTURE_USE|
|635_FOR_FUTURE_USE|635_FOR_FUTURE_USE|
|636_FOR_FUTURE_USE|636_FOR_FUTURE_USE|
|637_FOR_FUTURE_USE|637_FOR_FUTURE_USE|
|638_FOR_FUTURE_USE|638_FOR_FUTURE_USE|
|639_FOR_FUTURE_USE|639_FOR_FUTURE_USE|
|640_FOR_FUTURE_USE|640_FOR_FUTURE_USE|
|641_FOR_FUTURE_USE|641_FOR_FUTURE_USE|
|642_FOR_FUTURE_USE|642_FOR_FUTURE_USE|
|643_FOR_FUTURE_USE|643_FOR_FUTURE_USE|
|644_FOR_FUTURE_USE|644_FOR_FUTURE_USE|
|645_FOR_FUTURE_USE|645_FOR_FUTURE_USE|
|646_FOR_FUTURE_USE|646_FOR_FUTURE_USE|
|647_FOR_FUTURE_USE|647_FOR_FUTURE_USE|
|648_FOR_FUTURE_USE|648_FOR_FUTURE_USE|
|649_FOR_FUTURE_USE|649_FOR_FUTURE_USE|
|650_FOR_FUTURE_USE|650_FOR_FUTURE_USE|
|651_FOR_FUTURE_USE|651_FOR_FUTURE_USE|
|652_FOR_FUTURE_USE|652_FOR_FUTURE_USE|
|653_FOR_FUTURE_USE|653_FOR_FUTURE_USE|
|654_FOR_FUTURE_USE|654_FOR_FUTURE_USE|
|655_FOR_FUTURE_USE|655_FOR_FUTURE_USE|
|656_FOR_FUTURE_USE|656_FOR_FUTURE_USE|
|657_FOR_FUTURE_USE|657_FOR_FUTURE_USE|
|658_FOR_FUTURE_USE|658_FOR_FUTURE_USE|
|659_FOR_FUTURE_USE|659_FOR_FUTURE_USE|
|660_FOR_FUTURE_USE|660_FOR_FUTURE_USE|
|661_FOR_FUTURE_USE|661_FOR_FUTURE_USE|
|662_FOR_FUTURE_USE|662_FOR_FUTURE_USE|
|663_FOR_FUTURE_USE|663_FOR_FUTURE_USE|
|664_FOR_FUTURE_USE|664_FOR_FUTURE_USE|
|665_FOR_FUTURE_USE|665_FOR_FUTURE_USE|
|666_FOR_FUTURE_USE|666_FOR_FUTURE_USE|
|667_FOR_FUTURE_USE|667_FOR_FUTURE_USE|
|668_FOR_FUTURE_USE|668_FOR_FUTURE_USE|
|669_FOR_FUTURE_USE|669_FOR_FUTURE_USE|
|670_FOR_FUTURE_USE|670_FOR_FUTURE_USE|
|671_FOR_FUTURE_USE|671_FOR_FUTURE_USE|
|672_FOR_FUTURE_USE|672_FOR_FUTURE_USE|
|673_FOR_FUTURE_USE|673_FOR_FUTURE_USE|
|674_FOR_FUTURE_USE|674_FOR_FUTURE_USE|
|675_FOR_FUTURE_USE|675_FOR_FUTURE_USE|
|676_FOR_FUTURE_USE|676_FOR_FUTURE_USE|
|677_FOR_FUTURE_USE|677_FOR_FUTURE_USE|
|678_FOR_FUTURE_USE|678_FOR_FUTURE_USE|
|679_FOR_FUTURE_USE|679_FOR_FUTURE_USE|
|680_FOR_FUTURE_USE|680_FOR_FUTURE_USE|
|681_FOR_FUTURE_USE|681_FOR_FUTURE_USE|
|682_FOR_FUTURE_USE|682_FOR_FUTURE_USE|
|683_FOR_FUTURE_USE|683_FOR_FUTURE_USE|
|684_FOR_FUTURE_USE|684_FOR_FUTURE_USE|
|685_FOR_FUTURE_USE|685_FOR_FUTURE_USE|
|686_FOR_FUTURE_USE|686_FOR_FUTURE_USE|
|687_FOR_FUTURE_USE|687_FOR_FUTURE_USE|
|688_FOR_FUTURE_USE|688_FOR_FUTURE_USE|
|689_FOR_FUTURE_USE|689_FOR_FUTURE_USE|
|690_FOR_FUTURE_USE|690_FOR_FUTURE_USE|
|691_FOR_FUTURE_USE|691_FOR_FUTURE_USE|
|692_FOR_FUTURE_USE|692_FOR_FUTURE_USE|
|693_FOR_FUTURE_USE|693_FOR_FUTURE_USE|
|694_FOR_FUTURE_USE|694_FOR_FUTURE_USE|
|695_FOR_FUTURE_USE|695_FOR_FUTURE_USE|
|696_FOR_FUTURE_USE|696_FOR_FUTURE_USE|
|697_FOR_FUTURE_USE|697_FOR_FUTURE_USE|
|698_FOR_FUTURE_USE|698_FOR_FUTURE_USE|
|699_FOR_FUTURE_USE|699_FOR_FUTURE_USE|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### FRANCHISE_INDICATOR

* Description: Value that indicates the merchat is a franchise or not.
* API field: `franchiseIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| FRANCHISE     |Franchise   |
| NON_FRANCHISE     |Non Franchise   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |        NA       |    NA      |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| FRANCHISE     |Franchise   |
| NON_FRANCHISE     |Non Franchise   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### SEASONAL_INDICATOR

* Description: Value that indicates the merchat is a seasonal or not.
* API field: `seasonalIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA         |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| Yes     |  Seasonal Merchant   |
| No      |  Non Seasonal Merchant   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | Required     | Allowed |    NA         |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| Yes     |Seasonal Merchant    |
| No      |Non Seasonal Merchant |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | NA |    NA        |

<!-- type: tab-end -->
---

### SALESMAN_CODE

* Description: Code that indicates the salesman associated with a merchant.
* API field: `salesmanCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    8        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |    4        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Available     | Required     | Allowed |    NA         |

<!-- type: tab-end -->
---

### RELATIONSHIP_MGR_CODE

* Description: Code that indicates a relationship manager who is responsible for managing the merchant's account.
* API field: `relationshipMgrCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Required     | Allowed  |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      3        |    3        |    Available     | Required     | Allowed |    NA     |

* It will be 3 byte long

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MARKER_BANK_CODE

* Description: Code that indicates the bank associated with a maker or client.
* API field: `markerBankCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Required     | Allowed  |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      3        |    3       |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CLEARING_BANK_CODE

* Description: Code that indicates the clearing bank associated with a merchant.
* API field: `clearingBankCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|FDMS_HONG_KONG | Clearing Entity for FDMS Hong Kong|
|SOLE_PROP_FIRST_NAME | Clearing Entity for Sole Proprietor First Name|
|POST_BANK | Clearing Entity for Post Bank|
|PAY_WAVE | Clearing Entity for Pay Wave|
|FDRA | Clearing Entity for FDRA|
|FDMS_SINGAPORE | Clearing Entity for FDMS Singapore|
|UC | Clearing Entity for UC|
|WEST_PAC | Clearing Entity for West Pacific|
|FDLC | Clearing Entity for FDLC|
|FDEL | Clearing Entity for FDEL|
|WELLS_FARGO | Clearing Entity for Wells Fargo|
|GMA_INST | Clearing Entity for GMA (Institution)|

* Available values are only applicable for GMA. It can only take 3 bytes for North platform.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       3        |    3       |    Available     | Required     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | Required     |    NA   |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|FDMS_HONG_KONG | Clearing Entity for FDMS Hong Kong|
|SOLE_PROP_FIRST_NAME | Clearing Entity for Sole Proprietor First Name|
|POST_BANK | Clearing Entity for Post Bank|
|PAY_WAVE | Clearing Entity for Pay Wave|
|FDRA | Clearing Entity for FDRA|
|FDMS_SINGAPORE | Clearing Entity for FDMS Singapore|
|UC | Clearing Entity for UC|
|WEST_PAC | Clearing Entity for West Pacific|
|FDLC | Clearing Entity for FDLC|
|FDEL | Clearing Entity for FDEL|
|WELLS_FARGO | Clearing Entity for Wells Fargo|
|GMA_INST | Clearing Entity for GMA (Institution)|

<!-- type: tab-end -->
---

### BUSINESS_START_DATE

* Description: Date on which the business was started.
* API field: `businessStartDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date   |      10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### PRICING_TYPE_CODE

* Description: Code that indicates the pricing type for interchange calculations.
* API field: `pricingTypeCode`
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
| DC_COURT_FINE_GOVT_SERVICE     |DC Court/Fine/Govser   |
| CHARITY     |Charity   |
| RG_EMERGING_MARKET     |RG Emerging Market   |
| RG_SMT     |RG Small Ticket   |
| RETAIL_OR_SMT     |Retail/Small Ticket   |
| RECR_BILL_PAY     |Recurring Bill Pay   |
| RG_DC_RETAIL_OR_SMT     |RG DC Retail/Small Ticket   |
| DC_SUPERMARKET     |DC Supermarket   |
| RG_DC_CONV_STORE     |RG DC Convenience Store   |
| MOTO_NO_AVS     |MO/TO (No AVS)   |
| HC_MOTO     |Healthcare MOTO   |
| DC_RETAIL_OR_SMT     |DC Retail/Small Ticket   |
| EPS_QPS_NO_AUTH     |EPS/QPS (No Auth)   |
| BAR_CATERER_RETAIL     |Bar/Caterer Retail   |
| DC_EMERGIN_MKT     |DC Emerging Market   |
| HC_MOTO     |Healthcare MOTO   |
| HOTEL     |Hotel   |
| RETAIL_KEY_ENTRY1     |Retail (Key Entry)   |
| T&E_MOTO     |T&E MOTO#1   |
| DC_HOTEL     |DC Hotel   |
| RG_MOTO_NON_AVS     |RG MOTO (No AVS)   |
| RG_DC_CAR     |RG DC Car   |
| PR_EMERGING_MKT     |PR Emerging Market   |
| DC_INS     |DC Insurance   |
| EDUCATIONAL_MOTO     |Education MOTO   |
| PR_T&E_CP     |PR T&E Card Present   |
| EDU_RETAIL     |Education Retail   |
| DC_RESTAURANT     |DC Restaurant/Fast Food   |
| DC_EMERGING_MARKET_GOVT_EDU     |DC Emrg Mkt Gov/EDU   |
| RG_CONV_STORE     |RG Convenience Store   |
| RG_CAR     |RG Car   |
| PR_PETRO_AFD     |PR Petroleum AFD   |
| RG_DC_EMERGING_MARKET     |RG DC Emerging Market   |
| T&E_MOTO     |T&E MOTO#1   |
| DC_RETAIL     |DC Retail   |
| DC_ECOMM_PREF     |DC Elec Comm Pref   |
| RG_DC_SERVICE_STATIONS     |RG DC Service Stations   |
| B2B_PUR_CARD_LEVEL3     |B2B Purchase Card LVL3   |
| ECOMM_BASIC     |Elec Commerce Basic   |
| EDU_MOTO     |Education MOTO   |
| DC_SERVICE_STATION     |DC Service Stations   |
| T&E_RETAIL     |T&E Retail#2   |
| PR_T&E_CNP     |PR T&E Card Not Present   |
| COMM_B2B_TAX_EXMP     |Comm B2B Tax Exempt   |
| PR_MOTO     |PR MO/TO   |
| INSURANCE     |Insurance   |
| GU_RETAIL     |GU Retail   |
| RG_REATIL_OR_SMT     |RG Retail/Small Ticket   |
| RG_DC_SMT     |RG DC Small Ticket   |
| GU_ECOMM     |GU Ecommerce   |
| DC_FILL_UCAF     |DC Full UCAF   |
| RG_DC_COURT_FINE_GOVT_SERV     |RG DC Court/Fine/Govser   |
| COMM_RETAL_TAX_EXMP     |Comm RTL Tax Exempt   |
| RETAIL     |Merchant supporting sale of products in stores, person-to-person, or through direct mail   |
| HC_MOTO     |Healthcare MOTO   |
| RG_RETAIL     |RG Retail   |
| RG_DC_HOTEL     |RG DC Hotel   |
| FUEL_DISP     |Fuel Dispenser   |
| RG_AUTOMATED_FUEL_DISP     |RG Automated Fuel Disp   |
| MERIT_1_DAYCARE     |Merit 1 Daycare   |
| RG_DC_QSR_THTR_TAXI_LIMO     |RG DC QSR/Thtr/Taxi/Limo   |
| AUTOMATED_FULEL_DISP     |Automated Fuel Dispenser   |
| HC_RETAIL     |Healthcare Retail   |
| EDUCATIONAL_MOTO     |Education MOTO   |
| FULL_UCAF     |Full UCAF   |
| RG_REST_OR_FAST_FOOD     |RG Restaurant/Fast Food   |
| SMALL_TICKET     |Small Ticket   |
| SUPERMARKET     |Supermarket   |
| T&E_RETAIL     |T&E Retail#2   |
| DC_AOTOMATED_FUEL_DISP     |DC Automated Fuel Disp   |
| BAR_CATERER_MOTO     |Bar/Caterer MOTO   |
| RG_DC_AUTO_FUEL_DISP     |RG DC Auto Fuel Disp   |
| EMERGING_MARKET     |Emerging Market   |
| RETAIL_KEY_ENTRY2     |Retail (Key Entry)   |
| RH_COMM_RETAIL_TAX_EXMP     |RG Comm RTL Tax Exempt   |
| T&E_MOTO     |T&E MOTO#1   |
| RG_DC_MOTO     |RG DC MOTO   |
| COMM_CNP_TAX_EXMP     |Comm CNP Tax Exempt   |
| RG_INS     |RG Insurance   |
| RG_DC_PUBLIC_SECTOR     |RG DC Public Sector   |
| T&E_RETAIL     |T&E Retail#2   |
| GU_MOTO     |GU MO/TO   |
| RG_COMM_B2B_TAX_EXMP     |RG Comm B2B Tax Exempt   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| DC_UTILITY     |DC Utility   |
| DC_RETAIL_2     |DC Retail 2   |
| RG_ECOMM_BASIC     |RG Elec Comm Basic   |
| RG_DC_ECOMM_BASIC     |RG DC Elec Comm Basic   |
| UTILITY     |Utility   |
| T&E_RETAIL     |T&E Retail#2   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| RG_DC_RETAIL_2     |RG DC Retail 2   |
| RETAIL_2     |Retail 2   |
| HC_RETAIL     |Healthcare Retail   |
| RG_DC_FULL_UCAF     |RG DC Full UCAF   |
| VI_RETAIL     |VI Retail   |
| QSR_THEATER_TAXI_LIMO     |QSR/Theater/Taxi/Limo   |
| RG_B2B_PRCH_CARD     |RG B2B Purchase Card   |
| RG_DC_ACCT_FUNDING     |RG DC Acct Funding   |
| EMERGING_MKT_GOVT_EDU     |Emerging Mkt Govt/EDU   |
| EDUCATION_MOTO     |Education MOTO   |
| RG_MOTO     |RG MOTO   |
| RG_CHARITY     |RG Charity   |
| HOTEL_CARRENTAL     |Hotel/Car Rental/Retail   |
| SERVICE_STATION     |Service Stations   |
| DC_CAR     |DC Car   |
| HC_RETAIL     |Healthcare Retail   |
| CAR_RENTAL_CNP     |Car Rent/Card Not Presnt   |
| RG_COMM_CNP_TAX_EXMP     |RG Comm CNP Tax Exempt   |
| VI_ECOMM     |VI Ecommerce   |
| RG_ACCT_FUNDING     |RG Acct Funding   |
| DC_ECOMM_BASIC     |DC Elec Comm Basic   |
| DEC_RETAIL_KE     |DC Retail Key Entry   |
| RG_ECOMM_PREF     |RG Elec Comm Pref   |
| RG_DC_MOTO_NON_AVS     |RG DC MOTO (No AVS)   |
| RG_DC_INS     |RG DC Insurance   |
| HC_RETAIL     |Healthcare Retail   |
| RG_SERVICE_STATIONS     |RG Service Stations   |
| PR_SUPERMARKET     |PR Supermarket   |
| CASH_ADV     |Cash Advance   |
| RG_B2B_PRCH_CARD_LEVEL3     |RG B2B Purch Card LVL3   |
| RG_DC_RETAIL     |RG DC Retail   |
| DC_MOTO     |DC MOTO   |
| DC_SMT     |DC Small Ticket   |
| B2B_PURC_CARD     |B2B Purchase Card   |
| RG_DC_SUPERMARKET     |RG DC Supermarket   |
| DC_CHARITY     |DC Charity   |
| DC_PUBLIC_SECTOR     |DC Public Sector   |
| RG_PAPER     |RG Paper   |
| DEFAULT     |Default   |
| RG_UTILITY     |RG Utility   |
| RG_QSR_THTR_TAXI_LIMO     |RG QSR/Thtr/Taxi/Limo   |
| DC_ACCT_FUNDING     |DC Acct Funding   |
| QSR_THEATER_SMT     |QSR/Theater/Small Ticket   |
| RECR_BILL_PAY     |Recurring Bill Pay   |
| RG_DC_RETAIL_OR_SMT     |RG DC Retail/Small Ticket   |
| RG_HOTEL     |RG Hotel   |
| RG_RETAIL_KEY_ENTRY     |RG Retail Key Entry   |
| RG_COURT_FINE_GOVT_SERV     |RG Court/Fine/Govser   |
| INTERNET     |Internet   |
| DC_MOTO_NON_AVS     |DC MOTO (No AVS)   |
| RG_CASH_ADV     |RG Cash Advance   |
| RG_PUBLIC_SECTOR     |RG Public Sector   |
| PAPER     |Paper   |
| DC_CONV_STORES     |DC Convenience Store   |
| PR_PETRO_SVC_STATION     |PR Petroleum Srv Stn   |
| DC_QSR_THTR_TAXI_LIMO     |DC QSR/Thtr/Taxi/Limo   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| RG_RETAIL_2     |RG Retail 2   |
| RESTAURANT     |Restaurant/Fast Food   |
| RG_DC_ECOMM_PREF     |RG DC Elec Comm Pref   |
| RG_FULL_UCAF     |RG Full UCAF   |
| RG_SUPERMARKET     |RG Supermarket   |
| ECOMM_PREF     |Elec Commerce Pref   |
| PR_RETAIL     |PR Retail   |
| HC_MOTO     |Healthcare MOTO   |
| CAR     |Car   |
| T&E_MOTO     |T&E MOTO#1   |
| RG_DC_REST_OR_FAST_FOOD     |RG DC Restrnt/Fast Food   |
| RG_DC_UTILITY     |RG DC Utility   |
| COURT_FINES_GOVT_SERV     |Court/Fines/Govt Service   |
| ACCT_FUNDING     |Acct Funding   |
| PUBLIC_SECTOR     |Public Sector   |
| VI_MOTO     |VI MO/TO   |
| MOTO     |MAIL ORDER TELEPHONE ORDER   |
| RG_DC_RETAIL_KEY_ENTRY     |RG DC Retail Key Entry   |
| CONV_STORES     |Convenience Stores   |
| RG_DC_CHARITY | RG DC Charity |
| MERIT_DAYCARE_150 | Merit Day care 150 |
| MERIT_DAYCARE_250 | Merit Day care 250 |
| MERIT_DAYCARE_350 | Merit Day care 350 |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String   |     NA       |    NA      |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| DC_COURT_FINE_GOVT_SERVICE     |DC Court/Fine/Govser   |
| CHARITY     |Charity   |
| RG_EMERGING_MARKET     |RG Emerging Market   |
| RG_SMT     |RG Small Ticket   |
| RETAIL_OR_SMT     |Retail/Small Ticket   |
| RECR_BILL_PAY     |Recurring Bill Pay   |
| RG_DC_RETAIL_OR_SMT     |RG DC Retail/Small Ticket   |
| DC_SUPERMARKET     |DC Supermarket   |
| RG_DC_CONV_STORE     |RG DC Convenience Store   |
| MOTO_NO_AVS     |MO/TO (No AVS)   |
| HC_MOTO     |Healthcare MOTO   |
| DC_RETAIL_OR_SMT     |DC Retail/Small Ticket   |
| EPS_QPS_NO_AUTH     |EPS/QPS (No Auth)   |
| BAR_CATERER_RETAIL     |Bar/Caterer Retail   |
| DC_EMERGIN_MKT     |DC Emerging Market   |
| HC_MOTO     |Healthcare MOTO   |
| HOTEL     |Hotel   |
| RETAIL_KEY_ENTRY1     |Retail (Key Entry)   |
| T&E_MOTO     |T&E MOTO#1   |
| DC_HOTEL     |DC Hotel   |
| RG_MOTO_NON_AVS     |RG MOTO (No AVS)   |
| RG_DC_CAR     |RG DC Car   |
| PR_EMERGING_MKT     |PR Emerging Market   |
| DC_INS     |DC Insurance   |
| EDUCATIONAL_MOTO     |Education MOTO   |
| PR_T&E_CP     |PR T&E Card Present   |
| EDU_RETAIL     |Education Retail   |
| DC_RESTAURANT     |DC Restaurant/Fast Food   |
| DC_EMERGING_MARKET_GOVT_EDU     |DC Emrg Mkt Gov/EDU   |
| RG_CONV_STORE     |RG Convenience Store   |
| RG_CAR     |RG Car   |
| PR_PETRO_AFD     |PR Petroleum AFD   |
| RG_DC_EMERGING_MARKET     |RG DC Emerging Market   |
| T&E_MOTO     |T&E MOTO#1   |
| DC_RETAIL     |DC Retail   |
| DC_ECOMM_PREF     |DC Elec Comm Pref   |
| RG_DC_SERVICE_STATIONS     |RG DC Service Stations   |
| B2B_PUR_CARD_LEVEL3     |B2B Purchase Card LVL3   |
| ECOMM_BASIC     |Elec Commerce Basic   |
| EDU_MOTO     |Education MOTO   |
| DC_SERVICE_STATION     |DC Service Stations   |
| T&E_RETAIL     |T&E Retail#2   |
| PR_T&E_CNP     |PR T&E Card Not Present   |
| COMM_B2B_TAX_EXMP     |Comm B2B Tax Exempt   |
| PR_MOTO     |PR MO/TO   |
| INSURANCE     |Insurance   |
| GU_RETAIL     |GU Retail   |
| RG_REATIL_OR_SMT     |RG Retail/Small Ticket   |
| RG_DC_SMT     |RG DC Small Ticket   |
| GU_ECOMM     |GU Ecommerce   |
| DC_FILL_UCAF     |DC Full UCAF   |
| RG_DC_COURT_FINE_GOVT_SERV     |RG DC Court/Fine/Govser   |
| COMM_RETAL_TAX_EXMP     |Comm RTL Tax Exempt   |
| RETAIL     |Merchant supporting sale of products in stores, person-to-person, or through direct mail   |
| HC_MOTO     |Healthcare MOTO   |
| RG_RETAIL     |RG Retail   |
| RG_DC_HOTEL     |RG DC Hotel   |
| FUEL_DISP     |Fuel Dispenser   |
| RG_AUTOMATED_FUEL_DISP     |RG Automated Fuel Disp   |
| MERIT_1_DAYCARE     |Merit 1 Daycare   |
| RG_DC_QSR_THTR_TAXI_LIMO     |RG DC QSR/Thtr/Taxi/Limo   |
| AUTOMATED_FULEL_DISP     |Automated Fuel Dispenser   |
| HC_RETAIL     |Healthcare Retail   |
| EDUCATIONAL_MOTO     |Education MOTO   |
| FULL_UCAF     |Full UCAF   |
| RG_REST_OR_FAST_FOOD     |RG Restaurant/Fast Food   |
| SMALL_TICKET     |Small Ticket   |
| SUPERMARKET     |Supermarket   |
| T&E_RETAIL     |T&E Retail#2   |
| DC_AOTOMATED_FUEL_DISP     |DC Automated Fuel Disp   |
| BAR_CATERER_MOTO     |Bar/Caterer MOTO   |
| RG_DC_AUTO_FUEL_DISP     |RG DC Auto Fuel Disp   |
| EMERGING_MARKET     |Emerging Market   |
| RETAIL_KEY_ENTRY2     |Retail (Key Entry)   |
| RH_COMM_RETAIL_TAX_EXMP     |RG Comm RTL Tax Exempt   |
| T&E_MOTO     |T&E MOTO#1   |
| RG_DC_MOTO     |RG DC MOTO   |
| COMM_CNP_TAX_EXMP     |Comm CNP Tax Exempt   |
| RG_INS     |RG Insurance   |
| RG_DC_PUBLIC_SECTOR     |RG DC Public Sector   |
| T&E_RETAIL     |T&E Retail#2   |
| GU_MOTO     |GU MO/TO   |
| RG_COMM_B2B_TAX_EXMP     |RG Comm B2B Tax Exempt   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| DC_UTILITY     |DC Utility   |
| DC_RETAIL_2     |DC Retail 2   |
| RG_ECOMM_BASIC     |RG Elec Comm Basic   |
| RG_DC_ECOMM_BASIC     |RG DC Elec Comm Basic   |
| UTILITY     |Utility   |
| T&E_RETAIL     |T&E Retail#2   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| RG_DC_RETAIL_2     |RG DC Retail 2   |
| RETAIL_2     |Retail 2   |
| HC_RETAIL     |Healthcare Retail   |
| RG_DC_FULL_UCAF     |RG DC Full UCAF   |
| VI_RETAIL     |VI Retail   |
| QSR_THEATER_TAXI_LIMO     |QSR/Theater/Taxi/Limo   |
| RG_B2B_PRCH_CARD     |RG B2B Purchase Card   |
| RG_DC_ACCT_FUNDING     |RG DC Acct Funding   |
| EMERGING_MKT_GOVT_EDU     |Emerging Mkt Govt/EDU   |
| EDUCATION_MOTO     |Education MOTO   |
| RG_MOTO     |RG MOTO   |
| RG_CHARITY     |RG Charity   |
| HOTEL_CARRENTAL     |Hotel/Car Rental/Retail   |
| SERVICE_STATION     |Service Stations   |
| DC_CAR     |DC Car   |
| HC_RETAIL     |Healthcare Retail   |
| CAR_RENTAL_CNP     |Car Rent/Card Not Presnt   |
| RG_COMM_CNP_TAX_EXMP     |RG Comm CNP Tax Exempt   |
| VI_ECOMM     |VI Ecommerce   |
| RG_ACCT_FUNDING     |RG Acct Funding   |
| DC_ECOMM_BASIC     |DC Elec Comm Basic   |
| DEC_RETAIL_KE     |DC Retail Key Entry   |
| RG_ECOMM_PREF     |RG Elec Comm Pref   |
| RG_DC_MOTO_NON_AVS     |RG DC MOTO (No AVS)   |
| RG_DC_INS     |RG DC Insurance   |
| HC_RETAIL     |Healthcare Retail   |
| RG_SERVICE_STATIONS     |RG Service Stations   |
| PR_SUPERMARKET     |PR Supermarket   |
| CASH_ADV     |Cash Advance   |
| RG_B2B_PRCH_CARD_LEVEL3     |RG B2B Purch Card LVL3   |
| RG_DC_RETAIL     |RG DC Retail   |
| DC_MOTO     |DC MOTO   |
| DC_SMT     |DC Small Ticket   |
| B2B_PURC_CARD     |B2B Purchase Card   |
| RG_DC_SUPERMARKET     |RG DC Supermarket   |
| DC_CHARITY     |DC Charity   |
| DC_PUBLIC_SECTOR     |DC Public Sector   |
| RG_PAPER     |RG Paper   |
| DEFAULT     |Default   |
| RG_UTILITY     |RG Utility   |
| RG_QSR_THTR_TAXI_LIMO     |RG QSR/Thtr/Taxi/Limo   |
| DC_ACCT_FUNDING     |DC Acct Funding   |
| QSR_THEATER_SMT     |QSR/Theater/Small Ticket   |
| RECR_BILL_PAY     |Recurring Bill Pay   |
| RG_DC_RETAIL_OR_SMT     |RG DC Retail/Small Ticket   |
| RG_HOTEL     |RG Hotel   |
| RG_RETAIL_KEY_ENTRY     |RG Retail Key Entry   |
| RG_COURT_FINE_GOVT_SERV     |RG Court/Fine/Govser   |
| INTERNET     |Internet   |
| DC_MOTO_NON_AVS     |DC MOTO (No AVS)   |
| RG_CASH_ADV     |RG Cash Advance   |
| RG_PUBLIC_SECTOR     |RG Public Sector   |
| PAPER     |Paper   |
| DC_CONV_STORES     |DC Convenience Store   |
| PR_PETRO_SVC_STATION     |PR Petroleum Srv Stn   |
| DC_QSR_THTR_TAXI_LIMO     |DC QSR/Thtr/Taxi/Limo   |
| EDUCATIONAL_RETAIL     |Education Retail   |
| RG_RETAIL_2     |RG Retail 2   |
| RESTAURANT     |Restaurant/Fast Food   |
| RG_DC_ECOMM_PREF     |RG DC Elec Comm Pref   |
| RG_FULL_UCAF     |RG Full UCAF   |
| RG_SUPERMARKET     |RG Supermarket   |
| ECOMM_PREF     |Elec Commerce Pref   |
| PR_RETAIL     |PR Retail   |
| HC_MOTO     |Healthcare MOTO   |
| CAR     |Car   |
| T&E_MOTO     |T&E MOTO#1   |
| RG_DC_REST_OR_FAST_FOOD     |RG DC Restrnt/Fast Food   |
| RG_DC_UTILITY     |RG DC Utility   |
| COURT_FINES_GOVT_SERV     |Court/Fines/Govt Service   |
| ACCT_FUNDING     |Acct Funding   |
| PUBLIC_SECTOR     |Public Sector   |
| VI_MOTO     |VI MO/TO   |
| MOTO     |MAIL ORDER TELEPHONE ORDER   |
| RG_DC_RETAIL_KEY_ENTRY     |RG DC Retail Key Entry   |
| CONV_STORES     |Convenience Stores   |
| RG_DC_CHARITY | RG DC Charity |
| MERIT_DAYCARE_150 | Merit Day care 150 |
| MERIT_DAYCARE_250 | Merit Day care 250 |
| MERIT_DAYCARE_350 | Merit Day care 350 |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### INTL_TAX_EXEMPT_INDICATOR

* Description: Value that indicates whether international tax exempt rule is applicable to Merchant ( Only for North).
* API field: `intlTaxExemptIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  | NA        |    NA        |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| YES     |Yes   |
| NO     |No   |
| UNKNOWN | Unknown Value |
| BLANK | Not Specified |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      NA        |    NA       |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| YES     |Yes   |
| NO     |No   |
| UNKNOWN | Unknown Value |
| BLANK | Not Specified |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ANNUAL_CARD_AMOUNT

* Description: NA - as it comes from diligence. (Not part of API)

Amount of the annual card in decimal format.

* API field: `annualCardAmount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   |         |            |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   |         |            |    Available     | NA     | NA |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### LANGUAGE_CODE

* Description: Code that indicates the language for communication with the merchant.
* API field: `languageCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA         |

**Valid Values**:
|              Value   |                    Description                   |
|:----------------------|:------------------------------------------------|
|ARABIC | Arabic|
|ENGLISH | English|
|CZECH | Czech|
|SLOVENIAN | Slovenian|
|FRENCH | French|
|GREEK | Greek|
|DUTCH | Dutch|
|DANISH | Danish|
|RUSSIAN | Russian|
|POLISH | Polish|
|ROMANIAN | Romanian|
|HUNGARIAN | Hungarian|
|ITALIAN | Italian|
|SPANISH | Spanish|
|NORWEGIAN | Norwegian|
|MALTESE | Maltese|
|GERMAN | German|
|SWEDISH | Swedish|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA       |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                   |
|:----------------------|:------------------------------------------------|
|ARABIC | Arabic|
|ENGLISH | English|
|CZECH | Czech|
|SLOVENIAN | Slovenian|
|FRENCH | French|
|GREEK | Greek|
|DUTCH | Dutch|
|DANISH | Danish|
|RUSSIAN | Russian|
|POLISH | Polish|
|ROMANIAN | Romanian|
|HUNGARIAN | Hungarian|
|ITALIAN | Italian|
|SPANISH | Spanish|
|NORWEGIAN | Norwegian|
|MALTESE | Maltese|
|GERMAN | German|
|SWEDISH | Swedish|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|              Value   |                    Description                   |
|:----------------------|:------------------------------------------------|
|ARABIC | Arabic|
|ENGLISH | English|
|CZECH | Czech|
|SLOVENIAN | Slovenian|
|FRENCH | French|
|GREEK | Greek|
|DUTCH | Dutch|
|DANISH | Danish|
|RUSSIAN | Russian|
|POLISH | Polish|
|ROMANIAN | Romanian|
|HUNGARIAN | Hungarian|
|ITALIAN | Italian|
|SPANISH | Spanish|
|NORWEGIAN | Norwegian|
|MALTESE | Maltese|
|GERMAN | German|
|SWEDISH | Swedish|

<!-- type: tab-end -->
---

### TAX_ID_TYPE_CODE

* Description: Code that indicates the type of tax identifier.
* API field: `taxIdTypeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| EIN     |EIN Fed Tax   |
| REFUSED     |Refused   |
| SSN     |SSN   |
| OTHER     |Other Federal Tax ID   |
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA         |    NA     |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| EIN     | EIN Fed Tax   |
| REFUSED     | Refused   |
| SSN     | SSN   |
| OTHER     | Other Federal Tax ID   |
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TAX_ID

* Description: Unique identifier of the merchat tax.
* API field: `taxId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 9        |    20        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      9        |    20        |    Available     | Required     | Allowed |    NA       |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 9        |    15        |    Available     | Optional     | Allowed |    NA        |

* Since this is a PII field, it will encrypted.

<!-- type: tab-end -->
---

### MULTI_CURRENCY_INDICATOR

* Description: Value that indicates whether a merchant conducts currency conversion at the point of sale.
* API field: `multiCurrencyIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| CURR_CONV     |Currency conversion   |
| DCC_GMA     |DCC on GMA   |
| FOREIGN_PROCESSING     |Foreign Processing   |
| INDIA     |India   |
| GLOBAL_EPRICING     |Global ePricing   |
| NO_CURR_CONV     |No currency conversion   |
| TAI     |Tai   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| CURR_CONV     |Currency conversion   |
| DCC_GMA     |DCC on GMA   |
| FOREIGN_PROCESSING     |Foreign Processing   |
| INDIA     |India   |
| GLOBAL_EPRICING     |Global ePricing   |
| NO_CURR_CONV     |No currency conversion   |
| TAI     |Tai   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### SUB_PLATFORM

* Description: Code that indicates the alliance pratform.
* API field: `subPlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| MSIP     |MSIP   |
| SUNTRUST_THREE     |3SunTrust   |
| NOVUS     |Novus   |
| IPAYMENT     |iPayment   |
| FISERV_BAMS     |Fiserv/BAMS   |
| BANK_OF_HAWAII     |Bank of Hawaii   |
| WELLS_WEST     |Wells West   |
| SANTANDER     |Santander   |
| SUNTRUST_ONE     |Sun Trust   |
| PNC     |PNC   |
| WALMART     |Walmart   |
| CORE_BUSINESS_RULES     |Core Business Rules   |
| FISERV_CHASE     |Fiserv/Chase   |
| RSA_PLATFORM_S     |RSA Platform S   |
| SUNTRUST_TWO     |2SunTrust   |
| RSA_PLATFORM_T     |RSA Platform T   |
| HUNTINGTON     |Huntington   |
| WELLS_EAST     |Wells East   |
| FISERV_BANK_OF_AMERICA     |Fiserv/Bank of America   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |      NA        |    NA      |    Available     | Required     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| MSIP     |MSIP (L)  |
| SUNTRUST_THREE     |SunTrust Three ( N)  |
| NOVUS     |Novus (Y)  |
| IPAYMENT     |iPayment  (V) |
| FISERV_BAMS     |Fiserv/BAMS  (C) |
| BANK_OF_HAWAII     |Bank of Hawaii  (J) |
| WELLS_WEST     |Wells West  (W) |
| SANTANDER     |Santander (M)   |
| SUNTRUST_ONE     |Sun Trust One (X) |
| PNC     |PNC (R)  |
| WALMART     |Walmart (D)  |
| CORE_BUSINESS_RULES     |Core Business Rules (K)  |
| FISERV_CHASE     |Fiserv/Chase (Q)  |
| RSA_PLATFORM_S     |RSA Platform (S)   |
| SUNTRUST_TWO     |SunTrust TWo(E)  |
| RSA_PLATFORM_T     |RSA Platform (T)   |
| HUNTINGTON     |Huntington (H)  |
| WELLS_EAST     |Wells East (O)  |
| FISERV_BANK_OF_AMERICA     |Fiserv/Bank of America  (F) |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CORPORATE_NAME

* Description: Official name of the merchant as it appears in legal and corporate documents.
* API field: `corporateName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String | 3             |    24      |    Available     | Required     | Allowed  |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |       3       |    24        |    Available     | Required     | Allowed |    NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
