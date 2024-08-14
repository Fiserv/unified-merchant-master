# Merchant Owner

* **Description**: Essential information about merchant owner, including demographic details, and contact information. This is a critical information for every principal owner of a merchant.
* **API schema**: `owners`
* **Table Name**: `UMM.MERCHANT_OWNER`

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
| String  | 8        |    50        |    Required     | Required     | Required |    Required  |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

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
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

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
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### OWNER_SEQ_CODE

* Description: Sequesnce number of the principal owner associated with the business.
* API field: `ownerSeqCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | Required     | Allowed  |    Allowed |

* ownerSeqCode is required to update or delete entire owner section.
* Delete will completely remove owner information associated with the specific sequence number.
* ownerSeqCode will be utilized to update owner information for a specific sequence number.

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|  String  | Available   | Required   | Allowed   | Allowed |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### FIRST_NAME

* Description: First name of the principal owner.
* API field: `firstName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|  String  | Available   | Required   | Allowed   | NA |

* North can support max 7 characters

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MIDDLE_NAME

* Description: Middle name of the principal owner.
* API field: `middleName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    30        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|  String  | Available   | Required   | Allowed   | NA |

* North can support max 2 characters

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### LAST_NAME

* Description: Last name of the principal owner.
* API field: `lastName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    25        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String  | Available   | Required   | Allowed   | NA |

* North can support max 8 characters

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TITLE

* Description: Title or prefix that is used before the name of the principal owner.
* API field: `title`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    24        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ADDRESS_1_TEXT

* Description: Address line 1.
* API field: `address1Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

* North can support max 24 characters

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### ADDRESS_2_TEXT

* Description: Address line 2.
* API field: `address2Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|  String  | Available   | Required   | Allowed   | NA |  

* North can support max 24 characters

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CITY

* Description: Name of the city.
* API field: `city`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### STATE_CODE

* Description: State province name as per ISO 3166-2:CA codes
* API field: `stateCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**: <!--need to put entire list -->
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
| NS     |     State Code   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

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
| NS     |     State Code   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### COUNTRY_CODE

* Description: Code that indicates the country.
* API field: `countryCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |      NA      |

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
| GIB     |     Gibraltar   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |      NA      |

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
| GIB     |     Gibraltar   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### POSTAL_CODE

* Description: Postal code or zip code.
* API field: `postalCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 5        |    10        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### BUSINESS_PHONE

* Description: Phone number of the principal owner.
* API field: `businessPhone`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MOBILE

* Description: Mobile number of the principal owner.
* API field: `mobile`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### SIGNER_INDICATOR

* Description: Value that indicates whether the principal owner is an authorized signer or not.
* API field: `signerIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Not Authorized   |
| YES     |     Authorized   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     Not Authorized   |
| YES     |     Authorized   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### GUARANTOR_INDICATOR

* Description: Value that indicates whether the principal guarantor exist or not.
* API field: `guarantorIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO     |     No   |
| YES     |     Yes   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

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

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

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

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### YEARS_AT_ADDRESS

* Description: The principal owner resides at the current address for a certain number of years.
* API field: `yearsAtAddress`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|  String  | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### OWNERSHIP_PERCENT

* Description: Percentage of ownershipthat a particular owner  holds in the business.
* API field: `ownershipPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MOBILE_VALIDATION_STATUS

* Description: Code that indicates the validation status of the principal owner's mobile number.
* API field: `mobileValidationStatus`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO_INFORMATION     |     Confirmed No Information   |
| LANDLINE_FAILED     |     Failed Landline Number   |
| WIRELESS_FAILED     |     Failed Wireless Number   |
| LANDLINE_VALIDATED     |     Passed Landline Number   |
| WIRELESS_VALIDATED     |     Passed Wireless Number   |

<!-- type: tab -->

|| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NO_INFORMATION     |     Confirmed No Information   |
| LANDLINE_FAILED     |     Failed Landline Number   |
| WIRELESS_FAILED     |     Failed Wireless Number   |
| LANDLINE_VALIDATED     |     Passed Landline Number   |
| WIRELESS_VALIDATED     |     Passed Wireless Number   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MOBILE_VALIDATION_SOURCE_CODE

* Description: Code that indicates the validation status of the principal owner's mobile number source.
* API field: `mobileValidationSourceCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| VIGILENCE     |     VIGILENCE   |
| None     |     Not known   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| VIGILENCE     |     VIGILENCE   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### MOBILE_VALIDATION_DATE

* Description: Date on which the principal owner's mobile number was validated.

Format: CCYY-MM-DD
Example: 2024-05-15

* API field: `mobileValidationDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---
