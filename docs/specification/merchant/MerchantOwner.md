# Merchant Owner
* **Description**: Essential information about merchant owner, including demographic details, and contact information. This is a critical information for every principal owner of a merchant.
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
| String  | 34        |    50        |    Available     | NA     | NA |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA  |

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
| String  | 5        |    50        |    Available     | Required     | NA |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |        | 
| OMNIPAY26     |        | 
| SOUTH     |     South   | 
| OMNIPAY21     |        |      |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | NA   | NA     |

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
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### OWNER_SEQ_CODE
* Description: Sequesnce number of the principal owner associated with the business.
* API field: `ownerSeqCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | Allowed (optional)     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed (optional)   | Required   | NA  |

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

### FIRST_NAME
* Description: First name of the principal owner.
* API field: `firstName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    100        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### MIDDLE_NAME
* Description: Middle name of the principal owner.
* API field: `middleName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    100        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### LAST_NAME
* Description: Last name of the principal owner.
* API field: `lastName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    100        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### TITLE
* Description: Title or prefix that is used before the name of the principal owner.
* API field: `title`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    80        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### ADDRESS_1_TEXT
* Description: Address line 1.
* API field: `address1Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    150        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### ADDRESS_2_TEXT
* Description: Address line 2.
* API field: `address2Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    150        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### CITY
* Description: Name of the city.
* API field: `city`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    100        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### STATE_CODE
* Description: State province name as per <a href=https://en.wikipedia.org/wiki/ISO_3166-2:US title=Click to open target=_blank >ISO 3166-2:US codes</a> or <a href=https://en.wikipedia.org/wiki/ISO_3166-2:CA title=Click to open target=_blank >ISO 3166-2:CA codes</a>
* API field: `stateCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    10        |    Available     | Allowed     | Required |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| BC     |     State Code   | 
| YT     |     State Code   | 
| SK     |     State Code   | 
| QC     |     State Code   | 
| PE     |     State Code   | 
| ON     |     State Code   | 
| NU     |     State Code   | 
| AB     |     State Code   | 
| MB     |     State Code   | 
| NB     |     State Code   | 
| NL     |     State Code   | 
| NT     |     State Code   | 
| NS     |     State Code   |      |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| BC     |     State Code   | 
| YT     |     State Code   | 
| SK     |     State Code   | 
| QC     |     State Code   | 
| PE     |     State Code   | 
| ON     |     State Code   | 
| NU     |     State Code   | 
| AB     |     State Code   | 
| MB     |     State Code   | 
| NB     |     State Code   | 
| NL     |     State Code   | 
| NT     |     State Code   | 
| NS     |     State Code   |   |

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

### COUNTRY_CODE
* Description: Code that indicates the country.
* API field: `countryCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    10        |    Available     | Allowed     | Required |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| BRA     |     Brazil   | 
| TWN     |     Taiwan   | 
| JPN     |     Japan   | 
| SVK     |     Slovakia   | 
| IND     |     India   | 
| MYS     |     Malaysia   | 
| NZL     |     New Zealand   | 
| PRI     |     Puerto Rico   | 
| SMR     |     San Marino   | 
| BMU     |     Bermuda   | 
| AND     |     Andorra   | 
| SGP     |     Singapore   | 
| FRA     |     France   | 
| DNK     |     Denmark   | 
| CHE     |     Switzerland   | 
| IRL     |     Ireland   | 
| NLD     |     Netherlands   | 
| POL     |     Poland   | 
| ESP     |     Spain   | 
| ISL     |     Iceland   | 
| HKG     |     Hong Kong   | 
| EST     |     Estonia   | 
| BEL     |     Belgium   | 
| ISR     |     Israel   | 
| LIE     |     Liechtenstein   | 
| FIN     |     Finland   | 
| BGR     |     Bulgaria   | 
| USA     |     United States   | 
| LUX     |     Luxembourg   | 
| CZE     |     Czech Republic   | 
| NOR     |     Norway   | 
| TUR     |     Turkey   | 
| DEU     |     Germany   | 
| CAN     |     Canada   | 
| ROM     |     Romania   | 
| NA     |     Not Applicable   | 
| MLT     |     Malta   | 
| GRC     |     Greece   | 
| MCO     |     Monaco   | 
| ITA     |     Italy   | 
| LVA     |     Latvia   | 
| SVN     |     Slovenia   | 
| LTU     |     Lithuania   | 
| HRV     |     Croatia   | 
| PRT     |     Portugal   | 
| GBR     |     United Kingdom   | 
| CYP     |     Cyprus   | 
| AUS     |     Australia   | 
| AUT     |     Austria   | 
| HUN     |     Hungary   | 
| SWE     |     Sweden   | 
| GIB     |     Gibraltar   |     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| BRA     |     Brazil   | 
| TWN     |     Taiwan   | 
| JPN     |     Japan   | 
| SVK     |     Slovakia   | 
| IND     |     India   | 
| MYS     |     Malaysia   | 
| NZL     |     New Zealand   | 
| PRI     |     Puerto Rico   | 
| SMR     |     San Marino   | 
| BMU     |     Bermuda   | 
| AND     |     Andorra   | 
| SGP     |     Singapore   | 
| FRA     |     France   | 
| DNK     |     Denmark   | 
| CHE     |     Switzerland   | 
| IRL     |     Ireland   | 
| NLD     |     Netherlands   | 
| POL     |     Poland   | 
| ESP     |     Spain   | 
| ISL     |     Iceland   | 
| HKG     |     Hong Kong   | 
| EST     |     Estonia   | 
| BEL     |     Belgium   | 
| ISR     |     Israel   | 
| LIE     |     Liechtenstein   | 
| FIN     |     Finland   | 
| BGR     |     Bulgaria   | 
| USA     |     United States   | 
| LUX     |     Luxembourg   | 
| CZE     |     Czech Republic   | 
| NOR     |     Norway   | 
| TUR     |     Turkey   | 
| DEU     |     Germany   | 
| CAN     |     Canada   | 
| ROM     |     Romania   | 
| NA     |     Not Applicable   | 
| MLT     |     Malta   | 
| GRC     |     Greece   | 
| MCO     |     Monaco   | 
| ITA     |     Italy   | 
| LVA     |     Latvia   | 
| SVN     |     Slovenia   | 
| LTU     |     Lithuania   | 
| HRV     |     Croatia   | 
| PRT     |     Portugal   | 
| GBR     |     United Kingdom   | 
| CYP     |     Cyprus   | 
| AUS     |     Australia   | 
| AUT     |     Austria   | 
| HUN     |     Hungary   | 
| SWE     |     Sweden   | 
| GIB     |     Gibraltar   |  |

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

### POSTAL_CODE
* Description: Postal code or zip code.
* API field: `postalCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 5        |    20        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### BUSINESS_PHONE
* Description: Phone number of the principal owner.
* API field: `businessPhone`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### MOBILE
* Description: Mobile number of the principal owner.
* API field: `mobile`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### SIGNER_INDICATOR
* Description: Value that indicates the principal owner is an authorized signer or not. 
* API field: `signerIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    3        |    Available     | Allowed     | Required |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Signer Indicator   | 
| YES     |     Signer Indicator   |      |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Signer Indicator   | 
| YES     |     Signer Indicator   |   |

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

### GUARANTOR_INDICATOR
* Description: Value that indicates the principal guarantor exist or not.
* API field: `guarantorIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    3        |    Available     | Allowed     | Required |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Guarantor Indicator   | 
| YES     |     Guarantor Indicator   |      |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Guarantor Indicator   | 
| YES     |     Guarantor Indicator   |   |

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

### BIRTH_DATE
* Description: Date on which the principal owner was born (birth date).

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `birthDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### YEARS_AT_ADDRESS
* Description: The principal owner resides at the current address for a certain number of years.
* API field: `yearsAtAddress`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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

### OWNERSHIP_PERCENT
* Description: Percentage of ownershipthat a particular individual or entity holds in the business.
* API field: `ownershipPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | Allowed     | Required |    NA     |

<!-- type: tab -->


##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   | Required   | NA  |

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
