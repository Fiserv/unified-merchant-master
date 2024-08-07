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
| fmgGroupCode | Fmg Group Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| fmgMarkerBank | Fmg Marker Bank        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Required     | Allowed |    NA |    
| futureUse1 | Future Use 1        |    Available     | Required     | Allowed |    NA |    
| futureUse2 | Future Use 2        |       |           |    Available     | Required     | Allowed |    NA |    
| globalClientDescription | Global Client Description        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
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

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    COMPLETED   |   Completed        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->

### fundingConfig
---
tags: [fundingConfig]
---
- Description: Free Processing
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
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
|                                     |                              |    2 - Bank Sequence Number#2   |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |  
|                                     |                              |    3 - Bank Sequence Number#3   |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                                     |                              |    4 - Bank Sequence Number#4   |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                                     |                              |    5 - Bank Sequence Number#5   |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
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
| depositsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
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
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    2 - Bank Sequence Number#2    |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    3 - Bank Sequence Number#3    |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    4 - Bank Sequence Number#4    |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    5 - Bank Sequence Number#5    |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |  
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
|                                           |                       |  2 - Bank Sequence Number#2|   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |  3 - Bank Sequence Number#3|   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |  
|                                           |                       |  4 - Bank Sequence Number#4|   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |  5 - Bank Sequence Number#5|   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode | Funding Category Code |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator                        | PTS Limits Indicator  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
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
|                                     |                              |    2 - Bank Sequence Number#2   |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |  
|                                     |                              |    3 - Bank Sequence Number#3   |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |    
|                                     |                              |    4 - Bank Sequence Number#4   |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                                     |                              |    5 - Bank Sequence Number#5   |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
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
| depositsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
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
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    2 - Bank Sequence Number#2    |    2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    3 - Bank Sequence Number#3    |    3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    4 - Bank Sequence Number#4    |    4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |   
|                                         |                              |    5 - Bank Sequence Number#5    |    5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |  
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence        |    1 - Bank Sequence Number#1   |   1 - Bank Sequence Number#1
|                                           |                       |  2 - Bank Sequence Number#2|   2 - Bank Sequence Number#2        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |  3 - Bank Sequence Number#3|   3 - Bank Sequence Number#3        |    Available     | Required     | Allowed |    NA |  
|                                           |                       |  4 - Bank Sequence Number#4|   4 - Bank Sequence Number#4        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |  5 - Bank Sequence Number#5|   5 - Bank Sequence Number#5        |    Available     | Required     | Allowed |    NA |    
| nonBankcardAdjustmentsFundingCategoryCode | Funding Category Code |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FEES   |   Fees        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CARS   |   Cars        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Required     | Allowed |    NA |    
| ptsLimitsIndicator                        | PTS Limits Indicator  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
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

### globalCurrencySolutions
---
tags: [globalCurrencySolutions]
---
- Description: Global Currency Solutions
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringSubType1| Offering Sub Type        |    NORTH_RATES_PLUS_DCCLUS_DCC   |   North Rates Plus Dcclus Dcc        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EXCEPTION_RATE_MCPE_MCP   |   Exception Rate Mcpe Mcp        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VI/MC_RATE_MCPP   |   Vi/Mc Rate Mcpp        |    Available     | Required     | Allowed |    NA |    
| offeringSubType2| Globally Used For All North Backend Sales Channels        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    PRISMATIC   |   Prismatic        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringSubType1| Offering Sub Type        |    NORTH_RATES_PLUS_DCCLUS_DCC   |   North Rates Plus Dcclus Dcc        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EXCEPTION_RATE_MCPE_MCP   |   Exception Rate Mcpe Mcp        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VI/MC_RATE_MCPP   |   Vi/Mc Rate Mcpp        |    Available     | Required     | Allowed |    NA |    
| offeringSubType2| Globally Used For All North Backend Sales Channels        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    PRISMATIC   |   Prismatic        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
    
<!-- type: tab-end -->

### highRiskMonitoring
---
tags: [highRiskMonitoring]
---
- Description: High Risk Monitoring
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CNP_PHARMACY   |   Cnp Pharmacy        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CNP_TOBACCO_VAPE   |   Cnp Tobacco Vape        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    SOCIAL_GAMING   |   Social Gaming        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ONLINE_FIREARMS   |   Online Firearms        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    SKILLED_GAMES   |   Skilled Games        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    BINGO   |   Bingo        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NFT   |   Nft        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CRYPTOCURRENCY   |   Cryptocurrency        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    HIGH_RISK   |   High Risk        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NUTRACEUTICALS   |   Nutraceuticals        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    LOTTERY   |   Lottery        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    GAMBLING   |   Gambling        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_REQUIRED   |   Not Required        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEREGISTERED   |   Deregistered        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    COMPLETE_REGISTER   |   Complete Register        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    PENDING_REGISTER   |   Pending Register        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CNP_PHARMACY   |   Cnp Pharmacy        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CNP_TOBACCO_VAPE   |   Cnp Tobacco Vape        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    SOCIAL_GAMING   |   Social Gaming        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ONLINE_FIREARMS   |   Online Firearms        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    SKILLED_GAMES   |   Skilled Games        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    BINGO   |   Bingo        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NFT   |   Nft        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CRYPTOCURRENCY   |   Cryptocurrency        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    HIGH_RISK   |   High Risk        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NUTRACEUTICALS   |   Nutraceuticals        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    LOTTERY   |   Lottery        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    GAMBLING   |   Gambling        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_REQUIRED   |   Not Required        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    DEREGISTERED   |   Deregistered        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    COMPLETE_REGISTER   |   Complete Register        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    PENDING_REGISTER   |   Pending Register        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### inHouseAuthConfig
---
tags: [inHouseAuthConfig]
---
- Description: InHouse Auth Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| inHouseAuthCaptureCode| InHouse Authorization Capture Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseBankCode| InHouse Bank Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseNonMerchantCode| InHouse NonMerchant Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
 
<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| inHouseAuthCaptureCode| InHouse Authorization Capture Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseBankCode| InHouse Bank Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseNonMerchantCode| InHouse NonMerchant Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
 
<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### indemnification
---
tags: [indemnification]
---
- Description: Indemnification
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| indemnificationDate| Indemnification Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| indemnificationIndicator| Indemnification Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| indemnificationPercent| Indemnification Risk Ratio Percentage        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| riskOwnerCode| Risk Owner Code        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ALLIANCE   |   Alliance        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| indemnificationDate| Indemnification Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| indemnificationIndicator| Indemnification Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| indemnificationPercent| Indemnification Risk Ratio Percentage        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| riskOwnerCode| Risk Owner Code        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    BANK   |   Bank        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    AGENT   |   Agent        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ALLIANCE   |   Alliance        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### independentSoftwareVendor
---
tags: [independentSoftwareVendor]
---
- Description: Independent Software Vendor (Isv) Global Indicator
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    BYPASS_CLOVER_ISV   |   Bypass Clover Isv        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    BYPASS_CLOVER_ISV   |   Bypass Clover Isv        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### internalItUse
---
tags: [internalItUse]
---
- Description: Internal It Use - Trigger Feeds And Save Data
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| discoverTrigger| Registration Merchant Feed To Discover        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| spomiTrigger| Sponsored Merchant Feed To Amex        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REPROCESS   |   Reprocess        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| discoverTrigger| Registration Merchant Feed To Discover        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| spomiTrigger| Sponsored Merchant Feed To Amex        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REPROCESS   |   Reprocess        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### iolCanadianVatRegNumber
---
tags: [iolCanadianVatRegNumber]
---
- Description: Iol Canadian Vat Reg Number
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| canadianVatRegNumber| Canadian Vat Registration Number        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| canadianVatRegNumber| Canadian Vat Registration Number        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### irsSupplementalInformation
---
tags: [irsSupplementalInformation]
---
- Description: Irs Supplemental Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| econsentDate| Econsent Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| econsentIndicator| Econsent Indicator        |    OWNERSHIP_CHANGE   |   Ownership Change        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ECONSENT_GIVEN   |   Econsent Given        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ECONSENT_REVOKED   |   Econsent Revoked        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    PENDING_STATUS   |   Pending Status        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EMAIL_DELIVERY_FAILED   |   Email Delivery Failed        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    STATUS_CHANGE   |   Status Change        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ONLY_EMAIL_ACTIVATED   |   Only Email Activated        |    Available     | Required     | Allowed |    NA |    
| primaryEmailIndicator| Primary Email Indicator        |    USE_ALTERNATE_EMAIL   |   Use Alternate Email        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    USE_PRIMARY_EMAIL   |   Use Primary Email        |    Available     | Required     | Allowed |    NA |    
| requestGuid| Request Guid        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| userProvidedEconsentEmail| User Provided Econsent Email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| econsentDate| Econsent Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| econsentIndicator| Econsent Indicator        |    OWNERSHIP_CHANGE   |   Ownership Change        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ECONSENT_GIVEN   |   Econsent Given        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ECONSENT_REVOKED   |   Econsent Revoked        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    PENDING_STATUS   |   Pending Status        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EMAIL_DELIVERY_FAILED   |   Email Delivery Failed        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    STATUS_CHANGE   |   Status Change        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    ONLY_EMAIL_ACTIVATED   |   Only Email Activated        |    Available     | Required     | Allowed |    NA |    
| primaryEmailIndicator| Primary Email Indicator        |    USE_ALTERNATE_EMAIL   |   Use Alternate Email        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    USE_PRIMARY_EMAIL   |   Use Primary Email        |    Available     | Required     | Allowed |    NA |    
| requestGuid| Request Guid        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| userProvidedEconsentEmail| User Provided Econsent Email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### isoServices
---
tags: [isoServices]
---
- Description: Iso Services
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| isoIdAmex| Iso Id Amex        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdDscv| Iso Id Discover        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdMc| Iso Id Mc        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdVi| Iso Id Vi        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| serviceProvider| Service Provider        |    APERIA   |   Aperia        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    WELLS   |   Wells        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    MARKETPLACE   |   Marketplace        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FD_DIRECT   |   Fd Direct        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| isoIdAmex| Iso Id Amex        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdDscv| Iso Id Discover        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdMc| Iso Id Mc        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| isoIdVi| Iso Id Vi        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| serviceProvider| Service Provider        |    APERIA   |   Aperia        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    WELLS   |   Wells        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    MARKETPLACE   |   Marketplace        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    FD_DIRECT   |   Fd Direct        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### keyReferenceNumber
---
tags: [keyReferenceNumber]
---
- Description: Key Reference Number
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| keyReferenceNumber| Credit Only Key Reference Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| tbd| Tbd        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| keyReferenceNumber| Credit Only Key Reference Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| tbd| Tbd        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

### merchantCountryOfOrigin

---
tags: [merchantCountryOfOrigin]
---
- Description: Merchant Country Of Origin
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| countryOfOrigin| Country Of Origin        |    GMB   |   Gmb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UZB   |   Uzb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WLF   |   Wlf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WSM   |   Wsm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRV   |   Hrv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GLP   |   Glp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HKG   |   Hkg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HTI   |   Hti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GAB   |   Gab        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLV   |   Slv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MYT   |   Myt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HMD   |   Hmd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GHA   |   Gha        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KIR   |   Kir        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DEU   |   Deu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSE   |   Pse        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GGY   |   Ggy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SRB   |   Srb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SGS   |   Sgs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CIV   |   Civ        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CXR   |   Cxr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHL   |   Chl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TCD   |   Tcd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LKA   |   Lka        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAN   |   Can        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COM   |   Com        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLR   |   Blr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DMA   |   Dma        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATA   |   Ata        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAR   |   Zar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TWN   |   Twn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLK   |   Flk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ECU   |   Ecu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IMN   |   Imn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TZA   |   Tza        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBR   |   Lbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IOT   |   Iot        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRA   |   Bra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BTN   |   Btn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BEL   |   Bel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AZE   |   Aze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AGO   |   Ago        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ASM   |   Asm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DZA   |   Dza        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRO   |   Fro        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NLD   |   Nld        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AFG   |   Afg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHN   |   Chn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FIN   |   Fin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRA   |   Fra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LTU   |   Ltu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CMR   |   Cmr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBN   |   Lbn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JOR   |   Jor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUT   |   Aut        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KAZ   |   Kaz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KGZ   |   Kgz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TKL   |   Tkl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUN   |   Tun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TKM   |   Tkm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TCA   |   Tca        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MKD   |   Mkd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALA   |   Ala        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRI   |   Pri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAM   |   Nam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NRU   |   Nru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TJK   |   Tjk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GNB   |   Gnb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOM   |   Som        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RWA   |   Rwa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SHN   |   Shn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KNA   |   Kna        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPM   |   Spm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    POL   |   Pol        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAN   |   Pan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMR   |   Smr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEN   |   Sen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBY   |   Lby        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MCO   |   Mco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNE   |   Mne        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VAT   |   Vat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLE   |   Sle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAR   |   Mar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IDN   |   Idn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRL   |   Irl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISR   |   Isr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ITA   |   Ita        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KEN   |   Ken        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOR   |   Kor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KWT   |   Kwt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LSO   |   Lso        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVN   |   Svn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VNM   |   Vnm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TGO   |   Tgo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TTO   |   Tto        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RUS   |   Rus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAF   |   Caf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UKR   |   Ukr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZWE   |   Zwe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUR   |   Sur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUR   |   Tur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLM   |   Blm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAF   |   Maf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VCT   |   Vct        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAU   |   Sau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SGP   |   Sgp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVK   |   Svk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAF   |   Zaf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRB   |   Brb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TON   |   Ton        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SYC   |   Syc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GBR   |   Gbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUV   |   Tuv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SJM   |   Sjm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EGY   |   Egy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JEY   |   Jey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIR   |   Vir        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BFA   |   Bfa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIC   |   Nic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PNG   |   Png        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARE   |   Are        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VUT   |   Vut        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAC   |   Mac        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MLT   |   Mlt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIN   |   Gin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAM   |   Jam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JPN   |   Jpn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ABW   |   Abw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UMI   |   Umi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NER   |   Ner        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIU   |   Niu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NFK   |   Nfk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNP   |   Mnp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FSM   |   Fsm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAK   |   Pak        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PHL   |   Phl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QAT   |   Qat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ROU   |   Rou        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MUS   |   Mus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IND   |   Ind        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRQ   |   Irq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SXM   |   Sxm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PCN   |   Pcn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LAO   |   Lao        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LVA   |   Lva        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIE   |   Lie        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDG   |   Mdg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MYS   |   Mys        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDV   |   Mdv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUM   |   Gum        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDA   |   Mda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSR   |   Msr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OMN   |   Omn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NPL   |   Npl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANT   |   Ant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUW   |   Cuw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOR   |   Nor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MHL   |   Mhl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COG   |   Cog        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRD   |   Grd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUY   |   Guy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HND   |   Hnd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GNQ   |   Gnq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ETH   |   Eth        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ERI   |   Eri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FJI   |   Fji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PYF   |   Pyf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COL   |   Col        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PLW   |   Plw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CRI   |   Cri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EST   |   Est        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DJI   |   Dji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NCL   |   Ncl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GEO   |   Geo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIB   |   Gib        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRC   |   Grc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GTM   |   Gtm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HUN   |   Hun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LUX   |   Lux        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    URY   |   Ury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VEN   |   Ven        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YEM   |   Yem        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZMB   |   Zmb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QZZ   |   Qzz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TMP   |   Tmp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUF   |   Guf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESH   |   Esh        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRY   |   Pry        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PER   |   Per        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BEN   |   Ben        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BGR   |   Bgr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AIA   |   Aia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USA   |   Usa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MWI   |   Mwi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MLI   |   Mli        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTQ   |   Mtq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRT   |   Mrt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MEX   |   Mex        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOZ   |   Moz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BES   |   Bes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NZL   |   Nzl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NGA   |   Nga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOM   |   Dom        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNG   |   Mng        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DNK   |   Dnk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRT   |   Prt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REU   |   Reu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISL   |   Isl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LCA   |   Lca        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STP   |   Stp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESP   |   Esp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SSD   |   Ssd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRL   |   Grl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWZ   |   Swz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWE   |   Swe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHE   |   Che        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THA   |   Tha        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYM   |   Cym        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CCK   |   Cck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUB   |   Cub        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALB   |   Alb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AND   |   And        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATG   |   Atg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUS   |   Aus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHR   |   Bhr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARM   |   Arm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BMU   |   Bmu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BWA   |   Bwa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLZ   |   Blz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLB   |   Slb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KHM   |   Khm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CPV   |   Cpv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATF   |   Atf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UGA   |   Uga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COK   |   Cok        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHS   |   Bhs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYP   |   Cyp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MMR   |   Mmr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BDI   |   Bdi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZE   |   Cze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARG   |   Arg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BGD   |   Bgd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOL   |   Bol        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIH   |   Bih        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BVT   |   Bvt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VGB   |   Vgb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRN   |   Brn        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| countryOfOrigin| Country Of Origin        |    GMB   |   Gmb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UZB   |   Uzb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WLF   |   Wlf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WSM   |   Wsm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRV   |   Hrv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GLP   |   Glp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HKG   |   Hkg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HTI   |   Hti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GAB   |   Gab        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLV   |   Slv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MYT   |   Myt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HMD   |   Hmd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GHA   |   Gha        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KIR   |   Kir        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DEU   |   Deu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSE   |   Pse        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GGY   |   Ggy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SRB   |   Srb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SGS   |   Sgs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CIV   |   Civ        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CXR   |   Cxr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHL   |   Chl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TCD   |   Tcd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LKA   |   Lka        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAN   |   Can        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COM   |   Com        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLR   |   Blr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DMA   |   Dma        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATA   |   Ata        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAR   |   Zar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TWN   |   Twn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLK   |   Flk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ECU   |   Ecu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IMN   |   Imn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TZA   |   Tza        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBR   |   Lbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IOT   |   Iot        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRA   |   Bra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BTN   |   Btn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BEL   |   Bel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AZE   |   Aze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AGO   |   Ago        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ASM   |   Asm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DZA   |   Dza        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRO   |   Fro        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NLD   |   Nld        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AFG   |   Afg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHN   |   Chn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FIN   |   Fin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRA   |   Fra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LTU   |   Ltu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CMR   |   Cmr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBN   |   Lbn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JOR   |   Jor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUT   |   Aut        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KAZ   |   Kaz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KGZ   |   Kgz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TKL   |   Tkl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUN   |   Tun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TKM   |   Tkm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TCA   |   Tca        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MKD   |   Mkd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALA   |   Ala        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRI   |   Pri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAM   |   Nam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NRU   |   Nru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TJK   |   Tjk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GNB   |   Gnb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOM   |   Som        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RWA   |   Rwa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SHN   |   Shn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KNA   |   Kna        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPM   |   Spm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    POL   |   Pol        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAN   |   Pan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMR   |   Smr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEN   |   Sen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LBY   |   Lby        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MCO   |   Mco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNE   |   Mne        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VAT   |   Vat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLE   |   Sle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAR   |   Mar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IDN   |   Idn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRL   |   Irl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISR   |   Isr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ITA   |   Ita        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KEN   |   Ken        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOR   |   Kor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KWT   |   Kwt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LSO   |   Lso        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVN   |   Svn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VNM   |   Vnm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TGO   |   Tgo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TTO   |   Tto        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RUS   |   Rus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAF   |   Caf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UKR   |   Ukr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZWE   |   Zwe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUR   |   Sur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUR   |   Tur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLM   |   Blm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAF   |   Maf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VCT   |   Vct        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAU   |   Sau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SGP   |   Sgp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVK   |   Svk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAF   |   Zaf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRB   |   Brb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TON   |   Ton        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SYC   |   Syc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GBR   |   Gbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUV   |   Tuv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SJM   |   Sjm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EGY   |   Egy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JEY   |   Jey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIR   |   Vir        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BFA   |   Bfa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIC   |   Nic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PNG   |   Png        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARE   |   Are        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VUT   |   Vut        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAC   |   Mac        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MLT   |   Mlt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIN   |   Gin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAM   |   Jam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JPN   |   Jpn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ABW   |   Abw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UMI   |   Umi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NER   |   Ner        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIU   |   Niu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NFK   |   Nfk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNP   |   Mnp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FSM   |   Fsm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAK   |   Pak        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PHL   |   Phl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QAT   |   Qat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ROU   |   Rou        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MUS   |   Mus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IND   |   Ind        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRQ   |   Irq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SXM   |   Sxm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PCN   |   Pcn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LAO   |   Lao        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LVA   |   Lva        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIE   |   Lie        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDG   |   Mdg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MYS   |   Mys        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDV   |   Mdv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUM   |   Gum        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDA   |   Mda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSR   |   Msr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OMN   |   Omn        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NPL   |   Npl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANT   |   Ant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUW   |   Cuw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOR   |   Nor        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MHL   |   Mhl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COG   |   Cog        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRD   |   Grd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUY   |   Guy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HND   |   Hnd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GNQ   |   Gnq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ETH   |   Eth        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ERI   |   Eri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FJI   |   Fji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PYF   |   Pyf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COL   |   Col        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PLW   |   Plw        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CRI   |   Cri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EST   |   Est        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DJI   |   Dji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NCL   |   Ncl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GEO   |   Geo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIB   |   Gib        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRC   |   Grc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GTM   |   Gtm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HUN   |   Hun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LUX   |   Lux        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    URY   |   Ury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VEN   |   Ven        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YEM   |   Yem        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZMB   |   Zmb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QZZ   |   Qzz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TMP   |   Tmp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUF   |   Guf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESH   |   Esh        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRY   |   Pry        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PER   |   Per        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BEN   |   Ben        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BGR   |   Bgr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AIA   |   Aia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USA   |   Usa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MWI   |   Mwi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MLI   |   Mli        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTQ   |   Mtq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRT   |   Mrt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MEX   |   Mex        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOZ   |   Moz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BES   |   Bes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NZL   |   Nzl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NGA   |   Nga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOM   |   Dom        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNG   |   Mng        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DNK   |   Dnk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PRT   |   Prt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REU   |   Reu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISL   |   Isl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LCA   |   Lca        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STP   |   Stp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESP   |   Esp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SSD   |   Ssd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRL   |   Grl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWZ   |   Swz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWE   |   Swe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHE   |   Che        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THA   |   Tha        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYM   |   Cym        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CCK   |   Cck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUB   |   Cub        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALB   |   Alb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AND   |   And        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATG   |   Atg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUS   |   Aus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHR   |   Bhr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARM   |   Arm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BMU   |   Bmu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BWA   |   Bwa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BLZ   |   Blz        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLB   |   Slb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KHM   |   Khm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CPV   |   Cpv        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ATF   |   Atf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UGA   |   Uga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COK   |   Cok        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHS   |   Bhs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYP   |   Cyp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MMR   |   Mmr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BDI   |   Bdi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZE   |   Cze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARG   |   Arg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BGD   |   Bgd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOL   |   Bol        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIH   |   Bih        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BVT   |   Bvt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VGB   |   Vgb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRN   |   Brn        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### merchantFraudAndSecurity

---
tags: [merchantFraudAndSecurity]
---
- Description: Merchant Fraud And Security
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| afdsMerchantAuthBlockStatus| Afds Merchant Auth Block Status        |    AFDS_AUTH_BLOCK   |   Afds Auth Block        |    Available     | Required     | Allowed |    NA |    
|          -                 |                 -                      |    AFDS_AUTH_UNBLOCK   |   Afds Auth Unblock        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| afdsMerchantAuthBlockStatus| Afds Merchant Auth Block Status        |    AFDS_AUTH_BLOCK   |   Afds Auth Block        |    Available     | Required     | Allowed |    NA |    
|          -                 |                 -                      |    AFDS_AUTH_UNBLOCK   |   Afds Auth Unblock        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### merchantFrontEnds

---
tags: [merchantFrontEnds]
---
- Description: Merchant Front Ends
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authNetworkCode1| Name Of The Network        |    WALMART_BEST_PRICE   |   Walmart Best Price        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VITAL   |   Vital        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH   |   South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARDNET   |   Cardnet        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMPASS   |   Compass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASHVILLE   |   Nashville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDI   |   Mdi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPER   |   Paper        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELECHECK   |   Telecheck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FDR   |   Fdr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELEMONEY   |   Telemoney        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAPP   |   Mapp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NDC   |   Ndc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUYPASS   |   Buypass        |    Available     | Required     | Allowed |    NA |    
| authNetworkCode2      | Name Of The Secondary Network        |    NDC   |   Ndc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPER   |   Paper        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMPASS   |   Compass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELECHECK   |   Telecheck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAPP   |   Mapp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FDR   |   Fdr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUYPASS   |   Buypass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELEMONEY   |   Telemoney        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH   |   South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WALMART_BEST_PRICE   |   Walmart Best Price        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASHVILLE   |   Nashville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VITAL   |   Vital        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARDNET   |   Cardnet        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDI   |   Mdi        |    Available     | Required     | Allowed |    NA |    
| authNetworkSecurityCode1| Code Which Can Be Used To Determine The Front End Network        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| authNetworkSecurityCode2| Code which is being used to determine the front end network         |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authNetworkCode1| Name Of The Network        |    WALMART_BEST_PRICE   |   Walmart Best Price        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VITAL   |   Vital        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH   |   South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARDNET   |   Cardnet        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMPASS   |   Compass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASHVILLE   |   Nashville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDI   |   Mdi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPER   |   Paper        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELECHECK   |   Telecheck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FDR   |   Fdr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELEMONEY   |   Telemoney        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAPP   |   Mapp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NDC   |   Ndc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUYPASS   |   Buypass        |    Available     | Required     | Allowed |    NA |    
| authNetworkCode2      | Name Of The Secondary Network        |    NDC   |   Ndc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPER   |   Paper        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMPASS   |   Compass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELECHECK   |   Telecheck        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAPP   |   Mapp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FDR   |   Fdr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUYPASS   |   Buypass        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TELEMONEY   |   Telemoney        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH   |   South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WALMART_BEST_PRICE   |   Walmart Best Price        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASHVILLE   |   Nashville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VITAL   |   Vital        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARDNET   |   Cardnet        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MDI   |   Mdi        |    Available     | Required     | Allowed |    NA |    
| authNetworkSecurityCode1| Code Which Can Be Used To Determine The Front End Network        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| authNetworkSecurityCode2| Code which is being used to determine the front end network         |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### merchantLiteConfig

---
tags: [merchantLiteConfig]
---
- Description: Merchant Lite Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| merchantLiteAuthLimitAmount  | Merchant Lite Auth Limit Amount                   |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteCreditLimitAmount| Merchant Lite Credit Limit Amount                 |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteSalesLimitAmount | Merchant Lite Sales Limit Amount                  |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| merchantLiteAuthLimitAmount  | Merchant Lite Auth Limit Amount                   |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteCreditLimitAmount| Merchant Lite Credit Limit Amount                 |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteSalesLimitAmount | Merchant Lite Sales Limit Amount                  |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### merchantMunicipality

---
tags: [merchantMunicipality]
---
- Description: Merchant Municipality
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| municipalityTaxInd| Municipality Tax Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| municipilatityCode| Municipality Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-->

##### GMA Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| municipalityTaxInd| Municipality Tax Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| municipilatityCode| Municipality Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    



<!-- type: tab-end -->




### merchantPortfolioType

---
tags: [merchantPortfolioType]
---
- Description: Merchant Portfolio Type
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| byTransactionCount| Transaction Count Portfolio Size        |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| byTransactionCount| Transaction Count Portfolio Size        |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### merchantPricingStructure

---
tags: [merchantPricingStructure]
---
- Description: Merchant Pricing Structure
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->




### miniPromoForStationOutage

---
tags: [miniPromoForStationOutage]
---
- Description: Mini Promo For Station Outage
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification


| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!-- type: tab-end -->


### miscReporting

---
tags: [miscReporting]
---
- Description: MISC
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| enhancedReportingIndicator| Enhanced Reporting Indicator        |    ALL_TRANS_FUNDED_CHG_FEE   |   All Trans Funded Chg Fee        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAI2_PINNACLE   |   Bai2 Pinnacle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PINNACLE   |   Pinnacle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCHANT_LOCATION_SUMM_J   |   Merchant Location Summ J        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_REP   |   All Trans Settled Rep        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_CHG_FEE   |   All Trans Settled Chg Fee        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_I   |   All Trans Settled I        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_E   |   Only Trans Funded E        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAI2   |   Bai2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_REP   |   Only Trans Funded Rep        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDI CONF   |   Edi Conf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_AUTOBILLBK_SYS   |   Not Autobillbk Sys        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_F   |   All Trans Settled F        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCHANT_LOCATION_SUMM_G   |   Merchant Location Summ G        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_H   |   Only Trans Funded H        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDI_CONF_PINNACLE   |   Edi Conf Pinnacle        |    Available     | Required     | Allowed |    NA |    
| farsFiscalDate        | Financial Account Reporting System Fiscal Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| farsMediaTypeCode     | Financial Activity Reporting System Media Type Code        |    TAPE_REEL_16100_BPI   |   Tape Reel 16100 Bpi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CATRIDGE_COMP   |   Catridge Comp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARTRIDGE_NON_COMP   |   Cartridge Non Comp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAPE_REEL_3250_BPI   |   Tape Reel 3250 Bpi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|farsReportFrequencyCode| Financial Activity Reporting System Report Frequency Code        |    MNTH_LAST_SAT   |   Mnth Last Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_MON   |   Wkly 1St 3Rd Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_THU   |   Wkly Tue Thu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_SAT   |   Wkly Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_FRI   |   Wkly Wed Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE   |   Wkly Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEMIMNTH_LAST_BUSS_DAY   |   Semimnth Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUN_2ND_LAST_WEEK   |   Sun 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_FRI   |   Wkly Tue Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_SAT   |   Wkly Tue Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUE_2ND_LAST_WEEK   |   Tue 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_TUE   |   Mnth Last Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_WED   |   Mnth Last Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_WED   |   Wkly 1St 3Rd Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QTRLY_LAST_BUSS_DAY   |   Qtrly Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MON_2ND_LAST_WEEK   |   Mon 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DLY   |   Dly        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_TUE   |   Wkly 1St 3Rd Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_SUN   |   Wkly 1St 3Rd Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_FARS_ENTITLED   |   Not Fars Entitled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_THURS   |   Wkly Thurs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_SUN   |   Wkly Wed Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTHLY_LAST_BUSS_DAY   |   Mthly Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    28_DAYS_CYCLE   |   28 Days Cycle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAT_2ND_LAST_WEEK   |   Sat 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_THURS   |   Mnth Last Thurs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTHLY_LAST_CAL_DAY   |   Mthly Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON_TUE   |   Wkly Mon Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QTRLY_LAST_CAL_DAY   |   Qtrly Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_FRI_SUN   |   Wkly Fri Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON   |   Wkly Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    28_35_28_DAYS_CYCLE   |   28 35 28 Days Cycle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRI_2ND_LAST_WEEK   |   Fri 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WED_2ND_LAST_WEEK   |   Wed 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_SUN   |   Mnth Last Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLEX_DAYS   |   Flex Days        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_FRI   |   Wkly 1St 3Rd Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED   |   Wkly Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_MON   |   Mnth Last Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON_WED   |   Wkly Mon Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_SUN   |   Wkly Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEMIMNTH_LAST_CAL_DAY   |   Semimnth Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_SAT   |   Wkly Wed Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_SUN   |   Wkly Tue Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_THU_SUN   |   Wkly Thu Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_SAT   |   Wkly 1St 3Rd Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THU_2ND_LAST_WEEK   |   Thu 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_FRI   |   Mnth Last Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_FRI   |   Wkly Fri        |    Available     | Required     | Allowed |    NA |  

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| enhancedReportingIndicator| Enhanced Reporting Indicator        |    ALL_TRANS_FUNDED_CHG_FEE   |   All Trans Funded Chg Fee        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAI2_PINNACLE   |   Bai2 Pinnacle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PINNACLE   |   Pinnacle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCHANT_LOCATION_SUMM_J   |   Merchant Location Summ J        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_REP   |   All Trans Settled Rep        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_CHG_FEE   |   All Trans Settled Chg Fee        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_I   |   All Trans Settled I        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_E   |   Only Trans Funded E        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAI2   |   Bai2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_REP   |   Only Trans Funded Rep        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDI CONF   |   Edi Conf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_AUTOBILLBK_SYS   |   Not Autobillbk Sys        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TRANS_SETTLED_F   |   All Trans Settled F        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCHANT_LOCATION_SUMM_G   |   Merchant Location Summ G        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLY_TRANS_FUNDED_H   |   Only Trans Funded H        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDI_CONF_PINNACLE   |   Edi Conf Pinnacle        |    Available     | Required     | Allowed |    NA |    
| farsFiscalDate        | Financial Account Reporting System Fiscal Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| farsMediaTypeCode     | Financial Activity Reporting System Media Type Code        |    TAPE_REEL_16100_BPI   |   Tape Reel 16100 Bpi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CATRIDGE_COMP   |   Catridge Comp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CARTRIDGE_NON_COMP   |   Cartridge Non Comp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAPE_REEL_3250_BPI   |   Tape Reel 3250 Bpi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|farsReportFrequencyCode| Financial Activity Reporting System Report Frequency Code        |    MNTH_LAST_SAT   |   Mnth Last Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_MON   |   Wkly 1St 3Rd Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_THU   |   Wkly Tue Thu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_SAT   |   Wkly Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_FRI   |   Wkly Wed Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE   |   Wkly Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEMIMNTH_LAST_BUSS_DAY   |   Semimnth Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUN_2ND_LAST_WEEK   |   Sun 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_FRI   |   Wkly Tue Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_SAT   |   Wkly Tue Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUE_2ND_LAST_WEEK   |   Tue 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_TUE   |   Mnth Last Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_WED   |   Mnth Last Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_WED   |   Wkly 1St 3Rd Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QTRLY_LAST_BUSS_DAY   |   Qtrly Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MON_2ND_LAST_WEEK   |   Mon 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DLY   |   Dly        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_TUE   |   Wkly 1St 3Rd Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_SUN   |   Wkly 1St 3Rd Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_FARS_ENTITLED   |   Not Fars Entitled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_THURS   |   Wkly Thurs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_SUN   |   Wkly Wed Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTHLY_LAST_BUSS_DAY   |   Mthly Last Buss Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    28_DAYS_CYCLE   |   28 Days Cycle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAT_2ND_LAST_WEEK   |   Sat 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_THURS   |   Mnth Last Thurs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MTHLY_LAST_CAL_DAY   |   Mthly Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON_TUE   |   Wkly Mon Tue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QTRLY_LAST_CAL_DAY   |   Qtrly Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_FRI_SUN   |   Wkly Fri Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON   |   Wkly Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    28_35_28_DAYS_CYCLE   |   28 35 28 Days Cycle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRI_2ND_LAST_WEEK   |   Fri 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WED_2ND_LAST_WEEK   |   Wed 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_SUN   |   Mnth Last Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLEX_DAYS   |   Flex Days        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_FRI   |   Wkly 1St 3Rd Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED   |   Wkly Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_MON   |   Mnth Last Mon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_MON_WED   |   Wkly Mon Wed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_SUN   |   Wkly Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEMIMNTH_LAST_CAL_DAY   |   Semimnth Last Cal Day        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_WED_SAT   |   Wkly Wed Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_TUE_SUN   |   Wkly Tue Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_THU_SUN   |   Wkly Thu Sun        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_1ST_3RD_SAT   |   Wkly 1St 3Rd Sat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THU_2ND_LAST_WEEK   |   Thu 2Nd Last Week        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MNTH_LAST_FRI   |   Mnth Last Fri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WKLY_FRI   |   Wkly Fri        |    Available     | Required     | Allowed |    NA |  

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab-end -->


### miscellaneous
---
tags: [miscellaneous]
---
- Description: Pricing Method Disclosures
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->
##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| SECURITY_EMAIL| Security contact email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| accountingUnitCode| Accounting Unit Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| aggregatorMerchantIndicator| Aggregator Merchant Indicator        |    NOT_AN_AGGREGATOR   |   Not An Aggregator        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_CHARITABLE_MERCHANT   |   Psp Charitable Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_SELECTIVE_ACCEPTANCE   |   Psp Selective Acceptance        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHARITABLE_MERCHANT   |   Charitable Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SELECTIVE_ACCEPTANCE   |   Selective Acceptance        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_MERCHANT   |   Psp Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GOVT_AND_EDU_PAYMENT_PROGRAM   |   Govt And Edu Payment Program        |    Available     | Required     | Allowed |    NA |    
| arpCode| ARP Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| bankingCategoryCode| Banking Category Code        |    OTHER_SILVER   |   Other Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_SILVER   |   Bbg Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_BRONZE   |   Wholesale Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_SILVER   |   Retail Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER_BRONZE   |   Other Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG   |   Bbg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER_GOLD   |   Other Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_GOLD   |   Wholesale Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_GOLD   |   Retail Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL   |   Retail        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE   |   Wholesale        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_SILVER   |   Wholesale Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_BRONZE   |   Bbg Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_GOLD   |   Bbg Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_BRONZE   |   Retail Bronze        |    Available     | Required     | Allowed |    NA |    
| branchDepositorIndicator| Branch Depositor Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| branchLongNumber| Branch Long Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| branchShortNumber| Branch Short Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| caseManagementIndicator| Case Management Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| cashManagementIndicator| Cash Management Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| cmsServiceCodes| CMS Service Codes        |       |           |    Available     | Required     | Allowed |    NA |    
| descriptorEntitledIndicator| Descriptor Entitled Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| SECURITY_EMAIL| Security contact email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| accountingUnitCode| Accounting Unit Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| aggregatorMerchantIndicator| Aggregator Merchant Indicator        |    NOT_AN_AGGREGATOR   |   Not An Aggregator        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_CHARITABLE_MERCHANT   |   Psp Charitable Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_SELECTIVE_ACCEPTANCE   |   Psp Selective Acceptance        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHARITABLE_MERCHANT   |   Charitable Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SELECTIVE_ACCEPTANCE   |   Selective Acceptance        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PSP_MERCHANT   |   Psp Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GOVT_AND_EDU_PAYMENT_PROGRAM   |   Govt And Edu Payment Program        |    Available     | Required     | Allowed |    NA |    
| arpCode| ARP Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| bankingCategoryCode| Banking Category Code        |    OTHER_SILVER   |   Other Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_SILVER   |   Bbg Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_BRONZE   |   Wholesale Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_SILVER   |   Retail Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER_BRONZE   |   Other Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG   |   Bbg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OTHER_GOLD   |   Other Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_GOLD   |   Wholesale Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_GOLD   |   Retail Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL   |   Retail        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE   |   Wholesale        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WHOLESALE_SILVER   |   Wholesale Silver        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_BRONZE   |   Bbg Bronze        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BBG_GOLD   |   Bbg Gold        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RETAIL_BRONZE   |   Retail Bronze        |    Available     | Required     | Allowed |    NA |    
| branchDepositorIndicator| Branch Depositor Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| branchLongNumber| Branch Long Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| branchShortNumber| Branch Short Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| caseManagementIndicator| Case Management Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| cashManagementIndicator| Cash Management Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| cmsServiceCodes| CMS Service Codes        |       |           |    Available     | Required     | Allowed |    NA |    
| descriptorEntitledIndicator| Descriptor Entitled Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| doNotChargeVee| Do Not Charge Vee for Omnipay        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| domesticForeignIndicator| DomesticForeignIndicator        |    DOM_MASTER_DESCRIPTION   |   Dom Master Description        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOM_FGN_INTERCHANGE_DESC   |   Dom Fgn Interchange Desc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FGN_MASTER_DESCRIPTION   |   Fgn Master Description        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AAFES_NAVY_MASTER_DESC   |   Aafes Navy Master Desc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AAFES_NAVY_USENEW_DESC   |   Aafes Navy Usenew Desc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOM_FGN_USENEW_DESC   |   Dom Fgn Usenew Desc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FGN_USENEW_DESCRIPTION   |   Fgn Usenew Description        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOM_USENEW_DESCRIPTION   |   Dom Usenew Description        |    Available     | Required     | Allowed |    NA |    
| emailtypecode| Type of Email Address        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| emvIndicator| EMV Chip Enabled Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| faxIndicator| Fax Indicator        |    EIDS_EMAIL   |   Eids Email        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INFO_FAX   |   Info Fax        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FAX   |   Fax        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CM_ALERT   |   Cm Alert        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EIDS   |   Eids        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PC_TO_PC   |   Pc To Pc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAIL   |   Mail        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EIDS_AUTOFAX   |   Eids Autofax        |    Available     | Required     | Allowed |    NA |    
| fireSafetyActIndicator| Fire Safety Act Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| imprintersCount| Imprinter Quantity Bill Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| internetCode| Internet Code        |    INTERNET_MERCHANT   |   Internet Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FISERV_GATEWAY   |   Fiserv Gateway        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DIAL_SOLUTION   |   Dial Solution        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEASED_LINE   |   Leased Line        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CERT_GATEWAY   |   Cert Gateway        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NON_PARTICIPANT   |   Non Participant        |    Available     | Required     | Allowed |    NA |    
| leaseCompanyCode| Lease Company Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| loyaltyProcessingCode| Loyalty Processing Code        |    N   |   N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    Y   |   Y        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
| ncptAmount| Anticipated Mc/Visa® net contribution per transaction        |       |           |    Available     | Required     | Allowed |    NA |    
| nrptAmount| Anticipated Mc/Visa® net revenue percentage        |       |           |    Available     | Required     | Allowed |    NA |    
| oilTradeClassCode| Class of Trade code for specific client usage        |    YES, NO   |   Yes, No        |    Available     | Required     | Allowed |    NA |    
| online| Online Indicator for Omnipay Merchant        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| paymentEssentialsCode| Payment essentials bundle code        |    BUNDLE8   |   Bundle8        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_1   |   Wells Bundle 1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE9   |   Bundle9        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE6   |   Bundle6        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE1   |   Bundle1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE14   |   Bundle14        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE3   |   Bundle3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_4   |   Wells Bundle 4        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE18   |   Bundle18        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_5   |   Wells Bundle 5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE11   |   Bundle11        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE16   |   Bundle16        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE12   |   Bundle12        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_2   |   Wells Bundle 2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE7   |   Bundle7        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE19   |   Bundle19        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE13   |   Bundle13        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE10   |   Bundle10        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE2   |   Bundle2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_6   |   Wells Bundle 6        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE20   |   Bundle20        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WELLS_BUNDLE_3   |   Wells Bundle 3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE5   |   Bundle5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE17   |   Bundle17        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE15   |   Bundle15        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BUNDLE4   |   Bundle4        |    Available     | Required     | Allowed |    NA |    
| rawDataAddendumIndicator| Raw Data Addendum Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| rejectNotifyCode| Reject Notification Code        |    OUTLET_DBA_ADDR   |   Outlet Dba Addr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OUTLET_BILLTO_ADDR   |   Outlet Billto Addr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHAIN_BILLTO_ADDR   |   Chain Billto Addr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHAIN_DBA_ADDR   |   Chain Dba Addr        |    Available     | Required     | Allowed |    NA |    
| restaurantGroupCode| Restaurant Group Code        |    NOT_MEMBER   |   Not Member        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SIG_REQUIRED   |   Sig Required        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GOLDEN_RETRIEVER   |   Golden Retriever        |    Available     | Required     | Allowed |    NA |    
| revenueBookedDate| Revenue Booked Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| specialNationalAccountIndicator| Special National Account Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| techEmail| Tech Email        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| volumeTierIndicator| Volume Tier Indicator        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Required     | Allowed |    NA |    
| volumeTierInterchangeFeeIndicator| Volume Tier Interchange Fee Indicator        |    TIER_10   |   Tier 10        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_17   |   Tier 17        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_04   |   Tier 04        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_41   |   Tier 41        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MP   |   Mp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_09   |   Tier 09        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_PARTICIPATING   |   Not Participating        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_18   |   Tier 18        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_22   |   Tier 22        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_33   |   Tier 33        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_20   |   Tier 20        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_11   |   Tier 11        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_30   |   Tier 30        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_19   |   Tier 19        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_08   |   Tier 08        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_01   |   Tier 01        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_39   |   Tier 39        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_21   |   Tier 21        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_13   |   Tier 13        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIER_23   |   Tier 23        |    Available     | Required     | Allowed |    NA |    
| xrefIndicator| Xref Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-end -->



### modelAfterMerchant

---
tags: [modelAfterMerchant]
---
- Description: Model After Merchant For Boarding Usage
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



### msipDetails

---
tags: [msipDetails]
---
- Description: MSIP Details
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| msipAlternateCityName| MSIP Alternate City Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipAlternateMerchantName| MSIP Alternate Merchant Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipBacsIndicator| MSIP Bacs Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| msipBacsMerchantName| MSIP Bacs Merchant Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipCategoryLevelCode| MSIP Category Level Code        |    VAU_MERCHANT   |   Vau Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIMITED_AMOUNT_TERMINAL   |   Limited Amount Terminal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRCH_PERFPGM_NOT_ME2ME   |   Mrch Perfpgm Not Me2Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_A_CAT_MERCHANT   |   Not A Cat Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ORIGINAL_CREDIT_TRANS   |   Original Credit Trans        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRCH_PERFPGM_AND_ME2ME   |   Mrch Perfpgm And Me2Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNATTEND_WITH_AUTH_CAPA   |   Unattend With Auth Capa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ME_TO_ME   |   Me To Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipChainRollupDate| MSIP Chain Rollup Date        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipChainRollupIndicator| MSIP Chain Rollup Indicator        |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipContactName| MSIP Contact Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipFax1Number| MSIP Fax1 Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipFax2Number| MSIP Fax2 Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipHotCardIndicator| MSIP Hot Card Indicator        |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    4   |   4        |    Available     | Required     | Allowed |    NA |    
| msipInternationalDialNumber| MSIP International Dial Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N   |   N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    5   |   5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipMaestroCeilingAmount| MSIP Maestro Ceiling Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroFloorAmount| MSIP Maestro Floor Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroFraudProneIndicator| MSIP Maestro Fraud Prone Indicator        |    NORMAL_RISK   |   Normal Risk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HIGHLY_FRAUD_PRONE   |   Highly Fraud Prone        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRAUD_PRONE   |   Fraud Prone        |    Available     | Required     | Allowed |    NA |    
| msipMaestroId| MSIP Maestro Id        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroMccCode| MSIP Maestro Mcc Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMailToAgentIndicator| MSIP Mail To Agent Indicator        |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipMailToBankIndicator| MSIP Mail To Bank Indicator        |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToBusinessIndicator| MSIP Mail To Business Indicator        |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToChainIndicator| MSIP Mail To Chain Indicator        |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
| msipMailToCorporationIndicator| MSIP Mail To Corporation Indicator        |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToOutletIndicator| MSIP Mail To Outlet Indicator        |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    O   |   O        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
| msipMastercardCurrencyCode| MSIP Mastercard Currency Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipNewAccountIndicator| MSIP New Account Indicator        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipPlasticFormatCode| MSIP Plastic Format Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipPlasticRegenerateIndicator| MSIP Plastic Regenerate Indicator        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipRecourseCode| MSIP Recourse Code        |    MAIL_ORDER_FULL_RECOURSE   |   Mail Order Full Recourse        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MISSING_IMPRINT_FULL_REC   |   Missing Imprint Full Rec        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOTH_MAIL_MISSING   |   Both Mail Missing        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| msipTerminalCount| MSIP Terminal Count        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaCashbackIndicator| MSIP Visa Cashback Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    5   |   5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N   |   N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
| msipVisaCeilingAmount| MSIP Visa Ceiling Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaCurrencyCode| MSIP Visa Currency Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaFloorAmount| MSIP Visa Floor Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| msipAlternateCityName| MSIP Alternate City Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipAlternateMerchantName| MSIP Alternate Merchant Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipBacsIndicator| MSIP Bacs Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| msipBacsMerchantName| MSIP Bacs Merchant Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipCategoryLevelCode| MSIP Category Level Code        |    VAU_MERCHANT   |   Vau Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIMITED_AMOUNT_TERMINAL   |   Limited Amount Terminal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRCH_PERFPGM_NOT_ME2ME   |   Mrch Perfpgm Not Me2Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_A_CAT_MERCHANT   |   Not A Cat Merchant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ORIGINAL_CREDIT_TRANS   |   Original Credit Trans        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MRCH_PERFPGM_AND_ME2ME   |   Mrch Perfpgm And Me2Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNATTEND_WITH_AUTH_CAPA   |   Unattend With Auth Capa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ME_TO_ME   |   Me To Me        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipChainRollupDate| MSIP Chain Rollup Date        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipChainRollupIndicator| MSIP Chain Rollup Indicator        |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipContactName| MSIP Contact Name        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipFax1Number| MSIP Fax1 Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipFax2Number| MSIP Fax2 Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipHotCardIndicator| MSIP Hot Card Indicator        |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    4   |   4        |    Available     | Required     | Allowed |    NA |    
| msipInternationalDialNumber| MSIP International Dial Number        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N   |   N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    5   |   5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipMaestroCeilingAmount| MSIP Maestro Ceiling Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroFloorAmount| MSIP Maestro Floor Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroFraudProneIndicator| MSIP Maestro Fraud Prone Indicator        |    NORMAL_RISK   |   Normal Risk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HIGHLY_FRAUD_PRONE   |   Highly Fraud Prone        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRAUD_PRONE   |   Fraud Prone        |    Available     | Required     | Allowed |    NA |    
| msipMaestroId| MSIP Maestro Id        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMaestroMccCode| MSIP Maestro Mcc Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipMailToAgentIndicator| MSIP Mail To Agent Indicator        |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipMailToBankIndicator| MSIP Mail To Bank Indicator        |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToBusinessIndicator| MSIP Mail To Business Indicator        |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToChainIndicator| MSIP Mail To Chain Indicator        |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
| msipMailToCorporationIndicator| MSIP Mail To Corporation Indicator        |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
| msipMailToOutletIndicator| MSIP Mail To Outlet Indicator        |    USE_DBA_ADDRESS   |   Use Dba Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    O   |   O        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_SENT   |   No Statement Sent        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    USE_BILL_TO_ADDRESS   |   Use Bill To Address        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_STATEMENT_GENERATED   |   No Statement Generated        |    Available     | Required     | Allowed |    NA |    
| msipMastercardCurrencyCode| MSIP Mastercard Currency Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipNewAccountIndicator| MSIP New Account Indicator        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| msipPlasticFormatCode| MSIP Plastic Format Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipPlasticRegenerateIndicator| MSIP Plastic Regenerate Indicator        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    0   |   0        |    Available     | Required     | Allowed |    NA |    
| msipRecourseCode| MSIP Recourse Code        |    MAIL_ORDER_FULL_RECOURSE   |   Mail Order Full Recourse        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MISSING_IMPRINT_FULL_REC   |   Missing Imprint Full Rec        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOTH_MAIL_MISSING   |   Both Mail Missing        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    1   |   1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| msipTerminalCount| MSIP Terminal Count        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaCashbackIndicator| MSIP Visa Cashback Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    5   |   5        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    2   |   2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N   |   N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    3   |   3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C   |   C        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
| msipVisaCeilingAmount| MSIP Visa Ceiling Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaCurrencyCode| MSIP Visa Currency Code        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    
| msipVisaFloorAmount| MSIP Visa Floor Amount        |    Not available in API mappings   |   Not Available In Api Mappings        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### mvbEmergingMarkets

---
tags: [mvbEmergingMarkets]
---
- Description: Mvb Emerging Markets
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    VISA_MC_HBR   |   Visa Mc Hbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGAL_GAMBLING   |   Legal Gambling        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DFS   |   Dfs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_PFAC   |   Single Mid Pfac        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    VISA_MC_HBR   |   Visa Mc Hbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGAL_GAMBLING   |   Legal Gambling        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DFS   |   Dfs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_PFAC   |   Single Mid Pfac        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### nationalAccountId

---
tags: [nationalAccountId]
---
- Description: National Account Underwriting Account Id
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| nationalAccountId| National account id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| nationalAccountId| National account id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### omahaDebitSuspenseItemsRelease

---
tags: [omahaDebitSuspenseItemsRelease]
---
- Description: Omaha Dd-623 Debit  Suspense Items Release - Channel Level
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### onBoardingDetails

---
tags: [onBoardingDetails]
---
- Description: OnBoarding Details
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| boardingOriginCode| Legacy field boarding origin code        |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EMERALD   |   Emerald        |    Available     | Required     | Allowed |    NA |    
| boardingSourceCode| Code which indicates what boarding tool or process was used        |    UAL   |   Ual        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONVERTED_ACCT   |   Converted Acct        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA_CLICK_TO_AGREE   |   Ama Click To Agree        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA   |   Ama        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HIERARCHY_ADD   |   Hierarchy Add        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACCESS_ONE   |   Access One        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA _WEB   |   Ama  Web        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FD_SNAP   |   Fd Snap        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COPILOT_N   |   Copilot N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COPILOT_O   |   Copilot O        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FD_MARKETPLACE   |   Fd Marketplace        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARTNER_REFERAL   |   Partner Referal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SNAP_MER_LITE   |   Snap Mer Lite        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GSB_BOARDING   |   Gsb Boarding        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA DE   |   Ama De        |    Available     | Required     | Allowed |    NA |    
| boardingTypeCode| Boarding Type Code        |    NEW_ACCOUNT   |   New Account        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ADDITIONAL_OUTLET   |   Additional Outlet        |    Available     | Required     | Allowed |    NA |    
| convertedAccountDate| Converted Account Date        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| convertedAccountIndicator| Converted Account Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| linkBackwardMerchantId| Link Backward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| linkForwardMerchantId| Link Forward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| boardingOriginCode| Legacy field boarding origin code        |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EMERALD   |   Emerald        |    Available     | Required     | Allowed |    NA |    
| boardingSourceCode| Code which indicates what boarding tool or process was used        |    UAL   |   Ual        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONVERTED_ACCT   |   Converted Acct        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA_CLICK_TO_AGREE   |   Ama Click To Agree        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA   |   Ama        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HIERARCHY_ADD   |   Hierarchy Add        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACCESS_ONE   |   Access One        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA _WEB   |   Ama  Web        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FD_SNAP   |   Fd Snap        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COPILOT_N   |   Copilot N        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COPILOT_O   |   Copilot O        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FD_MARKETPLACE   |   Fd Marketplace        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARTNER_REFERAL   |   Partner Referal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SNAP_MER_LITE   |   Snap Mer Lite        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GSB_BOARDING   |   Gsb Boarding        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMA DE   |   Ama De        |    Available     | Required     | Allowed |    NA |    
| boardingTypeCode| Boarding Type Code        |    NEW_ACCOUNT   |   New Account        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ADDITIONAL_OUTLET   |   Additional Outlet        |    Available     | Required     | Allowed |    NA |    
| convertedAccountDate| Converted Account Date        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| convertedAccountIndicator| Converted Account Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| linkBackwardMerchantId| Link Backward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| linkForwardMerchantId| Link Forward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### panMasking

---
tags: [panMasking]
---
- Description: Pan Masking
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|       offeringType       |              Offering Type          |    APPLY_PAN_MASKING   |   Apply Pan Masking        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|       offeringType       |              Offering Type          |    APPLY_PAN_MASKING   |   Apply Pan Masking        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->


### pathwardBankwire

---
tags: [pathwardBankwire]
---
- Description: Pathward Bankwire
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| beneficiaryCity| Beneficiary City        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryStateCode| Beneficiary State Code        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryStreetAddress| Beneficiary Street Address(No Po Box)        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryZipCode| Beneficiary Zip Code        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse1| Future Use 1        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse2| Future Use 2        |       |           |    Available     | Required     | Allowed |    NA |    
| seeBnfOnFndTab| See Bnf On Fnd Tab        |    SEE_BNF_ON_FND_TAB   |   See Bnf On Fnd Tab        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### pathwardEmergingMarkets

---
tags: [pathwardEmergingMarkets]
---
- Description: Pathward Emerging Markets
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType      |         Offering Type                |    NON_FI_LENDER   |   Non Fi Lender        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_MRKTPLACE   |   Single Mid Mrktplace        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSB_CRYPTO_NFT   |   Msb Crypto Nft        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DFS   |   Dfs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DCC   |   Dcc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLINE_FIREARMS   |   Online Firearms        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STAGED_DIGITAL_WALLET   |   Staged Digital Wallet        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MULTIPLE   |   Multiple        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CRUISE_LINES   |   Cruise Lines        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TBD   |   Tbd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGAL_GAMBLING   |   Legal Gambling        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_PFAC   |   Single Mid Pfac        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CAT_1   |   Cbd Cat 1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CAT_2   |   Cbd Cat 2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAYPAL_EXCEPTION   |   Paypal Exception        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AIRLINES   |   Airlines        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### paymentFacilitator

---
tags: [paymentFacilitator]
---
- Description: Payment Service Provider/Payment Facilitator
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| directPfFlag| Direct Pf Flag        |    A_AMOB_1MM   |   A Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    V_VI_1MM   |   V Vi 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    M_MC_1MM   |   M Mc 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    W_MC_VI_AMOB_1MM   |   W Mc Vi Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    X_VI_AMOB_1MM   |   X Vi Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    R_MC_VI_1MM   |   R Mc Vi 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    T_ MC_AMOB_1MM   |   T  Mc Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGACY   |   Legacy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GLOBAL   |   Global        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARKETPLACE_CLIENT   |   Marketplace Client        |    Available     | Required     | Allowed |    NA |    
| parentId| Parent ID        |       |           |    Available     | Required     | Allowed |    NA |    
| participantType| Participant Type        |    C_PARTICIPANT   |   C Participant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |   A Participant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    B_PARTICIPANT   |   B Participant        |    Available     | Required     | Allowed |    NA |    
| pfIdAmex| Payment Facilitator Id Amex        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdDscv| Payment Facilitator Id Discover        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdMc| Payment Facilitator Id Mc        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| directPfFlag| Direct Pf Flag        |    A_AMOB_1MM   |   A Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    V_VI_1MM   |   V Vi 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    M_MC_1MM   |   M Mc 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    W_MC_VI_AMOB_1MM   |   W Mc Vi Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    X_VI_AMOB_1MM   |   X Vi Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    R_MC_VI_1MM   |   R Mc Vi 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    T_ MC_AMOB_1MM   |   T  Mc Amob 1Mm        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGACY   |   Legacy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GLOBAL   |   Global        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARKETPLACE_CLIENT   |   Marketplace Client        |    Available     | Required     | Allowed |    NA |    
| parentId| Parent ID        |       |           |    Available     | Required     | Allowed |    NA |    
| participantType| Participant Type        |    C_PARTICIPANT   |   C Participant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |   A Participant        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    B_PARTICIPANT   |   B Participant        |    Available     | Required     | Allowed |    NA |    
| pfIdAmex| Payment Facilitator Id Amex        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdDscv| Payment Facilitator Id Discover        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdMc| Payment Facilitator Id Mc        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| pfIdMc| Payment Facilitator Id Mc        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdUpi| Payment Facilitator Id Upi        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdVi| Payment Facilitator Id-Marketplace Id Vi        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdVi| Payment Facilitator Id-Marketplace Id Vi        |       |           |    Available     | Required     | Allowed |    NA |    
| pspIndicator| Payment Service Provider Indicator        |    SELF_SERVICE   |   Self Service        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FUND_PF   |   Fund Pf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HYBRID_SERVICE   |   Hybrid Service        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FUND_SUB   |   Fund Sub        |    Available     | Required     | Allowed |    NA |    
| serviceType| Service Type for Omnipay        |    HYBRID   |   Hybrid        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FULL_SERVICE   |   Full Service        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SELF_SERVICE   |   Self Service        |    Available     | Required     | Allowed |    NA |    
| subMerchantId| Sub Merchant ID for Omnipay        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-end -->



### platformSwitch3CrossReference

---
tags: [platformSwitch3CrossReference]
---
- Description: Platform Switch 3 Cross Reference
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northChainBank| North Chain Bank        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->


##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northChainBank| North Chain Bank        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->



### pricingMthdDisclosures

---
tags: [pricingMthdDisclosures]
---
- Description: Pricing Method Disclosures
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType      |             Offering Type              |    UNKNOWN   |   Unknown        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_OTHER   |   All Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SIMPLIFIED   |   Simplified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLAT_RATE_NO_BB   |   Flat Rate No Bb        |    Available     | Required     | Allowed |    NA |    
| pricingSchedule| Pricing Schedule        |    SCHEDULE_103   |   Schedule 103        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNKNOWN   |   Unknown        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_135   |   Schedule 135        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_IC   |   Schedule Ic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_105   |   Schedule 105        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_112   |   Schedule 112        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_010   |   Schedule 010        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_3T   |   Schedule 3T        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_133   |   Schedule 133        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_127   |   Schedule 127        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_123   |   Schedule 123        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_120   |   Schedule 120        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_108   |   Schedule 108        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_113   |   Schedule 113        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_111   |   Schedule 111        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_102   |   Schedule 102        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_104   |   Schedule 104        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_136   |   Schedule 136        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_101   |   Schedule 101        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_028   |   Schedule 028        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_2T   |   Schedule 2T        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_150   |   Schedule 150        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_138   |   Schedule 138        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_125   |   Schedule 125        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_124   |   Schedule 124        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### North Specification

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType      |             Offering Type              |    UNKNOWN   |   Unknown        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_OTHER   |   All Other        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SIMPLIFIED   |   Simplified        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FLAT_RATE_NO_BB   |   Flat Rate No Bb        |    Available     | Required     | Allowed |    NA |    
| pricingSchedule| Pricing Schedule        |    SCHEDULE_103   |   Schedule 103        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNKNOWN   |   Unknown        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_135   |   Schedule 135        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_IC   |   Schedule Ic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_105   |   Schedule 105        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_112   |   Schedule 112        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_010   |   Schedule 010        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_3T   |   Schedule 3T        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_133   |   Schedule 133        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_127   |   Schedule 127        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_123   |   Schedule 123        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_120   |   Schedule 120        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_108   |   Schedule 108        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_113   |   Schedule 113        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_111   |   Schedule 111        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_102   |   Schedule 102        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_104   |   Schedule 104        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_136   |   Schedule 136        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_101   |   Schedule 101        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_028   |   Schedule 028        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_2T   |   Schedule 2T        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_150   |   Schedule 150        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_138   |   Schedule 138        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_125   |   Schedule 125        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SCHEDULE_124   |   Schedule 124        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab-end -->

