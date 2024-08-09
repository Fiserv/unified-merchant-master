# Merchant Address
* **Description**: Essential information about  business address of a merchant for official purposes and communication.
* **API schema**: `Address`
* **Table Name**: `MERCHANT_ADDRESS` 

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
| String  | 8        |    8        |    Required     | Required     | Required |    NA     |

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
| String  | 9        |    9        |    Required     | Required     | Required |    NA     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    | 
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->

---

### ADDRESS_TYPE_CODE
* Description: This field represents which level of merchant hierarchy that the request pertains to (there are different uses by platform and application).
* API field: `addressTypeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 5        |    17        |    Available     | Required     | Allowed |    NA        |       

* ADDRESS_TYPE_CODE will be required to update corresponding merchant address  

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|LOCATION|	Location address|
|CORPORATE|	Corporate Address|
|MSIP_LOCATION|	MSIP Location Address|
|MSIP_CORPORATE|	MSIP Corporate Address|
|DISPUTE_ADDRESS|	Dispute communication Address|
|HEAD_OFFICE|	Head office Address|
|LEGAL|	Legal entity Address|
|BENEFICIARY|	Beneficiary Address|
|BUSINESS_MANAGER|	Business Manager Address|
|ALTERNATE_ADDRESS|	Merchant Alternate Address|

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| LOCATION     |     Location Address   | 
| CORPORATE     |     Corporate Address   |
| MSIP_LOCATION|	MSIP Location Address|
| MSIP_CORPORATE|	MSIP Corporate Address|

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Required     | NA      |    NA        |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|LOCATION     |     Location Address   |
|CORPORATE     |     Corporate Address   |
|DISPUTE_ADDRESS|	Dispute communication Address|
|HEAD_OFFICE|	Head office Address|
|LEGAL|	Legal entity Address|
|BENEFICIARY|	Beneficiary Address|
|BUSINESS_MANAGER|	Business Manager Address|

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
| String  | 1        |    50        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Required     | Allowed |    NA        |

* Note: For addressTypeCode - LOCATION, the maximum and minimum length is 40 and 0 respectively.

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
| String  | 1        |    50        |    Available     | Optional     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab-end -->
---
### ADDRESS_3_TEXT
* Description: Address line 3.
* API field: `address3Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab-end -->
---
### ADDRESS_4_TEXT
* Description: Address line 4.
* API field: `address4Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab-end -->
---
### ADDRESS_5_TEXT
* Description: Address line 5.
* API field: `address5Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    50        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Optional     | Allowed |    NA |

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
| String  | 1        |    50        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Required     | Allowed |    NA        |

* Note: For addressTypeCode - LOCATION, the maximum and minimum length is 13 and 0 respectively.

<!-- type: tab-end -->
---

### STATE_CODE
* Description: State Code 
* API field: `stateCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    3        |    Available     | Required     | Allowed |    NA         |


<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |         |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    3        |    Available     | Optional     | Allowed |    NA         |

<!-- type: tab-end -->
---

### STATE_NAME
* Description: State Name 
* API field: `stateName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |   1      |      50      |    Available     | NA     | NA |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |   1      |      50      |    Available     | NA     | NA |    NA    |  

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
| String  | 2        |    3        |    Available     | Required     | Allowed |    NA         |

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
| NA      |     Not Applicable   | 
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

Apart from above values, it can accept any valid Country code. 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |         |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Required     | Allowed |    NA         |

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
| String  | 5        |    20        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String | 0        |    11        |    Available     | Optional     | Allowed |    NA         |

* Note: For addressTypeCode - LOCATION, the maximum and minimum length is 11 and 0 respectively.

<!-- type: tab-end -->
---

### COUNTY_NAME
* Description: Name of the county.
* API field: `countyName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    30        |    Available     | Optional     | Allowed |    NA |    

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
|String  |     NA    |    NA      |     NA         |  NA     |

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
| String  | 10        |    15        |    Available     | Required     | Allowed |    NA       |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    15        |    Available     | Optional     | Allowed |    NA        |

* Note: For addressTypeCode - LOCATION, the maximum and minimum length is 16 and 0 respectively.

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
| String  | 10        |    15        |    Available     | Required     | Allowed |    NA       |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | NA        |    NA        |    NA     | NA     | NA |    NA       |  

<!-- type: tab-end -->
---

### EMAIL_ADDRESS
* Description: E-mail address of the principal owner.
* API field: `emailAddress`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    240        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | Available   | Required   | Allowed   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    60        |    Available     | Optional     | Allowed |    NA       |

<!-- type: tab-end -->
---

### FAX
* Description: Fax of the principal owner.
* API field: `fax`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Optional     | Allowed |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    15        |    Available     | Optional     | Allowed |    NA        |

<!-- type: tab-end -->
---

### DELIVERY_METHOD
* Description: Delivery method code of correspondence to this address; however, it is dependent on the delivery solutions in place for the given institution.
* API field: `deliveryMethod`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 2        |    18   |    Available     | Required     | Allowed |    NA             |

**Valid Values**: 
|         Value        |                    Description                 |
|:---------------------|:-----------------------------------------------|
| REGISTERED_MAIL | Registered Mail |
| HAND_DELIVERY | Hand Delivery |
| LETTER | Letter |
| PRINT_FILE | Printfile |
| COURIER_MAIL | Courier Mail |
| FAST_MAIL | Fast mail (A) |
| PHONE | Phone |
| EMAIL | E-Mail |
| CARD | Card |
| REGISTERED_REGULAR | Registered Regular |
| CORRESPONDENCE | Correspondence |
| INTERNET | Internet |
| REGULAR_MAIL | Regular Mail |
| SFTP | SFTP |
| REPORT | Report |
| PICK_UP | Pick Up |
| PIN_MAILER | Pin Mailer |
| OTHER | Other |
| NA | Not Applicable |
| EXPRESS_MAIL | Express Mail |
| STATEMENTS | Statements |
| FAX | Fax |
| ONLINE_PORTAL | Online Portal |
| DEFAULT | Default |
| MOBILE | Mobile |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3   |    Available      | Required     | Allowed      |    NA        |

**Valid Values**: 
|         Value        |                    Description                 |
|:---------------------|:-----------------------------------------------|
| REGISTERED_MAIL | Registered Mail |
| HAND_DELIVERY | Hand Delivery |
| LETTER | Letter |
| PRINT_FILE | Printfile |
| COURIER_MAIL | Courier Mail |
| FAST_MAIL | Fast mail (A) |
| PHONE | Phone |
| EMAIL | E-Mail |
| CARD | Card |
| REGISTERED_REGULAR | Registered Regular |
| CORRESPONDENCE | Correspondence |
| INTERNET | Internet |
| REGULAR_MAIL | Regular Mail |
| SFTP | SFTP |
| REPORT | Report |
| PICK_UP | Pick Up |
| PIN_MAILER | Pin Mailer |
| OTHER | Other |
| NA | Not Applicable |
| EXPRESS_MAIL | Express Mail |
| STATEMENTS | Statements |
| FAX | Fax |
| ONLINE_PORTAL | Online Portal |
| DEFAULT | Default |
| MOBILE | Mobile |

<!-- type: tab-end -->
---

### CONTACT_NAME
* Description: The contact name at the address location. 
* API field: `contactName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    80        |    Available     | Optional     | Allowed |    NA        |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| STRING   | NA   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 0        |    35        |    Available     | Optional     | Allowed |    NA        |

<!-- type: tab-end -->