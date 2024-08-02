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

###  channelLevelDiscoverPromotionalPvi
---
tags: [channelLevelDiscoverPromotionalPvi
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



###  contract
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
