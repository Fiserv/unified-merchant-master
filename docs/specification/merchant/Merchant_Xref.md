# MERCHANT_XREF
* **Description**: Stores essential information about  cross reference of other platform for same merchant.
* **API schema**: `MerchantXref`
* **Table Name**: `MERCHANT_XREF`

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
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
| String |     -    |          |              |       NA     |

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
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
| String |     -    |          |              |       NA     |

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
| String  | 3        |    16        |    Available     | Optional      | NA |    Allowed |

* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to delete a particular cross reference. 

**Valid Values**: --- Complete list ??
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

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | optional   | NA   | NA |

**Valid Values**:  --- Complete list ??
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
| String  | 7        |    20        |    Available     | Optional     | NA |    Allowed  |   

* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to delete a particular cross reference. 
* It will delete all fields associated with the specific cross reference 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Optional   | NA   | Allowed |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    20        |    Available     | Required     | NA |       NA          |

<!-- type: tab-end -->
---

### PRIMARY_SECURITY_CODE
* Description: Security code  associated with a front end network.
* API field: `primarySecurityCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    4        |    Available     | Optional     | NA |    Allowed |    

* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to delete a particular cross reference. 
* It will delete all fields associated with the specific cross reference 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Optional   | NA   | Allowed |    

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
* Description: Code that indicates the alliance Platform.
* API field: `alliancePlatformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    22        |    Available     | Optional     | Allowed |    Allowed |         

* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to delete a particular cross reference. 
* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to update ALLIANCE_PLATFORM_CODE

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
| String  | 2        |    3        |    Available     | Optional     | Allowed |    Allowed |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   | 
| YES     |     Yes   | 

* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to delete a particular cross reference. 
* Merchant id , Platform code  and XREF_PLATFORM_CODE will be used to update XREF_CORRESPONDENCE_INDICATOR

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Optional   | Allowed   | Allowed |         |

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
