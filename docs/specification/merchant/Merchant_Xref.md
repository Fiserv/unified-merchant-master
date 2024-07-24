# MERCHANT_XREF
* **Description**: Stores essential information about merchants, including contact details, business type, and contractual data, ensuring efficient transaction processing and management. Every merchant has an entry in this critical repository.
* **API section**: root 
* **Table Name**: MERCHANT_XREF

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

### XREF_PLATFORM_CODE
* Description: Value that indicates the usage of cross reference record associated with the merchant.
* API field: `xrefPlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    16        |    Available     | Required     | Allowed (optional) |    NA |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|  COMPASS     |  Cross eference platform name   |
|  OLD_EXXON_DEALER     |  Cross eference platform name   |
|  OLD_IOL_SITE_ID     |  Cross eference platform name   |
|  BUYPASS     |  Cross eference platform name   |
|  OLD_EXXON_SHIP     |  Cross eference platform name   |
|  LE_PL_CITI_STORE     |  Cross eference platform name   |
|  PROSA     |  Cross eference platform name   |
|  EBT     |  Cross eference platform name   |
|  FDRL     |  Cross eference platform name   |
|  VRU     |  Cross eference platform name   |
|  NABANCO     |  Cross eference platform name   |
|  VPAY     |  Cross eference platform name   |
|  OLD_EXXON_SAP     |  Cross eference platform name   |
|  FDRL_MAESTRO     |  Cross eference platform name   |
|  CITI_TAIWAN     |  Cross eference platform name   |
|  3RD_PARTY     |  Cross eference platform name   |
|  SIGNET     |  Cross eference platform name   |
|  OLD_BUYPASS     |  Cross eference platform name   |
|  JIFFY_LUBE     |  Cross eference platform name   |
|  FDR_AUTH     |  Cross eference platform name   |
|  FDR_FULL_PROCESS     |  Cross eference platform name   |
|  MAPS     |  Cross eference platform name   |
|  MONERIS     |  Cross eference platform name   |
|  CARDNET     |  Cross eference platform name   |
|  HBOS     |  Cross eference platform name   |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed (optional)   | NA |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  COMPASS     |  Cross eference platform name   |
|  OLD_EXXON_DEALER     |  Cross eference platform name   |
|  OLD_IOL_SITE_ID     |  Cross eference platform name   |
|  BUYPASS     |  Cross eference platform name   |
|  OLD_EXXON_SHIP     |  Cross eference platform name   |
|  LE_PL_CITI_STORE     |  Cross eference platform name   |
|  PROSA     |  Cross eference platform name   |
|  EBT     |  Cross eference platform name   |
|  FDRL     |  Cross eference platform name   |
|  VRU     |  Cross eference platform name   |
|  NABANCO     |  Cross eference platform name   |
|  VPAY     |  Cross eference platform name   |
|  OLD_EXXON_SAP     |  Cross eference platform name   |
|  FDRL_MAESTRO     |  Cross eference platform name   |
|  CITI_TAIWAN     |  Cross eference platform name   |
|  3RD_PARTY     |  Cross eference platform name   |
|  SIGNET     |  Cross eference platform name   |
|  OLD_BUYPASS     |  Cross eference platform name   |
|  JIFFY_LUBE     |  Cross eference platform name   |
|  FDR_AUTH     |  Cross eference platform name   |
|  FDR_FULL_PROCESS     |  Cross eference platform name   |
|  MAPS     |  Cross eference platform name   |
|  MONERIS     |  Cross eference platform name   |
|  CARDNET     |  Cross eference platform name   |
|  HBOS     |  Cross eference platform name   |

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

### XREF_PLATFORM_MID
* Description: Unique identifier assigned to an external merchant.
* API field: `xrefPlatformMid`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    20        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |    

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

### PRIMARY_SECURITY_CODE
* Description: Code that indicates the security and can be used to determine the front end network.
* API field: `primarySecurityCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |    

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

### ALLIANCE_PLATFORM_CODE
* Description: Code that indicates the alliance pratform.
* API field: `alliancePlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    22        |    Available     | Required     | Allowed |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|  FISERV_BAMS	|  Fiserv/BAMS     |
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


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|  FISERV_BAMS	|  Fiserv/BAMS     |
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

### XREF_CORRESPONDENCE_INDICATOR
* Description: Value that indicates the merchants and communications uses the associated cross reference number.
* API field: `xrefCorrespondenceIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    3        |    Available     | Required     | Allowed |    NA |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   | 
| YES     |     Yes   | 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   | 
| YES     |     Yes   | 

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
