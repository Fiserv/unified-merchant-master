# Merchant Additional Data - US
* **Description**: description to come here....
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
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |            |    NA     | NA     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      12         |      12   | NA   | NA   | NA   | NA   |      |

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
### PLATFORM_CODE
* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |            |    NA     | NA     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | NA   | NA   | NA   | NA   |      |

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
### EXCLUSION_CODE
* Description: Code that indicates weather the merchant is excluded from the IRS processing.
* API field: `irsSparkExclusionCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       12        |    35        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### IRS_TIN_VALIDATION_CODE
* Description: Code that indicates the validation of the merchant's taxpayer identification number (TIN).
* API field: `irsTinValidationCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    24        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      2         |      2   | Required   | Required   | NA   | NA   |      |

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
### TIN_VALIDATION_DATE
* Description: Date on which the IRS taxpayer identification number (TIN) validation was last performed for a merchant.
* API field: `irsTinValidationDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### PAYEE_CODE
* Description: Code that indicates the unique code assigned to a payee or recipient for tax reporting purposes by the Internal Revenue Service (IRS).
* API field: `irsPayeeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       11        |    24        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### CP2100_NOTICE_RECEIVED_DATE
* Description: Date on which the merchant received a IRS CP2100 notice.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsCP2100NoticeReceivedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### CP2100_NOTICE_EFFECTIVE_DATE
* Description: Date on which the IRS CP2100 notice  becomes effective.
 
Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsCP2100NoticeEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_CODE
* Description: Code that indicates the IRS withholding is required or not.
* API field: `irsWithholdingCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       8        |    12        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_NOTIFICATION_CODE
* Description: Code that indicates the IRS back up withholding notification.
* API field: `irsWithholdingNotificationCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       6        |    22        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_NOTIFICATION_DATE
* Description: Date on which the taxpayer received a notification related to income withholding.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsWithholdingNotificationDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_REASON_CODE
* Description: Code that indicates the IRS back up withholding reason.
* API field: `irsWithholdingReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       11        |    24        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_EFFECTIVE_DATE
* Description: Date on which the IRS back up withholding becomes effective.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsWithholdingEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### WITHHOLDING_END_DATE
* Description: Date from which the IRS back up withholding is not effective.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsWithholdingEndDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### FED_WITHHOLDING_PERCENT
* Description: Percentage of backup withholding that is required to be withheld by the the IRS.
* API field: `irsFederalWithholdingPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    7        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      3         |      3   | Required   | Required   | NA   | NA   |      |

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
### STATE_WITHHOLDING_PERCENT
* Description: Percentage that applies to the withholding of state income tax.
* API field: `irsStateWithholdingPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    3        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      3         |      3   | Required   | Required   | NA   | NA   |      |

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
### FORM_CERT_STATUS_CODE
* Description: Code that indicates the status of IRS form certification.
* API field: `irsFormCertStatusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    24        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### FORM_CERT_STATUS_RECEIVED_DATE
* Description: Date on which the certification status of an IRS form was received.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsFormCertStatusReceivedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### TURF_EFFECTIVE_DATE
* Description: Effective date from when the Taxpayer's United Reporting Federation (TURF) makes an agreement with the IRS.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsTurfEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### TURF_REASON_CODE
* Description: Code that indicates the reason of updating the IRS TURF agreement.
* API field: `irsTurfReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       17        |    23        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      1   | Required   | Required   | NA   | NA   |      |

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
### TURF_UPDATE_DATE
* Description: Date on which the Taxpayer's United Reporting Federation (TURF) agreement with the IRS was last updated.

Format: CCYY-MM-DD 
Example: 2024-05-15
* API field: `irsTurfUpdateDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      10         |      10   | Required   | Required   | NA   | NA   |      |

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
### TAX_EFFECTIVE_YEAR
* Description: Year from which the IRS tax regulations, rules, and rates come into effect.
* API field: `irsTaxEffectiveYear`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |    4        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      4         |      4   | Required   | Required   | NA   | NA   |      |

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
### TIMS_ACCT_NUMBER
* Description: Account number associated with the Taxpayer Information Management System (TIMS).
* API field: `timsAccountNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       20        |    50        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |      1         |      20   | Required   | Required   | NA   | NA   |      |

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
### TAX_PAY_INDICATOR
* Description: Value that indicates whether a taxpayer has made the required tax payments for a specific period or tax year.
* API field: `taxPayIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |    2        |    Required     | Required     | NA |    NA     |

<!-- type: tab -->

##### North Specification 
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | Required   | Required   | NA   | NA   |      |

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
