# Merchant Attributes
* **Description**: List of fields grouped under logical **Domains** and stored as key-value(s) pair as attributes. 
  - Example of a **Domain**: [chargebackConfig](#-chargebackconfig) is a **domain** that groups all fields called as **Attributes** those configures chargeback related processing for a merchant. Example of some attributes are:
    - Chargeback Address code indicating where chargeback related information sent 
    - Chargeback Pre-note Days 
  - See [list of Domains](#list-of-domains)
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
  * Please see [List of Domains](#list-of-domains) for available domains and attributes.
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
### acknowledgementFilePreference
---
tags: [acknowledgementFilePreference]
---
- Description: Acknowledgement File Preference
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ackFilePreference            | Acknowledgement File Preference                   | NORMAL        | Normal                                                    |Available | Required | Allowed  |    NA    |
|                              |                                                   | MASK          | Mask                                                      |Available | Required | Allowed  |    NA    |

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ackFilePreference            | Acknowledgement File Preference                   | NORMAL        | Normal                                                    |Available | Required | Allowed  |    NA    |
|                              |                                                   | MASK          | Mask                                                      |Available | Required | Allowed  |    NA    |

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|:--------:|
|                              |                                                   |               |                                                           |          |        |        |    NA    |

<!-- type: tab-end -->

### additionalTaxInfo
---
tags: [additionalTaxInfo]
---
- Description: Additional Tax Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->
##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| incomeTaxCode                | Income Tax Code                                   |               |                                                           | Available| Required | Allowed  |    NA    |    
| secondaryTaxId               | Secondary Tax ID                                  |               |                                                           | Available| Required | Allowed  |    NA    |
| vatTaxCode                   | VAT Tax Code                                      |               |                                                           | Available| Required | Allowed  |    NA    |

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| incomeTaxCode                | Income Tax Code                                   |               |                                                           | Available| Required | Allowed  |    NA    |
| secondaryTaxId               | Secondary Tax ID                                  |               |                                                           | Available| Required | Allowed  |    NA    |
| vatTaxCode                   | VAT Tax Code                                      |               |                                                           | Available| Required | Allowed  |    NA    |

<!-- type: tab-end -->

### adrp
---
tags: [adrp]
---
- Description: Auto Decision Refund Process
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| adrpCumulativeLimitAmount| Cumulative refund amount on the same card in the past 30 or 60 days         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
|                          | ADRP cumulative limit count         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpLimitAmount| A dollar limit defined for credits with no offsets         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| adrpCumulativeLimitAmount| Cumulative refund amount on the same card in the past 30 or 60 days         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
|                          | ADRP cumulative limit count         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpLimitAmount| A dollar limit defined for credits with no offsets         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### authMatchExclusion
---
tags: [authMatchExclusion]
---
- Description: Auth Match Exclusion
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| southAuthMatchExclusion| South Auth Match Exclusion        |    ROOT_LEVEL_MATCHING   |   Root Level Matching        |    Available     | Required     | Allowed |    NA |    
|                        |                                   |    FULL_MID_MATCHING   |   Full Mid Matching        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| southAuthMatchExclusion| South Auth Match Exclusion        |    ROOT_LEVEL_MATCHING   |   Root Level Matching        |    Available     | Required     | Allowed |    NA |    
|                        |                                   |    FULL_MID_MATCHING   |   Full Mid Matching        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### authSettings
---
tags: [authSettings]
---
- Description: Auth Settings
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authTypeCode| Auth Type Code        |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|             |                       |    PRE_AUTHORIZATION   |   Pre Authorization        |    Available     | Required     | Allowed |    NA |    
|             |                       |    FINAL_AUTHORIZATION   |   Final Authorization        |    Available     | Required     | Allowed |    NA |    
| transactionCurrency| Transaction Currency         |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authTypeCode| Auth Type Code        |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|             |                       |    PRE_AUTHORIZATION   |   Pre Authorization        |    Available     | Required     | Allowed |    NA |    
|             |                       |    FINAL_AUTHORIZATION   |   Final Authorization        |    Available     | Required     | Allowed |    NA |    
| transactionCurrency| Transaction Currency         |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### avsControl
---
tags: [avsControl]
---
- Description: AVS Control
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| avsAddressIndicator| Address verification service address indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                    |                                                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsExactIndicator| Address verification service exact indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                    |                                                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsNoIndicator| Address verification service no indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                    |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsRetryIndicator| Address verification service retry indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                    |                                                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsServiceIndicator| Address verification service indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsUnavailableIndicator| Address verification service unavailable indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsWholeZipIndicator| Address verification service whole zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsYesIndicator| Address verification service Yes indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| avsAddressIndicator| Address verification service address indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                    |                                                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsExactIndicator| Address verification service exact indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                    |                                                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsNoIndicator| Address verification service no indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                    |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsRetryIndicator| Address verification service retry indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                    |                                                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsServiceIndicator| Address verification service indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsUnavailableIndicator| Address verification service unavailable indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsWholeZipIndicator| Address verification service whole zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsYesIndicator| Address verification service Yes indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                              |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### bamsDissolutionHoldingsStatus
---
tags: [bamsDissolutionHoldingsStatus]
---
- Description: Bams Dissolution Holdings Status
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|             |                      |    OTHER_ASSIGNED   |   Other Assigned        |    Available     | Required     | Allowed |    NA |    
|             |                      |    BANK_OF_AMERICA   |   Bank Of America        |    Available     | Required     | Allowed |    NA |    
| status       | Program Status        |    ALLOCATED   |   Allocated        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DORMANT_CANCELLED   |   Dormant Cancelled        |    Available     | Required     | Allowed |    NA |    
|             |                      |    RESERVED_ATTACHED   |   Reserved Attached        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|             |                      |    OTHER_ASSIGNED   |   Other Assigned        |    Available     | Required     | Allowed |    NA |    
|             |                      |    BANK_OF_AMERICA   |   Bank Of America        |    Available     | Required     | Allowed |    NA |    
| status       | Program Status        |    ALLOCATED   |   Allocated        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DORMANT_CANCELLED   |   Dormant Cancelled        |    Available     | Required     | Allowed |    NA |    
|             |                      |    RESERVED_ATTACHED   |   Reserved Attached        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### billingConfig
---
tags: [billingConfig]
---
- Description: Billing cofiguration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billSuppliesIndicator| Bill Supplies Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| delayedBillingEffectiveDate| Delayed billing effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| managementFeeDate| Date that management fee will be charged        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|             |                      |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| retailerRateCode| Retailer rate code specific client usage        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                      |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billSuppliesIndicator| Bill Supplies Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| delayedBillingEffectiveDate| Delayed billing effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| managementFeeDate| Date that management fee will be charged        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|             |                      |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| retailerRateCode| Retailer rate code specific client usage        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                      |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### billmatrix
---
tags: [billmatrix]
---
- Description: Billmatrix
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ACCEPTED   |   Not Accepted        |    Available     | Required     | Allowed |    NA |    
|        | Program Status        |    ACCEPTED   |   Accepted        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ACCEPTED   |   Not Accepted        |    Available     | Required     | Allowed |    NA |    
|        | Program Status        |    ACCEPTED   |   Accepted        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### boardingAdditionalInfo
---
tags: [boardingAdditionalInfo]
---
- Description: Merchant Boarding Additional Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| descriptionOfGoods| Description of goods and services sold by the merchant        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| wisoSalesRepId| Sales rep id of the wholesale iso employee        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| descriptionOfGoods| Description of goods and services sold by the merchant        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| wisoSalesRepId| Sales rep id of the wholesale iso employee        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### cardbrandPassThruFees
---
tags: [cardbrandPassThruFees]
---
- Description: Cardbrand Pass Thru Fees
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### cardconnect
---
tags: [cardconnect]
---
- Description: Cardconnect File Identifier
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### cashAdvance
---
tags: [cashAdvance]
---
- Description: Cash Advance
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cashAdvanceLimitAmount| Cash advance Limit Amount        |    REJECT_IF_GTE_100000 - Reject if greater than or equal to 100000  |   Reject If Gte 100000 - Reject If Greater Than Or Equal To 100000        |    Available     | Required     | Allowed |    NA |    
| splitFundingAdvanceAmount| Split Funding Advance Amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    ADV_REPAID   |   Adv Repaid        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
|                              |                                           ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|                              |                                           SPLIT_FUNDING   |   Split Funding        |    Available     | Required     | Allowed |    NA |    
| splitFundingPayToMerchantId| Split funding pay to merchant number        |    STRING - Digits only - MERCHANT ID   |   String - Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| splitFundingPercent| Split Funding Percentage        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    MER_ADV_FUNDING   |   Mer Adv Funding        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    FDMCA   |   Fdmca        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    RAPID_ADV   |   Rapid Adv        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    FUND_TREE   |   Fund Tree        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    ADV_ME   |   Adv Me        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    ADV_ME_INC   |   Adv Me Inc        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    BIZ2_CREDIT   |   Biz2 Credit        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cashAdvanceLimitAmount| Cash advance Limit Amount        |    REJECT_IF_GTE_100000 - Reject if greater than or equal to 100000  |   Reject If Gte 100000 - Reject If Greater Than Or Equal To 100000        |    Available     | Required     | Allowed |    NA |    
| splitFundingAdvanceAmount| Split Funding Advance Amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    ADV_REPAID   |   Adv Repaid        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
|                              |                                           ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|                              |                                           SPLIT_FUNDING   |   Split Funding        |    Available     | Required     | Allowed |    NA |    
| splitFundingPayToMerchantId| Split funding pay to merchant number        |    STRING - Digits only - MERCHANT ID   |   String - Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| splitFundingPercent| Split Funding Percentage        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    MER_ADV_FUNDING   |   Mer Adv Funding        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    FDMCA   |   Fdmca        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    RAPID_ADV   |   Rapid Adv        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    FUND_TREE   |   Fund Tree        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    ADV_ME   |   Adv Me        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    ADV_ME_INC   |   Adv Me Inc        |    Available     | Required     | Allowed |    NA |    
|                              |                                         |    BIZ2_CREDIT   |   Biz2 Credit        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### cashAdvanceProgram
---
tags: [cashAdvanceProgram]
---
- Description: Cash Advance Gl Funding Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                      |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                      |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!-- type: tab-end -->

### channelLevelDiscoverPromotionalPvi
---
tags: [channelLevelDiscoverPromotionalPvi]
---
- Description: Discover Promotional Program Verification Identifier - Channel Level
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FD_DISCOVER_PROMO   |   Fd Discover Promo        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CLIENT_DISCOVER_PRO   |   Client Discover Pro        |    Available     | Required     | Allowed |    NA |    
| status      | Program Status       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FD_DISCOVER_PROMO   |   Fd Discover Promo        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CLIENT_DISCOVER_PRO   |   Client Discover Pro        |    Available     | Required     | Allowed |    NA |    
| status      | Program Status       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

###  chargebackConfig
---
tags: [chargebackConfig]
---
- Description: chargeback Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| chargebackAddressCode| Indicates where the chargeback advice is directed        |    DBA_ADDR_BILLTO_ADDR   |   Dba Addr Billto Addr        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BILLTO_ADDR_ONLY   |   Billto Addr Only        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DBA_ADDR_ONLY   |   Dba Addr Only        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BILLTO_ADDR_DBA_ADDR   |   Billto Addr Dba Addr        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| chargebackPrenoteDays| Chargeback Prenote Days        |    STRING having digits only   |   String Having Digits Only        |    Available     | Required     | Allowed |    NA |    
| chargebackPrenoteIndicator| Indicates if the merchants recieves pre-notification before receiving a charge back        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| chargebackReportDestinationCode| Chargeback Report Destination Code        |    CHAIN   |   Chain        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    OUTLET   |   Outlet        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CORP   |   Corp        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BUSINESS   |   Business        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CURRENT_LEVEL   |   Current Level        |    Available     | Required     | Allowed |    NA |    
| disputeDispositionCode| Indicates the disposition option for chargeback disputes        |    DOC_FOLLOW_DEBIT   |   Doc Follow Debit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_WITH_DEBIT   |   Doc With Debit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CORE_BUSSINESS_RULES   |   Core Bussiness Rules        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_DEBIT_REP   |   Doc Debit Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_FOLLOWS_DEBIT_WITH_REP   |   Doc Follows Debit With Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DEBIT_NO_DOC_WITH_REP   |   Debit No Doc With Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DEBIT_NO_DOC   |   Debit No Doc        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DROP_TO_QUEUE   |   Drop To Queue        |    Available     | Required     | Allowed |    NA |    
| email| email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| excessiveChargebackIndicator| Excessive Chargeback Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| holdChargebackIndicator| Hold Chargebacks Indicator         |    PROCESS_MONTHLY   |   Process Monthly        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    PROCESS_DAILY   |   Process Daily        |    Available     | Required     | Allowed |    NA |    
| mediaFaxNumber| Media Fax Number        |    STRING having digits only   |   String Having Digits Only        |    Available     | Required     | Allowed |    NA |    
| mediaRetrievalCode| Code determining how the bank retrieval and chargeback retrieval advice or requests are processed        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| chargebackAddressCode| Indicates where the chargeback advice is directed        |    DBA_ADDR_BILLTO_ADDR   |   Dba Addr Billto Addr        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BILLTO_ADDR_ONLY   |   Billto Addr Only        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DBA_ADDR_ONLY   |   Dba Addr Only        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BILLTO_ADDR_DBA_ADDR   |   Billto Addr Dba Addr        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| chargebackPrenoteDays| Chargeback Prenote Days        |    STRING having digits only   |   String Having Digits Only        |    Available     | Required     | Allowed |    NA |    
| chargebackPrenoteIndicator| Indicates if the merchants recieves pre-notification before receiving a charge back        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| chargebackReportDestinationCode| Chargeback Report Destination Code        |    CHAIN   |   Chain        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    OUTLET   |   Outlet        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CORP   |   Corp        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BUSINESS   |   Business        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CURRENT_LEVEL   |   Current Level        |    Available     | Required     | Allowed |    NA |    
| disputeDispositionCode| Indicates the disposition option for chargeback disputes        |    DOC_FOLLOW_DEBIT   |   Doc Follow Debit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_WITH_DEBIT   |   Doc With Debit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    CORE_BUSSINESS_RULES   |   Core Bussiness Rules        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_DEBIT_REP   |   Doc Debit Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DOC_FOLLOWS_DEBIT_WITH_REP   |   Doc Follows Debit With Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DEBIT_NO_DOC_WITH_REP   |   Debit No Doc With Rep        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DEBIT_NO_DOC   |   Debit No Doc        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    DROP_TO_QUEUE   |   Drop To Queue        |    Available     | Required     | Allowed |    NA |    
| email| email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| excessiveChargebackIndicator| Excessive Chargeback Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| holdChargebackIndicator| Hold Chargebacks Indicator         |    PROCESS_MONTHLY   |   Process Monthly        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                      |                                                          |    PROCESS_DAILY   |   Process Daily        |    Available     | Required     | Allowed |    NA |    
| mediaFaxNumber| Media Fax Number        |    STRING having digits only   |   String Having Digits Only        |    Available     | Required     | Allowed |    NA |    
| mediaRetrievalCode| Code determining how the bank retrieval and chargeback retrieval advice or requests are processed        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


###  commercialCardInterchangeService
---
tags: [commercialCardInterchangeService]
---
- Description: Commercial Card Interchange Service
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ccisMerchantIncome| Commercial Card Interchange Service Merchant Income        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ccisMerchantIncome| Commercial Card Interchange Service Merchant Income        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



###  compassOnNorth
---
tags: [compassOnNorth]
---
- Description: Compass Podb Functionality On North
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| forcedDeposit| Eligible For Force Deposits        |    FORCE_DEPOSITS   |   Force Deposits        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_FORCE_DEPOSITS   |   No Force Deposits        |    Available     | Required     | Allowed |    NA |    
| partialReversals| Eligible For Partial Reversals        |    NO_PARTIAL_REVERSALS   |   No Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    PARTIAL_REVERSALS   |   Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_REAUTHORIZATIONS   |   No Reauthorizations        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    EXTENDED_AUTH_NO_REAUT   |   Extended Auth No Reaut        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    REAUTHORIZATIONS   |   Reauthorizations        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACTIVE_COMPASS_ON_NORTH   |   Active Compass On North        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL_COMPASS_ON_NORTH   |   Cancel Compass On North        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| forcedDeposit| Eligible For Force Deposits        |    FORCE_DEPOSITS   |   Force Deposits        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_FORCE_DEPOSITS   |   No Force Deposits        |    Available     | Required     | Allowed |    NA |    
| partialReversals| Eligible For Partial Reversals        |    NO_PARTIAL_REVERSALS   |   No Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    PARTIAL_REVERSALS   |   Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_REAUTHORIZATIONS   |   No Reauthorizations        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    EXTENDED_AUTH_NO_REAUT   |   Extended Auth No Reaut        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    REAUTHORIZATIONS   |   Reauthorizations        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACTIVE_COMPASS_ON_NORTH   |   Active Compass On North        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL_COMPASS_ON_NORTH   |   Cancel Compass On North        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



###  compassSpecialFeatures
---
tags: [compassSpecialFeatures]
---
- Description: Compass Front End Generated Refund Auths
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| amexOnlineRefund| Amex Online Refund        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| compassFrontendGenreFauth| Compass frontend Gen Ref Auth        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| visaToleranceCheckInd| Visa Tolerance Check Ind        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| amexOnlineRefund| Amex Online Refund        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| compassFrontendGenreFauth| Compass frontend Gen Ref Auth        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| visaToleranceCheckInd| Visa Tolerance Check Ind        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


###  conditionalApprovalProgram
---
tags: [conditionalApprovalProgram]
---
- Description: Conditional Approval Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    MISSING_CREDIT_DATA   |   Missing Credit Data        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CREDIT_RISK_REVIEW   |   Credit Risk Review        |    Available     | Required     | Allowed |    NA |    
|             |                      |    APP_INCONSISTENCIES   |   App Inconsistencies        |    Available     | Required     | Allowed |    NA |    
|             |                      |    REMOVED_FRM_COND_APP   |   Removed Frm Cond App        |    Available     | Required     | Allowed |    NA |    
|             |                      |    MISS_CRED_DATA_MPA   |   Miss Cred Data Mpa        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CRED_DATA_RISK_REV   |   Cred Data Risk Rev        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CRED_RISK_REV_MPA   |   Cred Risk Rev Mpa        |    Available     | Required     | Allowed |    NA |    
|             |                      |    INACTIVE   |   Inactive        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    MISSING_CREDIT_DATA   |   Missing Credit Data        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CREDIT_RISK_REVIEW   |   Credit Risk Review        |    Available     | Required     | Allowed |    NA |    
|             |                      |    APP_INCONSISTENCIES   |   App Inconsistencies        |    Available     | Required     | Allowed |    NA |    
|             |                      |    REMOVED_FRM_COND_APP   |   Removed Frm Cond App        |    Available     | Required     | Allowed |    NA |    
|             |                      |    MISS_CRED_DATA_MPA   |   Miss Cred Data Mpa        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CRED_DATA_RISK_REV   |   Cred Data Risk Rev        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CRED_RISK_REV_MPA   |   Cred Risk Rev Mpa        |    Available     | Required     | Allowed |    NA |    
|             |                      |    INACTIVE   |   Inactive        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### contract
---
tags: [contract]
---
- Description: Contract
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| clientRegionIndex| Client Region Index for Omnipay        |    BIN_OVERRIDE_123018   |   Bin Override 123018        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    CANADA   |   Canada        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    UNITEDKINGDOM   |   Unitedkingdom        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123008   |   Bin Override 123008        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    SINGAPORE   |   Singapore        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    AUSTRALIA   |   Australia        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123013   |   Bin Override 123013        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123019   |   Bin Override 123019        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123009   |   Bin Override 123009        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123007   |   Bin Override 123007        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123014   |   Bin Override 123014        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    HONG_KONG   |   Hong Kong        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123016   |   Bin Override 123016        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123005   |   Bin Override 123005        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123015   |   Bin Override 123015        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_TRANSACTION   |   By Transaction        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123006   |   Bin Override 123006        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123012   |   Bin Override 123012        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_TRAN_REJECTS   |   By Tran Rejects        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_COUNTRY   |   By Country        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123011   |   Bin Override 123011        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123010   |   Bin Override 123010        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123017   |   Bin Override 123017        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123004   |   Bin Override 123004        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123002   |   Bin Override 123002        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123020   |   Bin Override 123020        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123001   |   Bin Override 123001        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    EUROPEAN_UNION   |   European Union        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123003   |   Bin Override 123003        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    JAPAN   |   Japan        |    Available     | Required     | Allowed |    NA |    
| clientTariff     | This the merchant tariff assigned to the merchant        |       |           |    Available     | Required     | Allowed |    NA |    
| postingMethod| The posting method assigned to the merchant        |    GRS_999_USD   |   Grs 999 Usd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_ZAR_999   |   Gma Zar 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA_HK_999   |   Na Hk 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_HUF   |   All To Huf        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_GBP   |   Grs 999 Gbp        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG5_EU_999   |   Reg5 Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_NOK_999   |   Gma Nok 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_USD_MSC   |   Pf Usd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG1_SG_999   |   Reg1 Sg 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_CHF_MSC   |   Pf Chf Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_NZD_MSC   |   Pf Nzd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_EUR   |   Grs 999 Eur        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_AUD   |   Grs 999 Aud        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_SEK_999   |   Gma Sek 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_SEK   |   Grs 999 Sek        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_SGD_MSC   |   Pf Sgd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_GBP_MSC   |   Pf Gbp Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_SEK_MSC   |   Pf Sek Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_JPY   |   Grs 999 Jpy        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_CAD   |   Grs 999 Cad        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_2   |   Regular 2        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_EUR_MSC   |   Pf Eur Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_NOK   |   Grs 999 Nok        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA_EU_999   |   Na Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_6   |   Regular 6        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_DKK   |   Grs 999 Dkk        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_HKD_MSC   |   Pf Hkd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_CHF   |   Grs 999 Chf        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_CHF_999   |   Gma Chf 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_4   |   Regular 4        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_CAD_MSC   |   Pf Cad Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_NOK_MSC   |   Pf Nok Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA   |   Na        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_DKK_999   |   Gma Dkk 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_1EUR   |   All To 1Eur        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_JPY_MSC   |   Pf Jpy Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_NZD   |   Grs 999 Nzd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_CZK   |   All To Czk        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_1   |   Regular 1        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    TARIFF_15   |   Tariff 15        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_SGD   |   All To Sgd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG6_SG_999   |   Reg6 Sg 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG3_EU_999   |   Reg3 Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_ZAR_MSC   |   Pf Zar Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_DKK_MSC   |   Pf Dkk Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_HKD   |   Grs 999 Hkd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_ZAR   |   Grs 999 Zar        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    TR15_JP_999   |   Tr15 Jp 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_NZD_999   |   Gma Nzd 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_SGD   |   Grs 999 Sgd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_3   |   Regular 3        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_AUD_MSC   |   Pf Aud Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_GBP   |   All To Gbp        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_8   |   Regular 8        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_PLN   |   All To Pln        |    Available     | Required     | Allowed |    NA |    
| protectAgainstFXChange| Indicate if the Merchant is protected against currency fluctuations on the event the transaction is disputed        |    FALSE   |   False        |    Available     | Required     | Allowed |    NA |    
| salesLead| Secondary Tax ID        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| serviceContractIndex| Service contract defines the processing rules for a merchant        |    SERVICE_CONTRACT_1   |   Service Contract 1        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| clientRegionIndex| Client Region Index for Omnipay        |    BIN_OVERRIDE_123018   |   Bin Override 123018        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    CANADA   |   Canada        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    UNITEDKINGDOM   |   Unitedkingdom        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123008   |   Bin Override 123008        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    SINGAPORE   |   Singapore        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    AUSTRALIA   |   Australia        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123013   |   Bin Override 123013        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123019   |   Bin Override 123019        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123009   |   Bin Override 123009        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123007   |   Bin Override 123007        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123014   |   Bin Override 123014        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    HONG_KONG   |   Hong Kong        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123016   |   Bin Override 123016        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123005   |   Bin Override 123005        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123015   |   Bin Override 123015        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_TRANSACTION   |   By Transaction        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123006   |   Bin Override 123006        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123012   |   Bin Override 123012        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_TRAN_REJECTS   |   By Tran Rejects        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BY_COUNTRY   |   By Country        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123011   |   Bin Override 123011        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123010   |   Bin Override 123010        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123017   |   Bin Override 123017        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123004   |   Bin Override 123004        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123002   |   Bin Override 123002        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123020   |   Bin Override 123020        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123001   |   Bin Override 123001        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    EUROPEAN_UNION   |   European Union        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    BIN_OVERRIDE_123003   |   Bin Override 123003        |    Available     | Required     | Allowed |    NA |    
|                  |                                        |    JAPAN   |   Japan        |    Available     | Required     | Allowed |    NA |    
| clientTariff     | This the merchant tariff assigned to the merchant        |       |           |    Available     | Required     | Allowed |    NA |    
| postingMethod| The posting method assigned to the merchant        |    GRS_999_USD   |   Grs 999 Usd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_ZAR_999   |   Gma Zar 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA_HK_999   |   Na Hk 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_HUF   |   All To Huf        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_GBP   |   Grs 999 Gbp        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG5_EU_999   |   Reg5 Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_NOK_999   |   Gma Nok 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_USD_MSC   |   Pf Usd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG1_SG_999   |   Reg1 Sg 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_CHF_MSC   |   Pf Chf Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_NZD_MSC   |   Pf Nzd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_EUR   |   Grs 999 Eur        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_AUD   |   Grs 999 Aud        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_SEK_999   |   Gma Sek 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_SEK   |   Grs 999 Sek        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_SGD_MSC   |   Pf Sgd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_GBP_MSC   |   Pf Gbp Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_SEK_MSC   |   Pf Sek Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_JPY   |   Grs 999 Jpy        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_CAD   |   Grs 999 Cad        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_2   |   Regular 2        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_EUR_MSC   |   Pf Eur Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_NOK   |   Grs 999 Nok        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA_EU_999   |   Na Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_6   |   Regular 6        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_DKK   |   Grs 999 Dkk        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_HKD_MSC   |   Pf Hkd Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_CHF   |   Grs 999 Chf        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_CHF_999   |   Gma Chf 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_4   |   Regular 4        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_CAD_MSC   |   Pf Cad Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_NOK_MSC   |   Pf Nok Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    NA   |   Na        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_DKK_999   |   Gma Dkk 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_1EUR   |   All To 1Eur        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_JPY_MSC   |   Pf Jpy Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_NZD   |   Grs 999 Nzd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_CZK   |   All To Czk        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_1   |   Regular 1        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    TARIFF_15   |   Tariff 15        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_SGD   |   All To Sgd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG6_SG_999   |   Reg6 Sg 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REG3_EU_999   |   Reg3 Eu 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_ZAR_MSC   |   Pf Zar Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_DKK_MSC   |   Pf Dkk Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_HKD   |   Grs 999 Hkd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_ZAR   |   Grs 999 Zar        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    TR15_JP_999   |   Tr15 Jp 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GMA_NZD_999   |   Gma Nzd 999        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    GRS_999_SGD   |   Grs 999 Sgd        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_3   |   Regular 3        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    PF_AUD_MSC   |   Pf Aud Msc        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_GBP   |   All To Gbp        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    REGULAR_8   |   Regular 8        |    Available     | Required     | Allowed |    NA |    
|              |                                                    |    ALL_TO_PLN   |   All To Pln        |    Available     | Required     | Allowed |    NA |    
| protectAgainstFXChange| Indicate if the Merchant is protected against currency fluctuations on the event the transaction is disputed        |    FALSE   |   False        |    Available     | Required     | Allowed |    NA |    
| salesLead| Secondary Tax ID        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| serviceContractIndex| Service contract defines the processing rules for a merchant        |    SERVICE_CONTRACT_1   |   Service Contract 1        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-end -->

### contractExpirationDate

---
tags: [contractExpirationDate]
---
- Description: Contract Expiration Date Notifications/Flag
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractExpirationDate| Contract Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| gcid| Global Client Id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractExpirationDate| Contract Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| gcid| Global Client Id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### conversionInformation

---
tags: [conversionInformation]
---
- Description: Conversion  Account Source System Data
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| salesmanCode| Salesman Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| salesmanCode| Salesman Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### creditSettings

---
tags: [creditSettings]
---
- Description: Credit Settings
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| creditBinInclusionIndicator| Credit BIN Inclusion Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| creditLimitAmount| Credit Limit Amount        |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
| cumulativeCreditLimitAmount| Cumulative Credit Limit Amount        |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
| cumulativeSalesLimitAmount| Cumulative Sales Limit Amount        |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| creditBinInclusionIndicator| Credit BIN Inclusion Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| creditLimitAmount| Credit Limit Amount        |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                  |                            |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
| cumulativeCreditLimitAmount| Cumulative Credit Limit Amount        |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                            |                                       |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
| cumulativeSalesLimitAmount| Cumulative Sales Limit Amount        |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    UNLIMITED   |   Unlimited        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Required     | Allowed |    NA |    
|                            |                                     |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### crossBorderAcquiring

---
tags: [crossBorderAcquiring]
---
- Description: Cross Border Acquiring
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| viSingleMerchantId| Visa Single Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| viSmiActivationInd| Visa Smi Activation Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                   |                                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| viSingleMerchantId| Visa Single Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| viSmiActivationInd| Visa Smi Activation Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                   |                                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### dccForIab

---
tags: [dccForIab]
---
- Description: Dynamic Currency Conversion For International Agent Bank
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    DCC   |   Dcc        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DYNAMIC_PRICING   |   Dynamic Pricing        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    DCC   |   Dcc        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DYNAMIC_PRICING   |   Dynamic Pricing        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### depositRequirement

---
tags: [depositRequirement]
---
- Description: Deposit Requirement
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| programGuideVersion| Program Guide Version        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| programGuideVersion| Program Guide Version        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->


### disregardedEntity

---
tags: [disregardedEntity]
---
- Description: Disregarded Entity
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|       |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|       |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### earlyTerminationFee

---
tags: [earlyTerminationFee]
---
- Description: Early Termination Fee
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| earlyTermDate| Early termination date applicable to charging an associated fee        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeAmount| Early termination fee amount        |    STRING - Digits only - no decimal (max length - 4, min - 1)   |   String - Digits Only - No Decimal (Max Length: 4, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeIndicator| Early termination fee indicator        |    NO_TERMINATION_FEE   |   No Termination Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    CARS_DFAULT_FEE   |   Cars Dfault Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    USER_DEFINED_FEE   |   User Defined Fee        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| earlyTermDate| Early termination date applicable to charging an associated fee        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeAmount| Early termination fee amount        |    STRING - Digits only - no decimal (max length - 4, min - 1)   |   String - Digits Only - No Decimal (Max Length: 4, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeIndicator| Early termination fee indicator        |    NO_TERMINATION_FEE   |   No Termination Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    CARS_DFAULT_FEE   |   Cars Dfault Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    USER_DEFINED_FEE   |   User Defined Fee        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### electronicTicketCapture

---
tags: [electronicTicketCapture]
---
- Description: Electronic Ticket Capture
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| etcBypassEditsIndicator| TellS the edit programs if the Merchant wishes to let all his ETC transactions process        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                        |                                                                                               |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| etcCutoffTimeCode| Code indicating what time electronic ticket capture processing is terminated for the day        |    6PM_CST   |   6Pm Cst        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    10PM_EST   |   10Pm Est        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    12AM_CST   |   12Am Cst        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| etcOptionCode| Code identifying the type of electronic ticket capture processing used        |    None   |   None        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_VOICE_BKP   |   Etc Voice Bkp        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    NON_ETC   |   Non Etc        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_VOICE_BK_W_CLS_BAT   |   Etc Voice Bk W Cls Bat        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_ELECTRONIC_ONLY   |   Etc Electronic Only        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    HOST_OUT_OF_BALANCE   |   Host Out Of Balance        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_PLUS   |   Etc Plus        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_PLUS_DEBIT   |   Etc Plus Debit        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    HOST_MUST_BALANCE   |   Host Must Balance        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_ELC_W_CLS_BAT   |   Etc Elc W Cls Bat        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| etcBypassEditsIndicator| TellS the edit programs if the Merchant wishes to let all his ETC transactions process        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                        |                                                                                               |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| etcCutoffTimeCode| Code indicating what time electronic ticket capture processing is terminated for the day        |    6PM_CST   |   6Pm Cst        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    10PM_EST   |   10Pm Est        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    12AM_CST   |   12Am Cst        |    Available     | Required     | Allowed |    NA |    
|                  |                                                                                                 |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| etcOptionCode| Code identifying the type of electronic ticket capture processing used        |    None   |   None        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_VOICE_BKP   |   Etc Voice Bkp        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    NON_ETC   |   Non Etc        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_VOICE_BK_W_CLS_BAT   |   Etc Voice Bk W Cls Bat        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_ELECTRONIC_ONLY   |   Etc Electronic Only        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    HOST_OUT_OF_BALANCE   |   Host Out Of Balance        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_PLUS   |   Etc Plus        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_PLUS_DEBIT   |   Etc Plus Debit        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    HOST_MUST_BALANCE   |   Host Must Balance        |    Available     | Required     | Allowed |    NA |    
|              |                                                                               |    ETC_ELC_W_CLS_BAT   |   Etc Elc W Cls Bat        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->


### enhanceDebitCompletionFlow

---
tags: [enhanceDebitCompletionFlow]
---
- Description: Enhance Debit Completion Flow For Pts Direct Send Merchants
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ENHANCED_DB_FLOW_OFF   |   Enhanced Db Flow Off        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ENHANCED_DB_FLOW_ON   |   Enhanced Db Flow On        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ENHANCED_DB_FLOW_OFF   |   Enhanced Db Flow Off        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ENHANCED_DB_FLOW_ON   |   Enhanced Db Flow On        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### fdggMigration

---
tags: [fdggMigration]
---
- Description: First Data Global Gateway Migration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_MIGRATED   |   Not Migrated        |    Available     | Required     | Allowed |    NA |    
|       |                       |    MIGRATED   |   Migrated        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_MIGRATED   |   Not Migrated        |    Available     | Required     | Allowed |    NA |    
|       |                       |    MIGRATED   |   Migrated        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->


### financialBuAssignmentValues

---
tags: [financialBuAssignmentValues]
---
- Description: Financial Bu Assignment Values
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| companyCode| Company Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| financeAlliance| Finance Alliance        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financeEntity| Finance Entity        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financeParent| Finance Parent        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financePortfolio| Finance Portfolio        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fmgGroupCode| Fmg Group Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fmgMarkerBank| Fmg Marker Bank        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Required     | Allowed |    NA |    
| futureUse1| Future Use 1        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse2| Future Use 2        |       |           |    Available     | Required     | Allowed |    NA |    
| globalClientDescription| Global Client Description        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| globalClientId| Global Client Id        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| profitCenterDescription| Profit Center Description        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| profitCenterId| Profit Center Id        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| companyCode| Company Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| financeAlliance| Finance Alliance        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financeEntity| Finance Entity        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financeParent| Finance Parent        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| financePortfolio| Finance Portfolio        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fmgGroupCode| Fmg Group Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fmgMarkerBank| Fmg Marker Bank        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Required     | Allowed |    NA |    
| futureUse1| Future Use 1        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse2| Future Use 2        |       |           |    Available     | Required     | Allowed |    NA |    
| globalClientDescription| Global Client Description        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| globalClientId| Global Client Id        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| profitCenterDescription| Profit Center Description        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| profitCenterId| Profit Center Id        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->



### firstHawaiianBank

---
tags: [firstHawaiianBank]
---
- Description: First Hawaiian Bank
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| fhbNaicsNumber| Fhb Naics Number N        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| fhbNaicsNumber| Fhb Naics Number N        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### foreignLanguageSupport

---
tags: [foreignLanguageSupport]
---
- Description: Foreign Language Support
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| foreignLanguageSupport| Foreign Language Support        |    JAPANESE   |   Japanese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    SOMALI   |   Somali        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    HINDI   |   Hindi        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    FRENCH   |   French        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    FARSI   |   Farsi        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    BURMESE   |   Burmese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    CAMBODIAN   |   Cambodian        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    CANTONESE   |   Cantonese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    HAITIANCREOLE   |   Haitiancreole        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    ARABIC   |   Arabic        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    KAREN   |   Karen        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    KOREAN   |   Korean        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| foreignLanguageSupport| Foreign Language Support        |    JAPANESE   |   Japanese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    SOMALI   |   Somali        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    HINDI   |   Hindi        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    FRENCH   |   French        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    FARSI   |   Farsi        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    BURMESE   |   Burmese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    CAMBODIAN   |   Cambodian        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    CANTONESE   |   Cantonese        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    HAITIANCREOLE   |   Haitiancreole        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    ARABIC   |   Arabic        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    KAREN   |   Karen        |    Available     | Required     | Allowed |    NA |    
|                       |                                 |    KOREAN   |   Korean        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### franchise
---
tags: [franchise]
---
- Description: Franchise
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### fraudAndAccountTakeoverRisk
---
tags: [fraudAndAccountTakeoverRisk]
---
- Description: Fraud And Account Takeover Risk
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    CAUTION_PREVIOUS_FRAUD   |   Caution Previous Fraud        |    Available     | Required     | Allowed |    NA |    
|             |                |    URGENT_MERCH_AT_RISK   |   Urgent Merch At Risk        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    CAUTION_PREVIOUS_FRAUD   |   Caution Previous Fraud        |    Available     | Required     | Allowed |    NA |    
|             |                |    URGENT_MERCH_AT_RISK   |   Urgent Merch At Risk        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### freeProcessing
---
tags: [freeProcessing]
---
- Description: Free Processing
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    COMPLETED   |   Completed        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
| achSuspenseHoldIndicator| ACH suspense hold indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|       |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| achSuspenseReleaseIndicator| ACH suspense release indicator        |    DIVERT_TO_CARS   |   Divert To Cars        |    Available     | Required     | Allowed |    NA |    
|       |                       |    HOLD_30_DAYS   |   Hold 30 Days        |    Available     | Required     | Allowed |    NA |    
|       |                       |    RELEASE_FUNDING   |   Release Funding        |    Available     | Required     | Allowed |    NA |    
| agentBankSplitIndicator| Indicates if Bank Client is considered an agent relationship to FDCS        |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|       |                       |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
| bankwireBbkText| Bankwire beneficiary BBK Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| bankwireBnfText| Bankwire beneficiary BNF Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| bankwireObiText| Bankwire beneficiary OBI Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| chargebacksBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| convenienceFeeCode| Convenience fee code to indicate the ABA or DDA to be charged        |    ABA_DDA_3   |   Aba Dda 3        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_5   |   Aba Dda 5        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    None   |   None        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_2   |   Aba Dda 2        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_1   |   Aba Dda 1        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_4   |   Aba Dda 4        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                             |                                      |    2 - Bank Sequence Number#2  |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                             |                                      |    3 - Bank Sequence Number#3  |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                             |                                      |    4 - Bank Sequence Number#4  |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                             |                                      |    5 - Bank Sequence Number#5   |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| depositsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
|                           |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| depositsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| depositsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| depositsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| discountsBankSequenceNumber| Funding Bank Sequence        |  1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
|                            |                              |  2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |
|                            |                              |  3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                            |                              |  4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |   
|                            |                              |  5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5         |    Available     | Required     | Allowed |    NA |   
| discountsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| discountsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                           |                            |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| discountsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| feesBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |
|                       |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |
|                       |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                       |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |
|                       |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |
| feesFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| feesFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                      |                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| feesFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    2 - Bank Sequence Number#2        |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    3 - Bank Sequence Number#3        |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    4 - Bank Sequence Number#4        |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    5 - Bank Sequence Number#5        |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| funding30DayOverrideDate| Funding 30 day daily override date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| funding30DayOverrideIndicator| Funding 30 day override indicator        |    NOT_OVERRIDE   |   Not Override        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    OVERRIDE   |   Override        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
| fundingAchDelayDays| Retention period for deposits and daily discount before releasing them for ACH processing        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingBankCode| Funding Bank Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fundingCurrencyCode| Funding Currency Code        |    QATARI_RIAL   |   Qatari Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ISRAELI_NEW_SHEKEL   |   Israeli New Shekel        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFA_FRANC_BEAC   |   Cfa Franc Beac        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UNITED_STATES_DOLLAR   |   United States Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CONGOLESE_FRANC   |   Congolese Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAYSIAN_RINGGIT   |   Malaysian Ringgit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAURITIAN_RUPEE   |   Mauritian Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOROCCAN_DIRHAM   |   Moroccan Dirham        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARUBAN_FLORIN   |   Aruban Florin        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PERUVIAN_SOL   |   Peruvian Sol        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ST_HELENA_POUND   |   St Helena Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BURUNDI_FRANC   |   Burundi Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BRUNEI_DOLLAR   |   Brunei Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COMOROS_FRANC   |   Comoros Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LAO_KIP   |   Lao Kip        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JAMAICAN_DOLLAR   |   Jamaican Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JAPANESE_YEN   |   Japanese Yen        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_KOREAN_WON   |   South Korean Won        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KUWAITI_DINAR   |   Kuwaiti Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NICARAGUAN_CORDOBA   |   Nicaraguan Cordoba        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PARAGUAYAN_GUARANI   |   Paraguayan Guarani        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KYRGYZSTAN_SOM   |   Kyrgyzstan Som        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUINEAN_FRANC   |   Guinean Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    POUND_STERLING   |   Pound Sterling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SINGAPORE_DOLLAR   |   Singapore Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DJIBOUTIAN_FRANC   |   Djiboutian Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CROTIAN_KUNA   |   Crotian Kuna        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    YEMENI_RIAL   |   Yemeni Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAWIAN_KWACHA   |   Malawian Kwacha        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZIMBABWE_DOLLAR   |   Zimbabwe Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NORWEGIAN_KRONE   |   Norwegian Krone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ALBANIAN_LEK   |   Albanian Lek        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BARBADOS_DOLLAR   |   Barbados Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UGANDAN_SHILLING   |   Ugandan Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHINESE_YUAN   |   Chinese Yuan        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DOMINCAN_PESO   |   Domincan Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ETHIOPIAN_BIRR   |   Ethiopian Birr        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AZERBAIJANI_MANAT   |   Azerbaijani Manat        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TANZANIAN_SHILLING   |   Tanzanian Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_SUDANESE_POUNT   |   South Sudanese Pount        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOMALI_SHILLING   |   Somali Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUANESE_DOLLAR   |   Guanese Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HONG_KONG_DOLLAR   |   Hong Kong Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SIERRA_LEONEAN_LEONE   |   Sierra Leonean Leone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INDOSEIAN_RUPIAH   |   Indoseian Rupiah        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOLDOVAN_LEU   |   Moldovan Leu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BANGLADESHI_TAKA   |   Bangladeshi Taka        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BOLIVIANO   |   Boliviano        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARMENIAN_DRAM   |   Armenian Dram        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFP_FRANC   |   Cfp Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FIJI_DOLLAR   |   Fiji Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HUNGARIAN_FORINT   |   Hungarian Forint        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INDIAN_RUPEE   |   Indian Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LEBANEESE_POUNT   |   Lebaneese Pount        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LESHTHO_LOTI   |   Leshtho Loti        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PAPUA_NEW_GUINEAN_KINA   |   Papua New Guinean Kina        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MEXICAN_PESO   |   Mexican Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUINEA_BISSAU_PESO   |   Guinea Bissau Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_TAIWAN_DOLLAR   |   New Taiwan Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TURKISH_LIRA   |   Turkish Lira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ANGOLAN_KWANZA   |   Angolan Kwanza        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EURO   |   Euro        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAMBODIAN_FRANC   |   Cambodian Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LIBERIAN_DOLLAR   |   Liberian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UKRANIAN_HRYVNIA   |   Ukranian Hryvnia        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAYMAN_ISLANDS_DOLLAR   |   Cayman Islands Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAURITANIAN_OUGUIYA   |   Mauritanian Ouguiya        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KENYAN_SHILLING   |   Kenyan Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWEDISH_KRONA   |   Swedish Krona        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BULGARIAN_LEV   |   Bulgarian Lev        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GEORGIAN_LARI   |   Georgian Lari        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    THAI_BAHT   |   Thai Baht        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VANUATU_VATU   |   Vanuatu Vatu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SERBIAN_DINAR   |   Serbian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BERMUDIAN_DOLLAR   |   Bermudian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    URUGUAYAN_PESO   |   Uruguayan Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DANISH_KRONE   |   Danish Krone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LIBYAN_DINAR   |   Libyan Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VIETNAMESE_DONG   |   Vietnamese Dong        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ERITREAN_NAFKA   |   Eritrean Nafka        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NIGERIAN_NAIRA   |   Nigerian Naira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MACEDONIAN_DENAR   |   Macedonian Denar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHILEAN_PESO   |   Chilean Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KAZAKHSTANI_TENGE   |   Kazakhstani Tenge        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BAHRANI_DINAR   |   Bahrani Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EL_SALVADORE_COLON   |   El Salvadore Colon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    POLISH_ZLOTY   |   Polish Zloty        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZAMBIAN_KWACHA   |   Zambian Kwacha        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MACANESE_PATACA   |   Macanese Pataca        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BOTSWANA_PULA   |   Botswana Pula        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TONGAN_PAANGA   |   Tongan Paanga        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_AFRICAN_RAND   |   South African Rand        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MYANMAR_KYAT   |   Myanmar Kyat        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COSTA_RICAN_COLON   |   Costa Rican Colon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GHANAIAN_CEDI   |   Ghanaian Cedi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOLOMON_ISLANDS_DOLLAR   |   Solomon Islands Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOZQAMBICAN_METICAL   |   Mozqambican Metical        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAGASY_ARIARY   |   Malagasy Ariary        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JORDANIAN_DINAR   |   Jordanian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWAZI_LILANGENI   |   Swazi Lilangeni        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CZECH_KORUNA   |   Czech Koruna        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWISS_FRANC   |   Swiss Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    RWANDA_FRANC   |   Rwanda Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_RUBLE   |   New Ruble        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PAKASTANI_RUPEE   |   Pakastani Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SRI_LANKA_RUPEE   |   Sri Lanka Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HAITIAN_GOURDE   |   Haitian Gourde        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ICELANDIC_KRONA   |   Icelandic Krona        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GAMBIAN_DALASI   |   Gambian Dalasi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAPE_VERDE_ESCUDO   |   Cape Verde Escudo        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BELIZE_DOLLAR   |   Belize Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    IRAQI_DINAR   |   Iraqi Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TAJIKISTANI_SOMONI   |   Tajikistani Somoni        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ROMANIAN_LEU   |   Romanian Leu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BELARUSSIAN_RUBLE   |   Belarussian Ruble        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BRAZILIAN_REAL   |   Brazilian Real        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VENEZLA_BOLIVAR_SOBERANO   |   Venezla Bolivar Soberano        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PHILIPPINE_PESO   |   Philippine Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    OMANI_RIAL   |   Omani Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUATEMALAN_QUETZAL   |   Guatemalan Quetzal        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALDIVIAN_RUFIYAA   |   Maldivian Rufiyaa        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EAST_CARIBBEAN_DOLLAR   |   East Caribbean Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SURINAMESE_DOLLAR   |   Surinamese Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFA_FRANC_BCEAO   |   Cfa Franc Bceao        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CONVERTIBLE_MARK   |   Convertible Mark        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NTHLNDS_ANTILIES_GUILDER   |   Nthlnds Antilies Guilder        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NAMIBIAN_DOLLAR   |   Namibian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ALGERIAN_DINAR   |   Algerian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UZBEKISTAN_SUM   |   Uzbekistan Sum        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAO_TOME_PRINCIPE_DOBRA   |   Sao Tome Principe Dobra        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GIBRALTAR_POUND   |   Gibraltar Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    OFFSHORE_REMNIBI   |   Offshore Remnibi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BHUTANESE_NGULTRUM   |   Bhutanese Ngultrum        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BAHAMIAN_DOLLAR   |   Bahamian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AUSTRALIAN_DOLLAR   |   Australian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ESTONIAN_KROON   |   Estonian Kroon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AFGHAN_AFGHANI   |   Afghan Afghani        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FALKLAND_ISLAND_POUND   |   Falkland Island Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MONGOLIAN_TOGROG   |   Mongolian Togrog        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TUNISIAN_DINAR   |   Tunisian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SEYCHELLES_RUPEE   |   Seychelles Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TRINADAD_+_TOBAGO_DOLLAR   |   Trinadad + Tobago Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARGENTINIAN_PESO   |   Argentinian Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PANAMANIAN_BALBOA   |   Panamanian Balboa        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_ZEALAND_DOLLAR   |   New Zealand Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COLOMBIAN_PESO   |   Colombian Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAMOAN_TALA   |   Samoan Tala        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EGYPTIAN_POUND   |   Egyptian Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HONDURAN_LEMPIRA   |   Honduran Lempira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEPALESE_RUPEE   |   Nepalese Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UNT_ARAB_EMERATES_DIRHAM   |   Unt Arab Emerates Dirham        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAUDI_RIYAL   |   Saudi Riyal        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TURKMENISTANI_MANAT   |   Turkmenistani Manat        |    Available     | Required     | Allowed |    NA |    
| fundingDailyOverrideDate| Funding Daily Override Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingDailyOverrideIndicator| Funding Override Indicator        |    OVERRIDE   |   Override        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NOT_OVERRIDE   |   Not Override        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
| fundingExclude30DayLimitAmount| Merchant funding exclusion monthly sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingExcludeCode| Merchant funding exclusion code        |    DIVERT   |   Divert        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| fundingExcludeDailyLimitAmount| Merchant funding exclusion daily sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingMethodCode| Funding method code Code determining how funds will be settled        |    CHK_TO_MAIN_BLK_LVL   |   Chk To Main Blk Lvl        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_CHAIN_AUTO_NEG   |   Bnkwire Chain Auto Neg        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SPLIT_OUTLET_BNKWIRE_ACH   |   Split Outlet Bnkwire Ach        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_BANK   |   Ach Bank        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AGENT_BANK_SPLIT_FUNDING   |   Agent Bank Split Funding        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_MER_BLK_CHAIN   |   Ach Mer Blk Chain        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SPLIT_CHAIN_BNKWIRE_ACH   |   Split Chain Bnkwire Ach        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_AGENT_AUTO_NEG   |   Bnkwire Agent Auto Neg        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_OUTLET   |   Bnkwire Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_BANK   |   Bnkwire Bank        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_OUTLET   |   Ach Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BY_CHK_TO_OUTLET   |   By Chk To Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_MER_BLK_CHAIN   |   Bnkwire Mer Blk Chain        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyContactName| Funding notification contact name        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyFaxNumber| Funding notification contact name        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyIndicator| Funding notification indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyMethodCode| Funding notification method code        |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TELEPHONE   |   Telephone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAIL   |   Mail        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EMAIL   |   Email        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FAX   |   Fax        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyPhoneNumber| Funding notification phone number        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingRollupCode| Indicates how the funding transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VIA_CATGRY   |   Via Catgry        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| fundingRppChangeDate| Merchant funding revolving payment plan change date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingRppDelayDays| Revolving payment plan delay days        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppMinimumAmount| Revolving payment plan minimum dollar amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppMinimumReserveAmount| Revolving payment plan minimum reserve amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppPercent| Revolving payment plan percent        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRunCode| Merchant Funding Run        |    FUNDING_RUN6   |   Funding Run6        |    Available     | Required     | Allowed |    NA |    
|                     |                       |    FUNDING_RUNS   |   Funding Runs        |    Available     | Required     | Allowed |    NA |    
|                     |                       |    FUNDING_RUN1   |   Funding Run1        |    Available     | Required     | Allowed |    NA |    
|                     |                       |   FUNDING_RUN2    |   Funding Run2        |    Available     | Required     | Allowed |    NA |    
|                     |                       |   FUNDING_RUN3    |   Funding Run3        |    Available     | Required     | Allowed |    NA |    
|                     |                       |    FUNDING_RUN4   |   Funding Run4        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
|                     |                                            |   2 - Bank Sequence Number#2     |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |  
|                     |                                            |   3 - Bank Sequence Number#3     |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |  
|                     |                                            |   4 - Bank Sequence Number#4     |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |  
|                     |                                            |   5 - Bank Sequence Number#5     |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |  
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5   |   1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator| PTS Limits Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator| PTS Limits Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| reversalsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                            |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA | 
|                            |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA | 
| reversalsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| reversalsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| reversalsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| settleTimeframeCode| Settlement Timeframe Code        |    BACS_SUPER   |   Bacs Super        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BACS_OR_NA   |   Bacs Or Na        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FASTER_PYMNT_METHOD   |   Faster Pymnt Method        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TWO_DAY_HOLD   |   Two Day Hold        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZERO_DAY_HOLD   |   Zero Day Hold        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ONE_DAY_HOLD   |   One Day Hold        |    Available     | Required     | Allowed |    NA |    
| temporary30DayLimitAmount| Temporary monthly limit amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| temporaryDailyLimitAmount| Temporary Daily Limit Amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| temporaryFromDate| Temporary From Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| temporaryToDate| Temporary To Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    COMPLETED   |   Completed        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
| achSuspenseHoldIndicator| ACH suspense hold indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|       |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| achSuspenseReleaseIndicator| ACH suspense release indicator        |    DIVERT_TO_CARS   |   Divert To Cars        |    Available     | Required     | Allowed |    NA |    
|       |                       |    HOLD_30_DAYS   |   Hold 30 Days        |    Available     | Required     | Allowed |    NA |    
|       |                       |    RELEASE_FUNDING   |   Release Funding        |    Available     | Required     | Allowed |    NA |    
| agentBankSplitIndicator| Indicates if Bank Client is considered an agent relationship to FDCS        |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|       |                       |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
| bankwireBbkText| Bankwire beneficiary BBK Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| bankwireBnfText| Bankwire beneficiary BNF Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| bankwireObiText| Bankwire beneficiary OBI Text        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| chargebacksBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                              |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                               |                              |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| chargebacksFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| convenienceFeeCode| Convenience fee code to indicate the ABA or DDA to be charged        |    ABA_DDA_3   |   Aba Dda 3        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_5   |   Aba Dda 5        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    None   |   None        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_2   |   Aba Dda 2        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_1   |   Aba Dda 1        |    Available     | Required     | Allowed |    NA |    
|                             |                                                                         |    ABA_DDA_4   |   Aba Dda 4        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5   |   1 - Bank Sequence Number#1
|                              |                              |    2 - Bank Sequence Number#2
|                              |                              |    3 - Bank Sequence Number#3
|                              |                              |    4 - Bank Sequence Number#4
|                              |                              |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| depositsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
|                           |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                           |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| depositsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| depositsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| depositsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                          |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| discountsBankSequenceNumber| Funding Bank Sequence        |  1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
|                            |                              |  2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |
|                            |                              |  3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                            |                              |  4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |   
|                            |                              |  5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5         |    Available     | Required     | Allowed |    NA |   
| discountsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                             |                              |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| discountsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                           |                            |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| discountsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                           |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| feesBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |
|                       |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |
|                       |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                       |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |
|                       |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |
| feesFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| feesFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                      |                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| feesFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                      |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    2 - Bank Sequence Number#2        |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    3 - Bank Sequence Number#3        |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    4 - Bank Sequence Number#4        |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                      |                                               |    5 - Bank Sequence Number#5        |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| funding30DayOverrideDate| Funding 30 day daily override date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| funding30DayOverrideIndicator| Funding 30 day override indicator        |    NOT_OVERRIDE   |   Not Override        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    OVERRIDE   |   Override        |    Available     | Required     | Allowed |    NA |    
|                                            |                                  |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
| fundingAchDelayDays| Retention period for deposits and daily discount before releasing them for ACH processing        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingBankCode| Funding Bank Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fundingCurrencyCode| Funding Currency Code        |    QATARI_RIAL   |   Qatari Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ISRAELI_NEW_SHEKEL   |   Israeli New Shekel        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFA_FRANC_BEAC   |   Cfa Franc Beac        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UNITED_STATES_DOLLAR   |   United States Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CONGOLESE_FRANC   |   Congolese Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAYSIAN_RINGGIT   |   Malaysian Ringgit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAURITIAN_RUPEE   |   Mauritian Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOROCCAN_DIRHAM   |   Moroccan Dirham        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARUBAN_FLORIN   |   Aruban Florin        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PERUVIAN_SOL   |   Peruvian Sol        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ST_HELENA_POUND   |   St Helena Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BURUNDI_FRANC   |   Burundi Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BRUNEI_DOLLAR   |   Brunei Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COMOROS_FRANC   |   Comoros Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LAO_KIP   |   Lao Kip        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JAMAICAN_DOLLAR   |   Jamaican Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JAPANESE_YEN   |   Japanese Yen        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_KOREAN_WON   |   South Korean Won        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KUWAITI_DINAR   |   Kuwaiti Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NICARAGUAN_CORDOBA   |   Nicaraguan Cordoba        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PARAGUAYAN_GUARANI   |   Paraguayan Guarani        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KYRGYZSTAN_SOM   |   Kyrgyzstan Som        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUINEAN_FRANC   |   Guinean Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    POUND_STERLING   |   Pound Sterling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SINGAPORE_DOLLAR   |   Singapore Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DJIBOUTIAN_FRANC   |   Djiboutian Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CROTIAN_KUNA   |   Crotian Kuna        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    YEMENI_RIAL   |   Yemeni Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAWIAN_KWACHA   |   Malawian Kwacha        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZIMBABWE_DOLLAR   |   Zimbabwe Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NORWEGIAN_KRONE   |   Norwegian Krone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ALBANIAN_LEK   |   Albanian Lek        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BARBADOS_DOLLAR   |   Barbados Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UGANDAN_SHILLING   |   Ugandan Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHINESE_YUAN   |   Chinese Yuan        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DOMINCAN_PESO   |   Domincan Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ETHIOPIAN_BIRR   |   Ethiopian Birr        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AZERBAIJANI_MANAT   |   Azerbaijani Manat        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TANZANIAN_SHILLING   |   Tanzanian Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_SUDANESE_POUNT   |   South Sudanese Pount        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOMALI_SHILLING   |   Somali Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUANESE_DOLLAR   |   Guanese Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HONG_KONG_DOLLAR   |   Hong Kong Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SIERRA_LEONEAN_LEONE   |   Sierra Leonean Leone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INDOSEIAN_RUPIAH   |   Indoseian Rupiah        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOLDOVAN_LEU   |   Moldovan Leu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BANGLADESHI_TAKA   |   Bangladeshi Taka        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BOLIVIANO   |   Boliviano        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARMENIAN_DRAM   |   Armenian Dram        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFP_FRANC   |   Cfp Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FIJI_DOLLAR   |   Fiji Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HUNGARIAN_FORINT   |   Hungarian Forint        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INDIAN_RUPEE   |   Indian Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LEBANEESE_POUNT   |   Lebaneese Pount        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LESHTHO_LOTI   |   Leshtho Loti        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PAPUA_NEW_GUINEAN_KINA   |   Papua New Guinean Kina        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MEXICAN_PESO   |   Mexican Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUINEA_BISSAU_PESO   |   Guinea Bissau Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_TAIWAN_DOLLAR   |   New Taiwan Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TURKISH_LIRA   |   Turkish Lira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ANGOLAN_KWANZA   |   Angolan Kwanza        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EURO   |   Euro        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAMBODIAN_FRANC   |   Cambodian Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LIBERIAN_DOLLAR   |   Liberian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UKRANIAN_HRYVNIA   |   Ukranian Hryvnia        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAYMAN_ISLANDS_DOLLAR   |   Cayman Islands Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAURITANIAN_OUGUIYA   |   Mauritanian Ouguiya        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KENYAN_SHILLING   |   Kenyan Shilling        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWEDISH_KRONA   |   Swedish Krona        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BULGARIAN_LEV   |   Bulgarian Lev        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GEORGIAN_LARI   |   Georgian Lari        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    THAI_BAHT   |   Thai Baht        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VANUATU_VATU   |   Vanuatu Vatu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SERBIAN_DINAR   |   Serbian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BERMUDIAN_DOLLAR   |   Bermudian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    URUGUAYAN_PESO   |   Uruguayan Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DANISH_KRONE   |   Danish Krone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    LIBYAN_DINAR   |   Libyan Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VIETNAMESE_DONG   |   Vietnamese Dong        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ERITREAN_NAFKA   |   Eritrean Nafka        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NIGERIAN_NAIRA   |   Nigerian Naira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MACEDONIAN_DENAR   |   Macedonian Denar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHILEAN_PESO   |   Chilean Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    KAZAKHSTANI_TENGE   |   Kazakhstani Tenge        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BAHRANI_DINAR   |   Bahrani Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EL_SALVADORE_COLON   |   El Salvadore Colon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    POLISH_ZLOTY   |   Polish Zloty        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZAMBIAN_KWACHA   |   Zambian Kwacha        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MACANESE_PATACA   |   Macanese Pataca        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BOTSWANA_PULA   |   Botswana Pula        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TONGAN_PAANGA   |   Tongan Paanga        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOUTH_AFRICAN_RAND   |   South African Rand        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MYANMAR_KYAT   |   Myanmar Kyat        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COSTA_RICAN_COLON   |   Costa Rican Colon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GHANAIAN_CEDI   |   Ghanaian Cedi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SOLOMON_ISLANDS_DOLLAR   |   Solomon Islands Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MOZQAMBICAN_METICAL   |   Mozqambican Metical        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALAGASY_ARIARY   |   Malagasy Ariary        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    JORDANIAN_DINAR   |   Jordanian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWAZI_LILANGENI   |   Swazi Lilangeni        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CZECH_KORUNA   |   Czech Koruna        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SWISS_FRANC   |   Swiss Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    RWANDA_FRANC   |   Rwanda Franc        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_RUBLE   |   New Ruble        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PAKASTANI_RUPEE   |   Pakastani Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SRI_LANKA_RUPEE   |   Sri Lanka Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HAITIAN_GOURDE   |   Haitian Gourde        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ICELANDIC_KRONA   |   Icelandic Krona        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GAMBIAN_DALASI   |   Gambian Dalasi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CAPE_VERDE_ESCUDO   |   Cape Verde Escudo        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BELIZE_DOLLAR   |   Belize Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    IRAQI_DINAR   |   Iraqi Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TAJIKISTANI_SOMONI   |   Tajikistani Somoni        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ROMANIAN_LEU   |   Romanian Leu        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BELARUSSIAN_RUBLE   |   Belarussian Ruble        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BRAZILIAN_REAL   |   Brazilian Real        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VENEZLA_BOLIVAR_SOBERANO   |   Venezla Bolivar Soberano        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PHILIPPINE_PESO   |   Philippine Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    OMANI_RIAL   |   Omani Rial        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GUATEMALAN_QUETZAL   |   Guatemalan Quetzal        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MALDIVIAN_RUFIYAA   |   Maldivian Rufiyaa        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EAST_CARIBBEAN_DOLLAR   |   East Caribbean Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SURINAMESE_DOLLAR   |   Surinamese Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CFA_FRANC_BCEAO   |   Cfa Franc Bceao        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CONVERTIBLE_MARK   |   Convertible Mark        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NTHLNDS_ANTILIES_GUILDER   |   Nthlnds Antilies Guilder        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NAMIBIAN_DOLLAR   |   Namibian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ALGERIAN_DINAR   |   Algerian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UZBEKISTAN_SUM   |   Uzbekistan Sum        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAO_TOME_PRINCIPE_DOBRA   |   Sao Tome Principe Dobra        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    GIBRALTAR_POUND   |   Gibraltar Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    OFFSHORE_REMNIBI   |   Offshore Remnibi        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BHUTANESE_NGULTRUM   |   Bhutanese Ngultrum        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BAHAMIAN_DOLLAR   |   Bahamian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AUSTRALIAN_DOLLAR   |   Australian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ESTONIAN_KROON   |   Estonian Kroon        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AFGHAN_AFGHANI   |   Afghan Afghani        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FALKLAND_ISLAND_POUND   |   Falkland Island Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MONGOLIAN_TOGROG   |   Mongolian Togrog        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TUNISIAN_DINAR   |   Tunisian Dinar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SEYCHELLES_RUPEE   |   Seychelles Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TRINADAD_+_TOBAGO_DOLLAR   |   Trinadad + Tobago Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ARGENTINIAN_PESO   |   Argentinian Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    PANAMANIAN_BALBOA   |   Panamanian Balboa        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEW_ZEALAND_DOLLAR   |   New Zealand Dollar        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    COLOMBIAN_PESO   |   Colombian Peso        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAMOAN_TALA   |   Samoan Tala        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EGYPTIAN_POUND   |   Egyptian Pound        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    HONDURAN_LEMPIRA   |   Honduran Lempira        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NEPALESE_RUPEE   |   Nepalese Rupee        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    UNT_ARAB_EMERATES_DIRHAM   |   Unt Arab Emerates Dirham        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SAUDI_RIYAL   |   Saudi Riyal        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TURKMENISTANI_MANAT   |   Turkmenistani Manat        |    Available     | Required     | Allowed |    NA |    
| fundingDailyOverrideDate| Funding Daily Override Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingDailyOverrideIndicator| Funding Override Indicator        |    OVERRIDE   |   Override        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NOT_OVERRIDE   |   Not Override        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
| fundingExclude30DayLimitAmount| Merchant funding exclusion monthly sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingExcludeCode| Merchant funding exclusion code        |    DIVERT   |   Divert        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| fundingExcludeDailyLimitAmount| Merchant funding exclusion daily sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingMethodCode| Funding method code Code determining how funds will be settled        |    CHK_TO_MAIN_BLK_LVL   |   Chk To Main Blk Lvl        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_CHAIN_AUTO_NEG   |   Bnkwire Chain Auto Neg        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SPLIT_OUTLET_BNKWIRE_ACH   |   Split Outlet Bnkwire Ach        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_BANK   |   Ach Bank        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    AGENT_BANK_SPLIT_FUNDING   |   Agent Bank Split Funding        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_MER_BLK_CHAIN   |   Ach Mer Blk Chain        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    SPLIT_CHAIN_BNKWIRE_ACH   |   Split Chain Bnkwire Ach        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_AGENT_AUTO_NEG   |   Bnkwire Agent Auto Neg        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_OUTLET   |   Bnkwire Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_BANK   |   Bnkwire Bank        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ACH_OUTLET   |   Ach Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BY_CHK_TO_OUTLET   |   By Chk To Outlet        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BNKWIRE_MER_BLK_CHAIN   |   Bnkwire Mer Blk Chain        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyContactName| Funding notification contact name        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyFaxNumber| Funding notification contact name        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyIndicator| Funding notification indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyMethodCode| Funding notification method code        |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TELEPHONE   |   Telephone        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    MAIL   |   Mail        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EMAIL   |   Email        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FAX   |   Fax        |    Available     | Required     | Allowed |    NA |    
| fundingNotifyPhoneNumber| Funding notification phone number        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingRollupCode| Indicates how the funding transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    VIA_CATGRY   |   Via Catgry        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| fundingRppChangeDate| Merchant funding revolving payment plan change date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| fundingRppDelayDays| Revolving payment plan delay days        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppMinimumAmount| Revolving payment plan minimum dollar amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppMinimumReserveAmount| Revolving payment plan minimum reserve amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRppPercent| Revolving payment plan percent        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| fundingRunCode| Merchant Funding Run        |    FUNDING_RUN6   |   Funding Run6        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |   Funding Runs        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |   Funding Run4        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |   Funding Run1        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |   Funding Run2        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |   Funding Run3        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5   |   1 - Bank Sequence Number#1
2 - Bank Sequence Number#2
3 - Bank Sequence Number#3
4 - Bank Sequence Number#4
5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator| PTS Limits Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator| PTS Limits Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| reversalsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    2 - Bank Sequence Number#2   |   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                            |                              |    3 - Bank Sequence Number#3   |   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |
|                            |                              |    4 - Bank Sequence Number#4   |   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA | 
|                            |                              |    5 - Bank Sequence Number#5   |   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA | 
| reversalsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
| reversalsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| reversalsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
| settleTimeframeCode| Settlement Timeframe Code        |    BACS_SUPER   |   Bacs Super        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    BACS_OR_NA   |   Bacs Or Na        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    FASTER_PYMNT_METHOD   |   Faster Pymnt Method        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    TWO_DAY_HOLD   |   Two Day Hold        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ZERO_DAY_HOLD   |   Zero Day Hold        |    Available     | Required     | Allowed |    NA |    
|                     |                                            |    ONE_DAY_HOLD   |   One Day Hold        |    Available     | Required     | Allowed |    NA |    
| temporary30DayLimitAmount| Temporary monthly limit amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| temporaryDailyLimitAmount| Temporary Daily Limit Amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| temporaryFromDate| Temporary From Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| temporaryToDate| Temporary To Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->
