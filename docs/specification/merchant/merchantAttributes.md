# Merchant Attributes
* **Description**: List of fields grouped under logical `Domains` and stored as key-value(s) pair as attribute name and values. 
* **API section**: merchantAttributes
* **Table Name**: UMM.MERCHANT_ATTRIBUTES 
* **How to Retrieve attributes from Snowflake Data tables?**:
  * Master Tables: Attributes are defined using two Master tables in UMM
    * UMM.DOMAIN_MASTER : Contains the definition of the Domain
    * UMM.ATTRIBUTE_MASTER: Contains the definition of the attributes and tied to Domain
  * UMM.MERCHANT_ATTRIBUTES stores the ID of the UMM.ATTRIBUTE_MASTER for each attributes
  * Sample Query to pull the attributes:
  ```
  SELECT
    DM.DOMAIN,
    DM.DESCRIPTION as DOMAIN_DESCRIPTION,
    ATTRMASTER.NAME,
    ATTRMASTER.DESCRIPTION as ATTR_DESCRIPTION,
    MA.VALUE
  FROM UMMPRODDB.UMM.MERCHANT_ATTRIBUTES MA
  INNER JOIN UMM.ATTRIBUTE_MASTER ATTRMASTER ON MA.ATTRIBUTE_ID = ATTRMASTER.ID
  INNER JOIN UMM.DOMAIN_MASTER DM ON DM.ID = ATTRMASTER.DOMAIN_ID
  WHERE MA.MERCHANT_ID = '208201019881'
    AND MA.PLATFORM_CODE = 'NORTH'
    AND DM.DOMAIN = 'chargebackConfig'
    AND EFFECTIVE_END_DATE is NULL;
  ```
## List of Fields:
### MERCHANT_ID
* Description: Backend unique identifier for a merchant.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |  BE specific   |     50     |   N/A   | Required | Required |

<!-- type: tab-->

##### North Specification
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       12       |     12     |   N/A   | Required | Required |

<!-- type: tab--> 

##### South Specification

| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       11       |     11     |   N/A   | Required | Required |

<!-- type: tab-->

##### GMA Specification
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       11       |     11     |   N/A   | Required | Required |

<!-- type: tab-end -->

---

### PLATFORM_CODE
* Description: Backend platform identifier e.g. North, South etc.
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

##### UMM Specification
| Type | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| ENUM |      N/A       |     40     |   N/A   | Required | Required |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)
<!-- type: tab-end -->

---

### ATTRIBUTE_ID
* Description: UMM defined attribute ID. See the query above for further details.
* API field: Not applicable - domain and attribute name along with respective descriptions are returned. Sample payload shows the domain chargebackConfig and the list of attributes under that domain.
```
"merchantAttributes": {
                "chargebackConfig": {
                    "domainDescription": "chargeback Configuration",
                    "holdChargebackIndicator": {
                        "attributeDescription": "Hold Chargebacks Indicator ",
                        "values": [
                            "0"
                        ]
                    },
                    "chargebackPrenoteIndicator": {
                        "attributeDescription": "Indicates if the merchants recieves pre-notification before receiving a charge back",
                        "values": [
                            "NO"
                        ]
                    },
                    "excessiveChargebackIndicator": {
                        "attributeDescription": "Excessive Chargeback Indicator",
                        "values": [
                            "NO"
                        ]
                    },
                    "disputeDispositionCode": {
                        "attributeDescription": "Indicates the disposition option for chargeback disputes",
                        "values": [
                            "CORE_BUSSINESS_RULES"
                        ]
                    },
                    "chargebackPrenoteDays": {
                        "attributeDescription": "Chargeback Prenote Days",
                        "values": [
                            "0"
                        ]
                    },
                    "chargebackAddressCode": {
                        "attributeDescription": "Indicates where the chargeback advice is directed",
                        "values": [
                            "DBA_ADDR_ONLY"
                        ]
                    },
                    "mediaRetrievalCode": {
                        "attributeDescription": "Code determining how the bank retrieval and chargeback retrieval advice or requests are processed",
                        "values": [
                            "EIDS"
                        ]
                    },
                    "mediaFaxNumber": {
                        "attributeDescription": "Media Fax Number",
                        "values": [
                            ""
                        ]
                    },
                    "chargebackReportDestinationCode": {
                        "attributeDescription": "Chargeback Report Destination Code",
                        "values": [
                            "CURRENT_LEVEL"
                        ]
                    }
                }
            }                 
```
* Field Specification:

<!-- type: tab 
titles: UMM
-->

##### UMM Specification
| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Numeric |      N/A       |     6      |   N/A   |  N/A   |  N/A   |

<!-- type: tab-end -->

---

### VALUE
* Description: Value of the Attribute
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry | Create | Update |
|--------|:--------------:|:----------:|:-------:|:------:|:------:|
| String |      N/A       |    200     |   N/A   |  N/A   |  N/A   |

<!-- type: tab-end -->

---

##  List of Domains
### chargebackConfig
- Description: Chargeback Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|
| excessiveChargebackIndicator | Excessive Chargeback Indicator                    | YES           | Merchant has excessive Chargeback                         | Returned |  N/A   |  Yes   |
|                              |                                                   | NO            | Merchant does not have excessive Chargeback               | Returned |  N/A   |  Yes   |
| chargebackPrenoteDays        | Chargeback Prenote Days                           | Numeric Value | Chargeback Prenote Days                                   | Returned |  N/A   |  Yes   |
| email                        | email                                             | String        | Email address on file to send CHGBK related Communication | Returned |  N/A   |  Yes   |
| chargebackAddressCode        | Indicates where the chargeback advice is directed | DBA_ADDR_ONLY | chargeback advice is directed to DBA Address on file      | Returned |  N/A   |  Yes   |


<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|
| excessiveChargebackIndicator | Excessive Chargeback Indicator                    | YES           | Merchant has excessive Chargeback                         | Returned |  N/A   |  Yes   |
|                              |                                                   | NO            | Merchant does not have excessive Chargeback               | Returned |  N/A   |  Yes   |
| chargebackPrenoteDays        | Chargeback Prenote Days                           | Numeric Value | Chargeback Prenote Days                                   | Returned |  N/A   |  Yes   |
| email                        | email                                             | String        | Email address on file to send CHGBK related Communication | Returned |  N/A   |  Yes   |
| chargebackAddressCode        | Indicates where the chargeback advice is directed | DBA_ADDR_ONLY | chargeback advice is directed to DBA Address on file      | Returned |  N/A   |  Yes   |


<!-- type: tab--> 

##### South Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|
| excessiveChargebackIndicator | Excessive Chargeback Indicator                    | YES           | Merchant has excessive Chargeback                         | Returned |  N/A   |  Yes   |
|                              |                                                   | NO            | Merchant does not have excessive Chargeback               | Returned |  N/A   |  Yes   |
| chargebackPrenoteDays        | Chargeback Prenote Days                           | Numeric Value | Chargeback Prenote Days                                   | Returned |  N/A   |  Yes   |
| email                        | email                                             | String        | Email address on file to send CHGBK related Communication | Returned |  N/A   |  Yes   |
| chargebackAddressCode        | Indicates where the chargeback advice is directed | DBA_ADDR_ONLY | chargeback advice is directed to DBA Address on file      | Returned |  N/A   |  Yes   |


<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|
| excessiveChargebackIndicator | Excessive Chargeback Indicator                    | YES           | Merchant has excessive Chargeback                         | Returned |  N/A   |  Yes   |
|                              |                                                   | NO            | Merchant does not have excessive Chargeback               | Returned |  N/A   |  Yes   |
| chargebackPrenoteDays        | Chargeback Prenote Days                           | Numeric Value | Chargeback Prenote Days                                   | Returned |  N/A   |  Yes   |
| email                        | email                                             | String        | Email address on file to send CHGBK related Communication | Returned |  N/A   |  Yes   |
| chargebackAddressCode        | Indicates where the chargeback advice is directed | DBA_ADDR_ONLY | chargeback advice is directed to DBA Address on file      | Returned |  N/A   |  Yes   |


<!-- type: tab-end -->

---





