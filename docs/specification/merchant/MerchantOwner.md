# Merchant Owner
* **Description**: Essential information about merchant owner, including contact details, business type, and contractual data, ensuring efficient transaction processing and management. Every merchant has an entry in this critical repository.
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
| String |  Back-end specific |     50     |          |          |          |       NA     |

<!-- type: tab -->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       12       |     50     | Required | Required | Not Required |       NA     |

<!-- type: tab --> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:--------:|:------------:|:------------:|
| String |       -        |     -      |     -    |          |              |       NA     |

<!-- type: tab -->