# MERCHANT_XREF

* **Description**: Stores essential information about  cross reference of other platform for same merchant.
* **API schema**: `merchantXrefs`
* **Table Name**: `MERCHANT_XREF`
* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to uniquely identify a cros reference record for update and delete

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
| String  |      12       |    12      |    Required     | Required     | Required |    Required     |

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
| Enum  | NA        |    NA        |    Required     | Required     | Required |    Required     |

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

### XREF_PLATFORM_CODE

* Description: Value that indicates the usage of cross reference record associated with the merchant.
* API field: `xrefPlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional      | NA |    Allowed       |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|  COMPASS     |  Cross Reference platform    |
|  OLD_EXXON_DEALER     |  Cross Reference platform    |
|  OLD_IOL_SITE_ID     |  Cross Reference platform    |
|  BUYPASS     |  Cross Reference platform    |
|  OLD_EXXON_SHIP     |  Cross Reference platform    |
|  LE_PL_CITI_STORE     |  Cross Reference platform    |
|  PROSA     |  Cross Reference platform    |
|  EBT     |  Cross Reference platform    |
|  FDRL     |  Cross Reference platform    |
|  VRU     |  Cross Reference platform    |
|  NABANCO     |  Cross Reference platform    |
|  VPAY     |  Cross Reference platform    |
|  OLD_EXXON_SAP     |  Cross Reference platform    |
|  FDRL_MAESTRO     |  Cross Reference platform    |
|  CITI_TAIWAN     |  Cross Reference platform    |
|  3RD_PARTY     |  Cross Reference platform    |
|  SIGNET     |  Cross Reference platform    |
|  OLD_BUYPASS     |  Cross Reference platform    |
|  JIFFY_LUBE     |  Cross Reference platform    |
|  FDR_AUTH     |  Cross Reference platform    |
|  FDR_FULL_PROCESS     |  Cross Reference platform    |
|  MAPS     |  Cross Reference platform    |
|  MONERIS     |  Cross Reference platform    |
|  CARDNET     |  Cross Reference platform    |
|  HBOS     |  Cross Reference platform    |
|  NORTH     |  Cross Reference platform    |
|  NOVUS     |  Cross Reference platform    |
|  EXXON     |  Cross Reference platform    |
|  CHASE     |  Cross Reference platform    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional      | NA |    Allowed       |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|  COMPASS     |  Cross Reference platform    |
|  OLD_EXXON_DEALER     |  Cross Reference platform    |
|  OLD_IOL_SITE_ID     |  Cross Reference platform    |
|  BUYPASS     |  Cross Reference platform    |
|  OLD_EXXON_SHIP     |  Cross Reference platform    |
|  LE_PL_CITI_STORE     |  Cross Reference platform    |
|  PROSA     |  Cross Reference platform    |
|  EBT     |  Cross Reference platform    |
|  FDRL     |  Cross Reference platform    |
|  VRU     |  Cross Reference platform    |
|  NABANCO     |  Cross Reference platform    |
|  VPAY     |  Cross Reference platform    |
|  OLD_EXXON_SAP     |  Cross Reference platform    |
|  FDRL_MAESTRO     |  Cross Reference platform    |
|  CITI_TAIWAN     |  Cross Reference platform    |
|  3RD_PARTY     |  Cross Reference platform    |
|  SIGNET     |  Cross Reference platform    |
|  OLD_BUYPASS     |  Cross Reference platform    |
|  JIFFY_LUBE     |  Cross Reference platform    |
|  FDR_AUTH     |  Cross Reference platform    |
|  FDR_FULL_PROCESS     |  Cross Reference platform    |
|  MAPS     |  Cross Reference platform    |
|  MONERIS     |  Cross Reference platform    |
|  CARDNET     |  Cross Reference platform    |
|  HBOS     |  Cross Reference platform    |
|  NOVUS     |  Cross Reference platform    |
|  EXXON     |  Cross Reference platform    |
|  CHASE     |  Cross Reference platform    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional      | NA |    Allowed       |

**Valid Values**:
|         Value        |                    Description                   |
|:----------------------|:------------------------------------------------|
|  NORTH     |  Cross Reference platform    |

<!-- type: tab-end -->
---

### XREF_PLATFORM_MID

* Description: External merchant number corresponding to XREF_PLATFORM_CODE
* API field: `xrefPlatformMid`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    20        |    Available     | Optional     | NA |    Allowed  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      12       |    20      |    Available     | Optional     | NA |    Allowed  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    20        |    Available     | Required     | NA |       NA          |

<!-- type: tab-end -->
---

### PRIMARY_SECURITY_CODE

* Description: Security code  associated with a front end network.
* API field: `primarySecurityCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Optional     | NA |    Allowed |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Optional     | NA |    Allowed |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ALLIANCE_PLATFORM_CODE

* Description: Code that indicates the alliance Platform.
* API field: `alliancePlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional     | Allowed |    Allowed   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|  FISERV_BAMS |  Fiserv/BAMS     |
|  WALMART         |   Walmart     |
|  SUNTRUST_TWO         |   2SunTrust     |
|  FISERV_BANK_OF_AMERICA         |   Fiserv/Bank of America     |
|  HUNTINGTON         |   Huntington     |
|  BANK_OF_HAWAII         |   Bank of Hawaii     |
|  CORE_BUSINESS_RULES         |   Core Business Rules     |
|  MSIP         |   MSIP     |
|  SANTANDER         |   Santander     |
|  SUNTRUST_THREE         |   3SunTrust     |
|  WELLS_EAST         |   Wells East     |
|  FISERV_CHASE         |   Fiserv/Chase     |
|  PNC         |   PNC     |
|  RSA_PLATFORM_S         |   RSA Platform S     |
|  RSA_PLATFORM_T         |   RSA Platform T     |
|  IPAYMENT         |   iPayment     |
|  WELLS_WEST         |   Wells West     |
|  SUNTRUST_ONE         |   Sun Trust     |
|  NOVUS         |   Novus     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        | Available   | Required   | Allowed   | NA |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  FISERV_BAMS |  Fiserv/BAMS     |
|  WALMART         |   Walmart     |
|  SUNTRUST_TWO         |   2SunTrust     |
|  FISERV_BANK_OF_AMERICA         |   Fiserv/Bank of America     |
|  HUNTINGTON         |   Huntington     |
|  BANK_OF_HAWAII         |   Bank of Hawaii     |
|  CORE_BUSINESS_RULES         |   Core Business Rules     |
|  MSIP         |   MSIP     |
|  SANTANDER         |   Santander     |
|  SUNTRUST_THREE         |   3SunTrust     |
|  WELLS_EAST         |   Wells East     |
|  FISERV_CHASE         |   Fiserv/Chase     |
|  PNC         |   PNC     |
|  RSA_PLATFORM_S         |   RSA Platform S     |
|  RSA_PLATFORM_T         |   RSA Platform T     |
|  IPAYMENT         |   iPayment     |
|  WELLS_WEST         |   Wells West     |
|  SUNTRUST_ONE         |   Sun Trust     |
|  NOVUS         |   Novus     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### XREF_CORRESPONDENCE_INDICATOR

* Description: Value that indicates the merchants and communications uses the associated cross reference number.
* API field: `xrefCorrespondenceIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional     | Allowed |    Allowed   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   |
| YES     |     Yes   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional     | Allowed |    Allowed   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   |
| YES     |     Yes   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
