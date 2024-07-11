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
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   |   Minimum Length   | Max Length | Inquiry  |  Create  |  Update  |    Delete    |
|--------|:------------------:|:----------:|:--------:|:--------:|:--------:|:------------:|
| String |         12         |    50      |          |          |          |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length |   Inquiry    |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:------------:|:--------:|:------------:|:------------:|
| String |       12       |     12     | Not Required |   NA     |       NA     |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

##### GMA Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab-end -->

----
### PLATFORM_CODE
* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length |   Inquiry    |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:------------:|:--------:|:------------:|:------------:|
| String |        -       |     -      | Not Required |   NA     |       NA     |       NA     |

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
### OWNER_SEQ_CODE
* Description: Sequesnce number of the principal owner associated with the business.
* API field: `ownerSequenceNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |    100     | Required | Not Required |   Required   |   Required   |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     3      | Required |    Required  |   Required   |       NA     |

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
### FIRST_NAME
* Description: First name of the principal owner.
* API field: `ownerFirstName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     7      | Required |    Required  |   Required   |       NA     |

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
### MIDDLE_NAME
* Description: Middle name of the principal owner.
* API field: `ownerMiddleName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        1       |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |     2      | Required |    Required  |   Required   |       NA     |

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
### LAST_NAME
* Description: Last name of the principal owner.
* API field: `lastName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

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
### TITLE
* Description: Title or prefix that is used before the name of the principal owner.
* API field: `title`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       3        |    15      |     -    |          |              |       NA     |

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
### ADDRESS_1_TEXT
* Description: Address line 1.
* API field: `address1Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    150     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10        |    24      | Required |    Required  |   Required   |       NA     |

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
### ADDRESS_2_TEXT
* Description: Address line 2.
* API field: `address2Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    50      | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       0        |     0      | Required |    Required  |   Required   |       NA     |

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
### ADDRESS_3_TEXT
* Description: Address line 3.
* API field: `address3Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        -       |    -       | Required |       NA     |       NA     |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       0        |     0      | Required |       NA     |       NA     |       NA     |

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
### ADDRESS_4_TEXT
* Description: Address line 4.
* API field: `address4Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        -       |    -       | Required |       NA     |       NA     |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       0        |     0      | Required |       NA     |       NA     |       NA     |

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
### ADDRESS_5_TEXT
* Description: Address line 5.
* API field: `address5Text`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        -       |    -       | Required |       NA     |       NA     |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       0        |     0      | Required |       NA     |       NA     |       NA     |

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
### CITY
* Description: Name of the city.
* API field: `cityName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        2       |    100     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10       |     21     | Required |    Required  |   Required   |       NA     |

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
### STATE_CODE
* Description: State province name as per ISO 3166-2:US codes or ISO 3166-2:CA codes.
* API field: `stateCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    10      | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |    Required  |   Required   |       NA     |

* **Valid Values**: BC

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
### COUNTRY_CODE
* Description: Code that indicates the country.
* API field: `countryCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    10     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |     3      | Required |    Required  |   Required   |       NA     |

* **Valid Values**: BRA

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
### POSTAL_CODE
* Description: Postal code or zip code.
* API field: `postalCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       5        |    20     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      5         |      9   |  Required    |  Required    |  Required    | NA     |

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
### COUNTY_CODE
* Description: Code that indicates the county.
* API field: `countyCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      0         |      0   |  Required    |  Not Required    |  Not Required    | NA     |

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
### COUNTY_NAME
* Description: Name of the county.
* API field: `countyName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      0         |      0   |  Required    |  Not Required    |  Not Required    | NA     |

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
### BUSINESS_PHONE
* Description: Phone number of the principal owner.
* API field: `ownerPhoneNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    15     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      15   |  Required    |  Required    |  Required    | NA     |

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
### MOBILE
* Description: Mobile number of the principal owner.
* API field: `ownerMobileNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    15     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      15   |  Required    |  Required    |  Required    | NA     |

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

### SIGNER_INDICATOR
* Description: Value that indicates the principal owner is an authorized signer or not. 
* API field: `ownerSignerIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    1     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   |  Required    |  Required    |  Required    | NA     |

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

### BIRTH_DATE
* Description: Date on which the principal owner was born (birth date).

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `ownerBirthDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   |  Required    |  Required    |  Required    | NA     |

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
### YEARS_AT_ADDRESS
* Description: The principal owner resides at the current address for a certain number of years.
* API field: `ownerYearsAtAddress`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    3     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      0         |      0   |  Required    |  Required    |  Required    | NA     |

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
### EMAIL_ADDRESS
* Description: E-mail address of the principal owner.
* API field: `emailText`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      20         |      70   |  Required    |  Not Required    |  Not Required    | NA     |

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
### OWNERSHIP_PERCENT
* Description: Percentage of ownershipthat a particular individual or entity holds in the business.
* API field: `ownerPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    3     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      3         |      3   |  Required    |  Required    |  Required    | NA     |

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
### MOBILE_VALIDATION_STATUS
* Description: Code that indicates the vatiodation status of the principal owner's mobile number.
* API field: `ownerMobileValidateStatusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       15        |    15     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      3         |      3   |  Required    |  Required    |  Required    | NA     |

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
### MOBILE_VALIDATION_SOURCE_CODE
* Description: Code that indicates the vatiodation status of the principal owner's mobile number source.
* API field: `ownerMobileValidateSourceCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       15        |    50     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      3         |      3   |  Required    |  Required    |  Required    | NA     |

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
### MOBILE_VALIDATION_DATE
* Description: Date on which the principal owner's mobile number was validated.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `ownerMobileValidateDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   |  Required    |  Required    |  Required    | NA     |

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
### IDENTITY_DOC_TYPE_CODE
* Description: Code that indicates the type of tax identification document that the merchant provides for verification purpose.
* API field: `ownerTaxId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      15   |  Required    |  Not Required    |  Not Required    | NA     |

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
### IDENTITY_DOC_NUMBER
* Description: Taxpayer identification number of the principal owner.
* API field: `ownerTaxId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       20        |    50     | Required |    Required  |   Required   |       NA     |

  <!--   type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      15   |  Required    |  Required    |  Required    | NA     |

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
