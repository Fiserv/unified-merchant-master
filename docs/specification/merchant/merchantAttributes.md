# Merchant Attributes

* **Description**: List of fields grouped under logical **Domains** and stored as key-value(s) pair as attributes.
  * Example of a **Domain**: [chargebackConfig](#-chargebackconfig) is a **domain** that groups all fields called as **Attributes** those configures chargeback related processing for a merchant. Example of some attributes are:
    * Chargeback Address code indicating where chargeback related information sent
    * Chargeback Pre-note Days
  * See [list of Domains](#list-of-domains)
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

## List of Fields

### MERCHANT_ID

* Description: Backend unique identifier for a merchant.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

**UMM Specification**
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |  BE specific   |     50     |   N/A   | Required | Required |

<!-- type: tab -->

**North Specification**
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       12       |     12     |   N/A   | Required | Required |

<!-- type: tab -->

**South Specification**
| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       11       |     11     |   N/A   | Required | Required |

<!-- type: tab -->

**GMA Specification**

| Type   | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|--------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| String |       11       |     11     |   N/A   | Required | Required |

<!-- 
type: tab-end 
-->

---

### PLATFORM_CODE

* Description: Backend platform identifier e.g. North, South etc.
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

**UMM Specification**

| Type | Minimum Length | Max Length | Inquiry |  Create  |  Update  |
|------|:--------------:|:----------:|:-------:|:--------:|:--------:|
| ENUM |      N/A       |     40     |   N/A   | Required | Required |

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)
<!-- 
type: tab-end 
-->

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

**UMM Specification**

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Numeric |      N/A       |     6      |   N/A   |  N/A   |  N/A   |

<!--  type: tab-end  -->

---

### VALUE

* Description: Value of the Attribute
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

**UMM Specification**

| Type   | Minimum Length | Max Length | Inquiry | Create | Update |
|--------|:--------------:|:----------:|:-------:|:------:|:------:|
| String |      N/A       |    200     |   N/A   |  N/A   |  N/A   |

<!--  type: tab-end  -->

---

## List of Domains

### acknowledgementFilePreference
---
tags: [acknowledgementFilePreference]
---
- Description: Acknowledgement File Preference
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ackFilePreference            | Acknowledgement File Preference                   | NORMAL        | Normal                                                    |Available | Required | Allowed  |    NA    |
|                              |                                                   | MASK          | Mask                                                      |Available | Required | Allowed  |    NA    |

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ackFilePreference            | Acknowledgement File Preference                   | NORMAL        | Normal                                                    |Available | Required | Allowed  |    NA    |
|                              |                                                   | MASK          | Mask                                                      |Available | Required | Allowed  |    NA    |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create | Update |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|:--------:|
|                              |                                                   |               |                                                           |          |        |        |    NA    |

<!--  type: tab-end  -->

### additionalBusinessInfo
---
tags: [additionalBusinessInfo]
---
- Description: Acknowledgement File Preference
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Valid Values  | Value Description                                         | Inquiry  | Create | Update | Delete |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|:------:|
| rccCode| Merchant Retailer Category        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Valid Values  | Value Description                                         | Inquiry  | Create | Update | Delete |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:------:|:------:|:------:|
| rccCode| Merchant Retailer Category        |       |           |    Available     | Required     | Allowed |    NA |    

<!--  type: tab-end  -->

### additionalTaxInfo
---
tags: [additionalTaxInfo]
---
- Description: Additional Tax Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->
**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| incomeTaxCode                | Income Tax Code                                   |               |                                                           | Available| Required | Allowed  |    NA    | 
| secondaryTaxId               | Secondary Tax ID                                  |               |                                                           | Available| Required | Allowed  |    NA    |
| vatTaxCode                   | VAT Tax Code                                      |               |                                                           | Available| Required | Allowed  |    NA    |

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| incomeTaxCode                | Income Tax Code                                   |               |                                                           | Available| Required | Allowed  |    NA    |
| secondaryTaxId               | Secondary Tax ID                                  |               |                                                           | Available| Required | Allowed  |    NA    |
| vatTaxCode                   | VAT Tax Code                                      |               |                                                           | Available| Required | Allowed  |    NA    |

<!--  type: tab-end  -->

### adrp
---
tags: [adrp]
---
- Description: Auto Decision Refund Process
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| adrpCumulativeLimitAmount| Cumulative refund amount on the same card in the past 30 or 60 days         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpCumulativeLimitCount | ADRP cumulative limit count         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpLimitAmount| A dollar limit defined for credits with no offsets         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| adrpCumulativeLimitAmount| Cumulative refund amount on the same card in the past 30 or 60 days         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpCumulativeLimitCount | ADRP cumulative limit count         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpLimitAmount| A dollar limit defined for credits with no offsets         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->

### authMatchExclusion
---
tags: [authMatchExclusion]
---
- Description: Auth Match Exclusion
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| southAuthMatchExclusion| South Auth Match Exclusion        |    ROOT_LEVEL_MATCHING   |   Root Level Matching        |    Available     | Required     | Allowed |    NA |    
|                        |                                   |    FULL_MID_MATCHING   |   Full Mid Matching        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| southAuthMatchExclusion| South Auth Match Exclusion        |    ROOT_LEVEL_MATCHING   |   Root Level Matching        |    Available     | Required     | Allowed |    NA |    
|                        |                                   |    FULL_MID_MATCHING   |   Full Mid Matching        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->

### authSettings
---
tags: [authSettings]
---
- Description: Auth Settings
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authTypeCode| Auth Type Code        |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|             |                       |    PRE_AUTHORIZATION   |   Pre Authorization        |    Available     | Required     | Allowed |    NA |    
|             |                       |    FINAL_AUTHORIZATION   |   Final Authorization        |    Available     | Required     | Allowed |    NA |    
| transactionCurrency| Transaction Currency         |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authTypeCode| Auth Type Code        |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
|             |                       |    PRE_AUTHORIZATION   |   Pre Authorization        |    Available     | Required     | Allowed |    NA |    
|             |                       |    FINAL_AUTHORIZATION   |   Final Authorization        |    Available     | Required     | Allowed |    NA |    
| transactionCurrency| Transaction Currency         |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### avsControl
---
tags: [avsControl]
---
- Description: AVS Control
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
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
| avsZipIndicator| Address verification service zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |  
|                |                                                   |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |  
<!-- type: tab -->

**North Specification**
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
| avsZipIndicator| Address verification service zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |  
|                |                                                   |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |  

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### bamsDissolutionHoldingsStatus
---
tags: [bamsDissolutionHoldingsStatus]
---
- Description: Bams Dissolution Holdings Status
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|             |                      |    OTHER_ASSIGNED   |   Other Assigned        |    Available     | Required     | Allowed |    NA |    
|             |                      |    BANK_OF_AMERICA   |   Bank Of America        |    Available     | Required     | Allowed |    NA |    
| status       | Program Status        |    ALLOCATED   |   Allocated        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DORMANT_CANCELLED   |   Dormant Cancelled        |    Available     | Required     | Allowed |    NA |    
|             |                      |    RESERVED_ATTACHED   |   Reserved Attached        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
|             |                      |    OTHER_ASSIGNED   |   Other Assigned        |    Available     | Required     | Allowed |    NA |    
|             |                      |    BANK_OF_AMERICA   |   Bank Of America        |    Available     | Required     | Allowed |    NA |    
| status       | Program Status        |    ALLOCATED   |   Allocated        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DORMANT_CANCELLED   |   Dormant Cancelled        |    Available     | Required     | Allowed |    NA |    
|             |                      |    RESERVED_ATTACHED   |   Reserved Attached        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### billingConfig
---
tags: [billingConfig]
---
- Description: Billing cofiguration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billSuppliesIndicator| Bill Supplies Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|             |                      |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|             |                      |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| delayedBillingEffectiveDate| Delayed billing effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| managementFeeDate| Date that management fee will be charged        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| membershipFeeDate| Date that membership fees will be charged  |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| retailerRateCode| Retailer rate code specific client usage        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          |             |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          |             |    MASTERCARD_ONLY   |   Mastercard Only   |    Available     | Optional     | Allowed |    NA |
|          |             |    VISA_ONLY   |   Visa Only   |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billSuppliesIndicator| Bill Supplies Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| delayedBillingEffectiveDate| Delayed billing effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| managementFeeDate| Date that management fee will be charged        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| membershipFeeDate| Date that membership fees will be charged  |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| retailerRateCode| Retailer rate code specific client usage        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                      |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### billmatrix
---
tags: [billmatrix]
---
- Description: Billmatrix
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ACCEPTED   |   Not Accepted        |    Available     | Required     | Allowed |    NA |    
|        | Program Status        |    ACCEPTED   |   Accepted        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ACCEPTED   |   Not Accepted        |    Available     | Required     | Allowed |    NA |    
|        | Program Status        |    ACCEPTED   |   Accepted        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### boardingAdditionalInfo
---
tags: [boardingAdditionalInfo]
---
- Description: Merchant Boarding Additional Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| descriptionOfGoods| Description of goods and services sold by the merchant        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| wisoSalesRepId| Sales rep id of the wholesale iso employee        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| descriptionOfGoods| Description of goods and services sold by the merchant        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| wisoSalesRepId| Sales rep id of the wholesale iso employee        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### cardbrandPassThruFees
---
tags: [cardbrandPassThruFees]
---
- Description: Cardbrand Pass Thru Fees
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### cardconnect
---
tags: [cardconnect]
---
- Description: Cardconnect File Identifier
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### cashAdvance
---
tags: [cashAdvance]
---
- Description: Cash Advance
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cashAdvanceLimitAmount| Cash advance Limit Amount        |    REJECT_IF_GTE_100000 - Reject if greater than or equal to 100000  |   Reject If Gte 100000 - Reject If Greater Than Or Equal To 100000        |    Available     | Optional     | Allowed |    NA |
| splitFundingAdvanceAmount| Split Funding Advance Amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| splitFundingParticipationCode| Split Funding Participation Code        |    ADV_REPAID   |   Adv Repaid        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
|             |                 |                                           ACTIVE   |   Active        |    Available     | Optional     | Allowed |    NA |
|        |       |  SPLIT_FUNDING   |   Split Funding        |    Available     | Optional     | Allowed |    NA   |
|        |       |  RAPID_ADVANCE   |   Rapid Advance        |    Available     | Optional     | Allowed |    NA   |
|        |       |  MERCHANT_CAPITAL_SRC   |   Merchant Capital Source  |  Available  | Optional     | Allowed |    NA   |
| splitFundingPayToMerchantId| Split funding pay to merchant number        |    STRING - Digits only - MERCHANT ID   |   String - Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| splitFundingPercent| Split Funding Percentage        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| splitFundingVendorCode| Split funding cash advance vendor code        |    MER_ADV_FUNDING   |   Mer Adv Funding        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    FDMCA   |   Fdmca        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    RAPID_ADV   |   Rapid Adv        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    FUND_TREE   |   Fund Tree        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    ADV_ME   |   Adv Me        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    ADV_ME_INC   |   Adv Me Inc        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    BIZ2_CREDIT   |   Biz2 Credit        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cashAdvanceLimitAmount| Cash advance Limit Amount        |    REJECT_IF_GTE_100000 - Reject if greater than or equal to 100000  |   Reject If Gte 100000 - Reject If Greater Than Or Equal To 100000        |    Available     | Optional     | Allowed |    NA |
| splitFundingAdvanceAmount| Split Funding Advance Amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| splitFundingParticipationCode| Split Funding Participation Code        |    ADV_REPAID   |   Adv Repaid        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
|             |                 |    ACTIVE   |   Active        |    Available     | Optional     | Allowed |    NA |
|        |       |  SPLIT_FUNDING   |   Split Funding        |    Available     | Optional     | Allowed |    NA   |
|        |       |  RAPID_ADVANCE   |   Rapid Advance        |    Available     | Optional     | Allowed |    NA   |
|        |       |  MERCHANT_CAPITAL_SRC   |   Merchant Capital Source  |  Available  | Optional     | Allowed |    NA   |
| splitFundingPayToMerchantId| Split funding pay to merchant number        |    STRING - Digits only - MERCHANT ID   |   String - Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| splitFundingPercent| Split Funding Percentage        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| splitFundingVendorCode| Split funding cash advance vendor code        |    MER_ADV_FUNDING   |   Mer Adv Funding        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    FDMCA   |   Fdmca        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    RAPID_ADV   |   Rapid Adv        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    FUND_TREE   |   Fund Tree        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    ADV_ME   |   Adv Me        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    ADV_ME_INC   |   Adv Me Inc        |    Available     | Optional     | Allowed |    NA |
|                              |                                         |    BIZ2_CREDIT   |   Biz2 Credit        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### cashAdvanceProgram
---
tags: [cashAdvanceProgram]
---
- Description: Cash Advance Gl Funding Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                      |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                      |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->

### channelLevelDiscoverPromotionalPvi
---
tags: [channelLevelDiscoverPromotionalPvi]
---
- Description: Discover Promotional Program Verification Identifier - Channel Level
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FD_DISCOVER_PROMO   |   Fd Discover Promo        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CLIENT_DISCOVER_PRO   |   Client Discover Pro        |    Available     | Required     | Allowed |    NA |    
| status      | Program Status       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FD_DISCOVER_PROMO   |   Fd Discover Promo        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CLIENT_DISCOVER_PRO   |   Client Discover Pro        |    Available     | Required     | Allowed |    NA |    
| status      | Program Status       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|             |                      |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

###  chargebackConfig
---
tags: [chargebackConfig]
---
- Description: chargeback Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**
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

<!-- type: tab -->

**North Specification**
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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


###  commercialCardInterchangeService
---
tags: [commercialCardInterchangeService]
---
- Description: Commercial Card Interchange Service
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ccisMerchantIncome| Commercial Card Interchange Service Merchant Income        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| ccisMerchantIncome| Commercial Card Interchange Service Merchant Income        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



###  compassOnNorth
---
tags: [compassOnNorth]
---
- Description: Compass Podb Functionality On North
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| forcedDeposit| Eligible For Force Deposits        |    FORCE_DEPOSITS   |   Force Deposits        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_FORCE_DEPOSITS   |   No Force Deposits        |    Available     | Required     | Allowed |    NA |    
| partialReversals| Eligible For Partial Reversals        |    NO_PARTIAL_REVERSALS   |   No Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    PARTIAL_REVERSALS   |   Partial Reversals        |    Available     | Required     | Allowed |    NA |    
| reauthorizations     |  Eligible For Re-Authorizations  |    NO_REAUTHORIZATIONS   |   No Reauthorizations        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    EXTENDED_AUTH_NO_REAUT   |   Extended Auth No Reaut        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    REAUTHORIZATIONS   |   Reauthorizations        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACTIVE_COMPASS_ON_NORTH   |   Active Compass On North        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL_COMPASS_ON_NORTH   |   Cancel Compass On North        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| forcedDeposit| Eligible For Force Deposits        |    FORCE_DEPOSITS   |   Force Deposits        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    NO_FORCE_DEPOSITS   |   No Force Deposits        |    Available     | Required     | Allowed |    NA |    
| partialReversals| Eligible For Partial Reversals        |    NO_PARTIAL_REVERSALS   |   No Partial Reversals        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    PARTIAL_REVERSALS   |   Partial Reversals        |    Available     | Required     | Allowed |    NA |    
| reauthorizations     |  Eligible For Re-Authorizations  |    NO_REAUTHORIZATIONS   |   No Reauthorizations        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    EXTENDED_AUTH_NO_REAUT   |   Extended Auth No Reaut        |    Available     | Required     | Allowed |    NA |    
|              |                                    |    REAUTHORIZATIONS   |   Reauthorizations        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACTIVE_COMPASS_ON_NORTH   |   Active Compass On North        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL_COMPASS_ON_NORTH   |   Cancel Compass On North        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



###  compassSpecialFeatures
---
tags: [compassSpecialFeatures]
---
- Description: Compass Front End Generated Refund Auths
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| amexOnlineRefund| Amex Online Refund        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| compassFrontendGenreFauth| Compass frontend Gen Ref Auth        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| visaToleranceCheckInd| Visa Tolerance Check Ind        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| amexOnlineRefund| Amex Online Refund        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| compassFrontendGenreFauth| Compass frontend Gen Ref Auth        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| visaToleranceCheckInd| Visa Tolerance Check Ind        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                 |                           |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


###  conditionalApprovalProgram
---
tags: [conditionalApprovalProgram]
---
- Description: Conditional Approval Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**
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

<!-- type: tab -->

**North Specification**
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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### contract
---
tags: [contract]
---
- Description: Contract
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
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


<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| clientRegionIndex| Client Region Index for Omnipay        |    BIN_OVERRIDE_123018   |   Bin Override 123018        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANADA   |   Canada        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITEDKINGDOM   |   Unitedkingdom        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123008   |   Bin Override 123008        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGAPORE   |   Singapore        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUSTRALIA   |   Australia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123013   |   Bin Override 123013        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123019   |   Bin Override 123019        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123009   |   Bin Override 123009        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123007   |   Bin Override 123007        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123014   |   Bin Override 123014        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HONG_KONG   |   Hong Kong        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123016   |   Bin Override 123016        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123005   |   Bin Override 123005        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123015   |   Bin Override 123015        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BY_TRANSACTION   |   By Transaction        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123006   |   Bin Override 123006        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123012   |   Bin Override 123012        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BY_TRAN_REJECTS   |   By Tran Rejects        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BY_COUNTRY   |   By Country        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123011   |   Bin Override 123011        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123010   |   Bin Override 123010        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123017   |   Bin Override 123017        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123004   |   Bin Override 123004        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123002   |   Bin Override 123002        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123020   |   Bin Override 123020        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123001   |   Bin Override 123001        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EUROPEAN_UNION   |   European Union        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BIN_OVERRIDE_123003   |   Bin Override 123003        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAPAN   |   Japan        |    Available     | Required     | Allowed |    NA |    
| clientTariff| This the merchant tariff assigned to the merchant        |       |           |    Available     | Required     | Allowed |    NA |    
| postingMethod| The posting method assigned to the merchant        |    GRS_999_USD   |   Grs 999 Usd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_ZAR_999   |   Gma Zar 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NA_HK_999   |   Na Hk 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_HUF   |   All To Huf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_GBP   |   Grs 999 Gbp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REG5_EU_999   |   Reg5 Eu 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_NOK_999   |   Gma Nok 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_USD_MSC   |   Pf Usd Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REG1_SG_999   |   Reg1 Sg 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_CHF_MSC   |   Pf Chf Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_NZD_MSC   |   Pf Nzd Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_EUR   |   Grs 999 Eur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_AUD   |   Grs 999 Aud        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_SEK_999   |   Gma Sek 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_SEK   |   Grs 999 Sek        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_SGD_MSC   |   Pf Sgd Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_GBP_MSC   |   Pf Gbp Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_SEK_MSC   |   Pf Sek Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_JPY   |   Grs 999 Jpy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_CAD   |   Grs 999 Cad        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_2   |   Regular 2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_EUR_MSC   |   Pf Eur Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_NOK   |   Grs 999 Nok        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NA_EU_999   |   Na Eu 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_6   |   Regular 6        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_DKK   |   Grs 999 Dkk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_HKD_MSC   |   Pf Hkd Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_CHF   |   Grs 999 Chf        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_CHF_999   |   Gma Chf 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_4   |   Regular 4        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_CAD_MSC   |   Pf Cad Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_NOK_MSC   |   Pf Nok Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NA   |   Na        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_DKK_999   |   Gma Dkk 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_1EUR   |   All To 1Eur        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_JPY_MSC   |   Pf Jpy Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_NZD   |   Grs 999 Nzd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_CZK   |   All To Czk        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_1   |   Regular 1        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TARIFF_15   |   Tariff 15        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_SGD   |   All To Sgd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REG6_SG_999   |   Reg6 Sg 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REG3_EU_999   |   Reg3 Eu 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_ZAR_MSC   |   Pf Zar Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_DKK_MSC   |   Pf Dkk Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_HKD   |   Grs 999 Hkd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_ZAR   |   Grs 999 Zar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TR15_JP_999   |   Tr15 Jp 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GMA_NZD_999   |   Gma Nzd 999        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRS_999_SGD   |   Grs 999 Sgd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_3   |   Regular 3        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PF_AUD_MSC   |   Pf Aud Msc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_GBP   |   All To Gbp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REGULAR_8   |   Regular 8        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALL_TO_PLN   |   All To Pln        |    Available     | Required     | Allowed |    NA |    
| protectAgainstFXChange| Indicate if the Merchant is protected against currency fluctuations on the event the transaction is disputed        |    FALSE   |   False        |    Available     | Required     | Allowed |    NA |    
| salesLead| Secondary Tax ID        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| serviceContractIndex| Service contract defines the processing rules for a merchant        |    SERVICE_CONTRACT_1   |   Service Contract 1        |    Available     | Required     | Allowed |    NA |    

<!--  type: tab-end  -->

### contractExpirationDate

---
tags: [contractExpirationDate]
---
- Description: Contract Expiration Date Notifications/Flag
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractExpirationDate| Contract Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| gcid| Global Client Id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractExpirationDate| Contract Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| gcid| Global Client Id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### conversionInformation

---
tags: [conversionInformation]
---
- Description: Conversion  Account Source System Data
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| salesmanCode| Salesman Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| salesmanCode| Salesman Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### creditSettings

---
tags: [creditSettings]
---
- Description: Credit Settings
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| creditBinInclusionIndicator| Credit BIN Inclusion Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| creditLimitAmount| Credit Limit Amount        |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
| cumulativeCreditLimitAmount| Cumulative Credit Limit Amount        |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
| cumulativeSalesLimitAmount| Cumulative Sales Limit Amount        |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_90000   |   Reject If Gte 90000        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| creditBinInclusionIndicator| Credit BIN Inclusion Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| creditLimitAmount| Credit Limit Amount        |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                  |                            |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
| cumulativeCreditLimitAmount| Cumulative Credit Limit Amount        |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                            |                                       |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
| cumulativeSalesLimitAmount| Cumulative Sales Limit Amount        |    REJECT_IF_GTE_1000   |   Reject If Gte 1000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_120000   |   Reject If Gte 120000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_400000   |   Reject If Gte 400000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_200000   |   Reject If Gte 200000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_300000   |   Reject If Gte 300000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_100000   |   Reject If Gte 100000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_800000   |   Reject If Gte 800000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_50000   |   Reject If Gte 50000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    UNLIMITED   |   Unlimited        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_20000   |   Reject If Gte 20000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_70000   |   Reject If Gte 70000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_110000   |   Reject If Gte 110000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_30000   |   Reject If Gte 30000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_500   |   Reject If Gte 500        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_80000   |   Reject If Gte 80000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_60000   |   Reject If Gte 60000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_40000   |   Reject If Gte 40000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_1   |   Reject If Gte 1        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_25000   |   Reject If Gte 25000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_100   |   Reject If Gte 100        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_3000   |   Reject If Gte 3000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_2000   |   Reject If Gte 2000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_7500   |   Reject If Gte 7500        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_5000   |   Reject If Gte 5000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_2   |   Reject If Gte 2        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_500000   |   Reject If Gte 500000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_50   |   Reject If Gte 50        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_600000   |   Reject If Gte 600000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_250   |   Reject If Gte 250        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_10000   |   Reject If Gte 10000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_700000   |   Reject If Gte 700000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_130000   |   Reject If Gte 130000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_15000   |   Reject If Gte 15000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_140000   |   Reject If Gte 140000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_150000   |   Reject If Gte 150000        |    Available     | Optional     | Allowed |    NA |
|                            |                                     |    REJECT_IF_GTE_90000   |   Reject If Gte 90000        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### crossBorderAcquiring

---
tags: [crossBorderAcquiring]
---
- Description: Cross Border Acquiring
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| viSingleMerchantId| Visa Single Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| viSmiActivationInd| Visa Smi Activation Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                   |                                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| viSingleMerchantId| Visa Single Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| viSmiActivationInd| Visa Smi Activation Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                   |                                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### dccForIab

---
tags: [dccForIab]
---
- Description: Dynamic Currency Conversion For International Agent Bank
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    DCC   |   Dcc        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DYNAMIC_PRICING   |   Dynamic Pricing        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    DCC   |   Dcc        |    Available     | Required     | Allowed |    NA |    
|             |                      |    DYNAMIC_PRICING   |   Dynamic Pricing        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### depositRequirement

---
tags: [depositRequirement]
---
- Description: Deposit Requirement
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| programGuideVersion| Program Guide Version        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|             |                      |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| programGuideVersion| Program Guide Version        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### disregardedEntity

---
tags: [disregardedEntity]
---
- Description: Disregarded Entity
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|       |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|       |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### earlyTerminationFee

---
tags: [earlyTerminationFee]
---
- Description: Early Termination Fee
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| earlyTermDate| Early termination date applicable to charging an associated fee        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeAmount| Early termination fee amount        |    STRING - Digits only - no decimal (max length - 4, min - 1)   |   String - Digits Only - No Decimal (Max Length: 4, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeIndicator| Early termination fee indicator        |    NO_TERMINATION_FEE   |   No Termination Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    CARS_DFAULT_FEE   |   Cars Dfault Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    USER_DEFINED_FEE   |   User Defined Fee        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| earlyTermDate| Early termination date applicable to charging an associated fee        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeAmount| Early termination fee amount        |    STRING - Digits only - no decimal (max length - 4, min - 1)   |   String - Digits Only - No Decimal (Max Length: 4, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| earlyTermFeeIndicator| Early termination fee indicator        |    NO_TERMINATION_FEE   |   No Termination Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    CARS_DFAULT_FEE   |   Cars Dfault Fee        |    Available     | Required     | Allowed |    NA |    
|                      |                                        |    USER_DEFINED_FEE   |   User Defined Fee        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### electronicTicketCapture

---
tags: [electronicTicketCapture]
---
- Description: Electronic Ticket Capture
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| etcBypassEditsIndicator| TellS the edit programs if the Merchant wishes to let all his ETC transactions process        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                        |                                                                                               |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| etcCutoffTimeCode| Code indicating what time electronic ticket capture processing is terminated for the day        |    6PM_CST   |   6Pm Cst        |    Available     | Optional     | Allowed |    NA |
|                  |       |    10PM_EST   |   10Pm Est        |    Available     | Optional     | Allowed |    NA |
|                  |       |    12AM_CST   |   12Am Cst        |    Available     | Optional     | Allowed |    NA |
|                  |           |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                  |       |    FDMS_DEFAULT   |   FDMS Default  |    Available     |    Optional  | Allowed |    NA   |
| etcOptionCode| Code identifying the type of electronic ticket capture processing used        |    None   |   None        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_VOICE_BKP   |   Etc Voice Bkp        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    NON_ETC   |   Non Etc        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_VOICE_BK_W_CLS_BAT   |   Etc Voice Bk W Cls Bat        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_ELECTRONIC_ONLY   |   Etc Electronic Only        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    HOST_OUT_OF_BALANCE   |   Host Out Of Balance        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_PLUS   |   Etc Plus        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_PLUS_DEBIT   |   Etc Plus Debit        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    HOST_MUST_BALANCE   |   Host Must Balance        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_ELC_W_CLS_BAT   |   Etc Elc W Cls Bat        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| etcBypassEditsIndicator| TellS the edit programs if the Merchant wishes to let all his ETC transactions process        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                        |                                                                                               |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| etcCutoffTimeCode| Code indicating what time electronic ticket capture processing is terminated for the day        |    6PM_CST   |   6Pm Cst        |    Available     | Optional     | Allowed |    NA |
|                  |                                                                                                 |    10PM_EST   |   10Pm Est        |    Available     | Optional     | Allowed |    NA |
|                  |                                                                                                 |    12AM_CST   |   12Am Cst        |    Available     | Optional     | Allowed |    NA |
|                  |                                                                                                 |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                  |       |    FDMS_DEFAULT   |   FDMS Default  |    Available     |    Optional  | Allowed |    NA   |
| etcOptionCode| Code identifying the type of electronic ticket capture processing used        |    None   |   None        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_VOICE_BKP   |   Etc Voice Bkp        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    NON_ETC   |   Non Etc        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_VOICE_BK_W_CLS_BAT   |   Etc Voice Bk W Cls Bat        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_ELECTRONIC_ONLY   |   Etc Electronic Only        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    HOST_OUT_OF_BALANCE   |   Host Out Of Balance        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_PLUS   |   Etc Plus        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_PLUS_DEBIT   |   Etc Plus Debit        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    HOST_MUST_BALANCE   |   Host Must Balance        |    Available     | Optional     | Allowed |    NA |
|              |                                                                               |    ETC_ELC_W_CLS_BAT   |   Etc Elc W Cls Bat        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### enhanceDebitCompletionFlow

---
tags: [enhanceDebitCompletionFlow]
---
- Description: Enhance Debit Completion Flow For Pts Direct Send Merchants
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ENHANCED_DB_FLOW_OFF   |   Enhanced Db Flow Off        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ENHANCED_DB_FLOW_ON   |   Enhanced Db Flow On        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ENHANCED_DB_FLOW_OFF   |   Enhanced Db Flow Off        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ENHANCED_DB_FLOW_ON   |   Enhanced Db Flow On        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### fdggMigration

---
tags: [fdggMigration]
---
- Description: First Data Global Gateway Migration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_MIGRATED   |   Not Migrated        |    Available     | Required     | Allowed |    NA |    
|       |                       |    MIGRATED   |   Migrated        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    NOT_MIGRATED   |   Not Migrated        |    Available     | Required     | Allowed |    NA |    
|       |                       |    MIGRATED   |   Migrated        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### financialBuAssignmentValues

---
tags: [financialBuAssignmentValues]
---
- Description: Financial Bu Assignment Values
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->



### firstHawaiianBank

---
tags: [firstHawaiianBank]
---
- Description: First Hawaiian Bank
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| fhbNaicsNumber| Fhb Naics Number N        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| fhbNaicsNumber| Fhb Naics Number N        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### foreignLanguageSupport

---
tags: [foreignLanguageSupport]
---
- Description: Foreign Language Support
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### franchise
---
tags: [franchise]
---
- Description: Franchise
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type  |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|             |                |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### fraudAndAccountTakeoverRisk
---
tags: [fraudAndAccountTakeoverRisk]
---
- Description: Fraud And Account Takeover Risk
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    CAUTION_PREVIOUS_FRAUD   |   Caution Previous Fraud        |    Available     | Required     | Allowed |    NA |    
|             |                |    URGENT_MERCH_AT_RISK   |   Urgent Merch At Risk        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    CAUTION_PREVIOUS_FRAUD   |   Caution Previous Fraud        |    Available     | Required     | Allowed |    NA |    
|             |                |    URGENT_MERCH_AT_RISK   |   Urgent Merch At Risk        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### freeProcessing
---
tags: [freeProcessing]
---
- Description: Free Processing
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    COMPLETED   |   Completed        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    COMPLETED   |   Completed        |    Available     | Required     | Allowed |    NA |    
|       |                       |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|       |                       |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### fundingConfig
---
tags: [fundingConfig]
---
- Description: Free Processing
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| achSuspenseHoldIndicator| ACH suspense hold indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|       |                       |    HOLD   |   Hold        |    Available     | Optional     | Allowed |    NA |
| achSuspenseReleaseIndicator| ACH suspense release indicator        |    DIVERT_TO_CARS   |   Divert To Cars        |    Available     | Optional     | Allowed |    NA |
|       |                       |    HOLD_30_DAYS   |   Hold 30 Days        |    Available     | Optional     | Allowed |    NA |
|       |                       |    RELEASE_FUNDING   |   Release Funding        |    Available     | Optional     | Allowed |    NA |
| agentBankSplitIndicator| Indicates if Bank Client is considered an agent relationship to FDCS        |    AGENT   |   Agent        |    Available     | Optional     | Allowed |    NA |
|       |                       |    BANK   |   Bank        |    Available     | Optional     | Allowed |    NA |
| bankwireBbkText| Bankwire beneficiary BBK Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| bankwireBnfText| Bankwire beneficiary BNF Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| bankwireObiText| Bankwire beneficiary OBI Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| chargebacksBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit        |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| chargebacksFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| chargebacksFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| chargebacksFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| convenienceFeeCode| Convenience fee code to indicate the ABA or DDA to be charged        |    ABA_DDA_3   |   Aba Dda 3        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_5   |   Aba Dda 5        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    None   |   None        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_2   |   Aba Dda 2        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_1   |   Aba Dda 1        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_4   |   Aba Dda 4        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
| depositsBankSequenceNumber| Funding Bank Sequence |  REMIT | Remit |  Available  | Optional | Allowed |  NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| depositsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
| depositsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|       |       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|       |       |    ICE   |   Ice        |    Available     | Optional     | Allowed |    NA |
| depositsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
| discountsBankSequenceNumber| Funding Bank Sequence  |  REMIT   |   Remit  | Available | Optional | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| discountsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
| discountsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                           |                            |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| discountsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
| feesBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available   |  Optional | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| feesFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
| feesFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                      |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| feesFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsBankSequenceNumber| Funding Bank Sequence  |    REMIT   |   Remit  |  Available |  Optional  | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingRollupCode   |Indicates how the transactions will be combined on DDA statement |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| funding30DayOverrideDate| Funding 30 day daily override date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| funding30DayOverrideIndicator| Funding 30 day override indicator        |    NOT_OVERRIDE   |   Not Override        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    OVERRIDE   |   Override        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
| fundingAchDelayDays| Retention period for deposits and daily discount before releasing them for ACH processing        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingBankCode| Funding Bank Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| fundingCurrencyCode| Funding Currency Code        |    QATARI_RIAL   |   Qatari Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ISRAELI_NEW_SHEKEL   |   Israeli New Shekel        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFA_FRANC_BEAC   |   Cfa Franc Beac        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UNITED_STATES_DOLLAR   |   United States Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CONGOLESE_FRANC   |   Congolese Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAYSIAN_RINGGIT   |   Malaysian Ringgit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAURITIAN_RUPEE   |   Mauritian Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOROCCAN_DIRHAM   |   Moroccan Dirham        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARUBAN_FLORIN   |   Aruban Florin        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PERUVIAN_SOL   |   Peruvian Sol        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ST_HELENA_POUND   |   St Helena Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BURUNDI_FRANC   |   Burundi Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BRUNEI_DOLLAR   |   Brunei Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COMOROS_FRANC   |   Comoros Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LAO_KIP   |   Lao Kip        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JAMAICAN_DOLLAR   |   Jamaican Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JAPANESE_YEN   |   Japanese Yen        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_KOREAN_WON   |   South Korean Won        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KUWAITI_DINAR   |   Kuwaiti Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NICARAGUAN_CORDOBA   |   Nicaraguan Cordoba        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PARAGUAYAN_GUARANI   |   Paraguayan Guarani        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KYRGYZSTAN_SOM   |   Kyrgyzstan Som        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUINEAN_FRANC   |   Guinean Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    POUND_STERLING   |   Pound Sterling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SINGAPORE_DOLLAR   |   Singapore Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DJIBOUTIAN_FRANC   |   Djiboutian Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CROTIAN_KUNA   |   Crotian Kuna        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    YEMENI_RIAL   |   Yemeni Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAWIAN_KWACHA   |   Malawian Kwacha        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZIMBABWE_DOLLAR   |   Zimbabwe Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NORWEGIAN_KRONE   |   Norwegian Krone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ALBANIAN_LEK   |   Albanian Lek        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BARBADOS_DOLLAR   |   Barbados Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UGANDAN_SHILLING   |   Ugandan Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHINESE_YUAN   |   Chinese Yuan        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DOMINCAN_PESO   |   Domincan Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ETHIOPIAN_BIRR   |   Ethiopian Birr        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AZERBAIJANI_MANAT   |   Azerbaijani Manat        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TANZANIAN_SHILLING   |   Tanzanian Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_SUDANESE_POUNT   |   South Sudanese Pount        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOMALI_SHILLING   |   Somali Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUANESE_DOLLAR   |   Guanese Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HONG_KONG_DOLLAR   |   Hong Kong Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SIERRA_LEONEAN_LEONE   |   Sierra Leonean Leone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INDOSEIAN_RUPIAH   |   Indoseian Rupiah        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOLDOVAN_LEU   |   Moldovan Leu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BANGLADESHI_TAKA   |   Bangladeshi Taka        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BOLIVIANO   |   Boliviano        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARMENIAN_DRAM   |   Armenian Dram        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFP_FRANC   |   Cfp Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FIJI_DOLLAR   |   Fiji Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HUNGARIAN_FORINT   |   Hungarian Forint        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INDIAN_RUPEE   |   Indian Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LEBANEESE_POUNT   |   Lebaneese Pount        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LESHTHO_LOTI   |   Leshtho Loti        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PAPUA_NEW_GUINEAN_KINA   |   Papua New Guinean Kina        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MEXICAN_PESO   |   Mexican Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUINEA_BISSAU_PESO   |   Guinea Bissau Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_TAIWAN_DOLLAR   |   New Taiwan Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TURKISH_LIRA   |   Turkish Lira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ANGOLAN_KWANZA   |   Angolan Kwanza        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EURO   |   Euro        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAMBODIAN_FRANC   |   Cambodian Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LIBERIAN_DOLLAR   |   Liberian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UKRANIAN_HRYVNIA   |   Ukranian Hryvnia        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAYMAN_ISLANDS_DOLLAR   |   Cayman Islands Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAURITANIAN_OUGUIYA   |   Mauritanian Ouguiya        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KENYAN_SHILLING   |   Kenyan Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWEDISH_KRONA   |   Swedish Krona        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BULGARIAN_LEV   |   Bulgarian Lev        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GEORGIAN_LARI   |   Georgian Lari        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    THAI_BAHT   |   Thai Baht        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VANUATU_VATU   |   Vanuatu Vatu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SERBIAN_DINAR   |   Serbian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BERMUDIAN_DOLLAR   |   Bermudian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    URUGUAYAN_PESO   |   Uruguayan Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DANISH_KRONE   |   Danish Krone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LIBYAN_DINAR   |   Libyan Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VIETNAMESE_DONG   |   Vietnamese Dong        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ERITREAN_NAFKA   |   Eritrean Nafka        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NIGERIAN_NAIRA   |   Nigerian Naira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MACEDONIAN_DENAR   |   Macedonian Denar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHILEAN_PESO   |   Chilean Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KAZAKHSTANI_TENGE   |   Kazakhstani Tenge        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BAHRANI_DINAR   |   Bahrani Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EL_SALVADORE_COLON   |   El Salvadore Colon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    POLISH_ZLOTY   |   Polish Zloty        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZAMBIAN_KWACHA   |   Zambian Kwacha        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MACANESE_PATACA   |   Macanese Pataca        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BOTSWANA_PULA   |   Botswana Pula        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TONGAN_PAANGA   |   Tongan Paanga        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_AFRICAN_RAND   |   South African Rand        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MYANMAR_KYAT   |   Myanmar Kyat        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COSTA_RICAN_COLON   |   Costa Rican Colon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GHANAIAN_CEDI   |   Ghanaian Cedi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOLOMON_ISLANDS_DOLLAR   |   Solomon Islands Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOZQAMBICAN_METICAL   |   Mozqambican Metical        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAGASY_ARIARY   |   Malagasy Ariary        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JORDANIAN_DINAR   |   Jordanian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWAZI_LILANGENI   |   Swazi Lilangeni        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CZECH_KORUNA   |   Czech Koruna        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWISS_FRANC   |   Swiss Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    RWANDA_FRANC   |   Rwanda Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_RUBLE   |   New Ruble        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PAKASTANI_RUPEE   |   Pakastani Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SRI_LANKA_RUPEE   |   Sri Lanka Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HAITIAN_GOURDE   |   Haitian Gourde        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ICELANDIC_KRONA   |   Icelandic Krona        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GAMBIAN_DALASI   |   Gambian Dalasi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAPE_VERDE_ESCUDO   |   Cape Verde Escudo        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BELIZE_DOLLAR   |   Belize Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    IRAQI_DINAR   |   Iraqi Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TAJIKISTANI_SOMONI   |   Tajikistani Somoni        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ROMANIAN_LEU   |   Romanian Leu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BELARUSSIAN_RUBLE   |   Belarussian Ruble        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BRAZILIAN_REAL   |   Brazilian Real        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VENEZLA_BOLIVAR_SOBERANO   |   Venezla Bolivar Soberano        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PHILIPPINE_PESO   |   Philippine Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    OMANI_RIAL   |   Omani Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUATEMALAN_QUETZAL   |   Guatemalan Quetzal        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALDIVIAN_RUFIYAA   |   Maldivian Rufiyaa        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EAST_CARIBBEAN_DOLLAR   |   East Caribbean Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SURINAMESE_DOLLAR   |   Surinamese Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFA_FRANC_BCEAO   |   Cfa Franc Bceao        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CONVERTIBLE_MARK   |   Convertible Mark        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NTHLNDS_ANTILIES_GUILDER   |   Nthlnds Antilies Guilder        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NAMIBIAN_DOLLAR   |   Namibian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ALGERIAN_DINAR   |   Algerian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UZBEKISTAN_SUM   |   Uzbekistan Sum        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAO_TOME_PRINCIPE_DOBRA   |   Sao Tome Principe Dobra        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GIBRALTAR_POUND   |   Gibraltar Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    OFFSHORE_REMNIBI   |   Offshore Remnibi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BHUTANESE_NGULTRUM   |   Bhutanese Ngultrum        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BAHAMIAN_DOLLAR   |   Bahamian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AUSTRALIAN_DOLLAR   |   Australian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ESTONIAN_KROON   |   Estonian Kroon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AFGHAN_AFGHANI   |   Afghan Afghani        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FALKLAND_ISLAND_POUND   |   Falkland Island Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MONGOLIAN_TOGROG   |   Mongolian Togrog        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TUNISIAN_DINAR   |   Tunisian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SEYCHELLES_RUPEE   |   Seychelles Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TRINADAD_+_TOBAGO_DOLLAR   |   Trinadad + Tobago Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARGENTINIAN_PESO   |   Argentinian Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PANAMANIAN_BALBOA   |   Panamanian Balboa        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_ZEALAND_DOLLAR   |   New Zealand Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COLOMBIAN_PESO   |   Colombian Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAMOAN_TALA   |   Samoan Tala        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EGYPTIAN_POUND   |   Egyptian Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HONDURAN_LEMPIRA   |   Honduran Lempira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEPALESE_RUPEE   |   Nepalese Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UNT_ARAB_EMERATES_DIRHAM   |   Unt Arab Emerates Dirham        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAUDI_RIYAL   |   Saudi Riyal        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TURKMENISTANI_MANAT   |   Turkmenistani Manat        |    Available     | Optional     | Allowed |    NA |
| fundingDailyOverrideDate| Funding Daily Override Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingDailyOverrideIndicator| Funding Override Indicator        |    OVERRIDE   |   Override        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NOT_OVERRIDE   |   Not Override        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
| fundingExclude30DayLimitAmount| Merchant funding exclusion monthly sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingExcludeCode| Merchant funding exclusion code        |    DIVERT   |   Divert        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| fundingExcludeDailyLimitAmount| Merchant funding exclusion daily sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingMethodCode| Funding method code Code determining how funds will be settled        |    CHK_TO_MAIN_BLK_LVL   |   Chk To Main Blk Lvl        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_CHAIN_AUTO_NEG   |   Bnkwire Chain Auto Neg        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SPLIT_OUTLET_BNKWIRE_ACH   |   Split Outlet Bnkwire Ach        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_BANK   |   Ach Bank        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AGENT_BANK_SPLIT_FUNDING   |   Agent Bank Split Funding        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_MER_BLK_CHAIN   |   Ach Mer Blk Chain        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SPLIT_CHAIN_BNKWIRE_ACH   |   Split Chain Bnkwire Ach        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_AGENT_AUTO_NEG   |   Bnkwire Agent Auto Neg        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_OUTLET   |   Bnkwire Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_BANK   |   Bnkwire Bank        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_OUTLET   |   Ach Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BY_CHK_TO_OUTLET   |   By Chk To Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_MER_BLK_CHAIN   |   Bnkwire Mer Blk Chain        |    Available     | Optional     | Allowed |    NA |
|            |         |    BANKWIRE_OUTLET_ACH   |   Bankwire Outlet ACH    |    Available     | Optional     | Allowed |    NA   |
| fundingNotifyContactName| Funding notification contact name        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyFaxNumber| Funding notification contact name        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyIndicator| Funding notification indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|       |      |    HIERARCHY   |   Hierarchy        |    Available     | Optional     | Allowed |    NA    |
| fundingNotifyMethodCode| Funding notification method code        |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TELEPHONE   |   Telephone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EMAIL   |   Email        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FAX   |   Fax        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyPhoneNumber| Funding notification phone number        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingRollupCode| Indicates how the funding transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VIA_CATGRY   |   Via Catgry        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| fundingRppChangeDate| Merchant funding revolving payment plan change date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingRppDelayDays| Revolving payment plan delay days        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppMinimumAmount| Revolving payment plan minimum dollar amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppMinimumReserveAmount| Revolving payment plan minimum reserve amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppPercent| Revolving payment plan percent        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRunCode| Merchant Funding Run        |    FUNDING_RUN6   |   Funding Run6        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Runs        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run4        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run1        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run2        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run3        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence  |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| interchangeAssessmentsFundingCategoryCode | Funding Category Code |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                                        |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsFundingRollupCode | Indicates how the transactions will be combined on DDA statement |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit |    Available | Optional | Allowed |  NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| nonBankcardAdjustmentsFundingCategoryCode | Funding Category Code |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsFundingDivertCode   | Funding Divert Code  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsFundingRollupCode   | Indicates how the transactions will be combined on DDA statement |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| ptsLimitsIndicator                        | PTS Limits Indicator  |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| reversalsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| reversalsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
| reversalsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| reversalsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
| settleTimeframeCode| Settlement Timeframe Code        |    BACS_SUPER   |   Bacs Super        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BACS_OR_NA   |   Bacs Or Na        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FASTER_PYMNT_METHOD   |   Faster Pymnt Method        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TWO_DAY_HOLD   |   Two Day Hold        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZERO_DAY_HOLD   |   Zero Day Hold        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ONE_DAY_HOLD   |   One Day Hold        |    Available     | Optional     | Allowed |    NA |
|             |          |    DEFERRED   |   Deferred        |    Available     | Optional     | Allowed |    NA |
| temporary30DayLimitAmount| Temporary monthly limit amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| temporaryDailyLimitAmount| Temporary Daily Limit Amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| temporaryFromDate| Temporary From Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| temporaryToDate| Temporary To Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| achSuspenseHoldIndicator| ACH suspense hold indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|       |                       |    HOLD   |   Hold        |    Available     | Optional     | Allowed |    NA    |
| achSuspenseReleaseIndicator| ACH suspense release indicator        |    DIVERT_TO_CARS   |   Divert To Cars        |    Available     | Optional     | Allowed |    NA |
|       |                       |    HOLD_30_DAYS   |   Hold 30 Days        |    Available     | Optional     | Allowed |    NA |
|       |                       |    RELEASE_FUNDING   |   Release Funding        |    Available     | Optional     | Allowed |    NA |
| agentBankSplitIndicator| Indicates if Bank Client is considered an agent relationship to FDCS        |    AGENT   |   Agent        |    Available     | Optional     | Allowed |    NA |
|       |                       |    BANK   |   Bank        |    Available     | Optional     | Allowed |    NA |
| bankwireBbkText| Bankwire beneficiary BBK Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| bankwireBnfText| Bankwire beneficiary BNF Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| bankwireObiText| Bankwire beneficiary OBI Text        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| chargebacksBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit        |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| chargebacksFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| chargebacksFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                               |                              |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| chargebacksFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| convenienceFeeCode| Convenience fee code to indicate the ABA or DDA to be charged        |    ABA_DDA_3   |   Aba Dda 3        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_5   |   Aba Dda 5        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    None   |   None        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_2   |   Aba Dda 2        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_1   |   Aba Dda 1        |    Available     | Optional     | Allowed |    NA |
|                             |                                                                         |    ABA_DDA_4   |   Aba Dda 4        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| depositAdjustmentsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
| depositsBankSequenceNumber| Funding Bank Sequence |  REMIT | Remit |  Available  | Optional | Allowed |  NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| depositsFundingCategoryCode| Funding Category Code        |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                            |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
| depositsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|               |          |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|       |       |    ICE   |   Ice        |    Available     | Optional     | Allowed |    NA |
| depositsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                          |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
| discountsBankSequenceNumber| Funding Bank Sequence  |  REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| discountsFundingCategoryCode| Funding Category Code        |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                             |                              |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
| discountsFundingDivertCode| Funding Divert Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                           |                            |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| discountsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                           |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
| feesBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available   |  Optional | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| feesFundingCategoryCode| Funding Category Code        |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
| feesFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                      |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| feesFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                      |                                                                         |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsBankSequenceNumber| Funding Bank Sequence  |    REMIT   |   Remit  |  Available |  Optional  | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingCategoryCode| Funding Category Code        |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| financialAdjustmentsFundingRollupCode   |Indicates how the transactions will be combined on DDA statement |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
| funding30DayOverrideDate| Funding 30 day daily override date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| funding30DayOverrideIndicator| Funding 30 day override indicator        |    NOT_OVERRIDE   |   Not Override        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    OVERRIDE   |   Override        |    Available     | Optional     | Allowed |    NA |
|                                            |                                  |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
| fundingAchDelayDays| Retention period for deposits and daily discount before releasing them for ACH processing        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingBankCode| Funding Bank Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| fundingCurrencyCode| Funding Currency Code        |    QATARI_RIAL   |   Qatari Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ISRAELI_NEW_SHEKEL   |   Israeli New Shekel        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFA_FRANC_BEAC   |   Cfa Franc Beac        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UNITED_STATES_DOLLAR   |   United States Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CONGOLESE_FRANC   |   Congolese Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAYSIAN_RINGGIT   |   Malaysian Ringgit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAURITIAN_RUPEE   |   Mauritian Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOROCCAN_DIRHAM   |   Moroccan Dirham        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARUBAN_FLORIN   |   Aruban Florin        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PERUVIAN_SOL   |   Peruvian Sol        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ST_HELENA_POUND   |   St Helena Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BURUNDI_FRANC   |   Burundi Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BRUNEI_DOLLAR   |   Brunei Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COMOROS_FRANC   |   Comoros Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LAO_KIP   |   Lao Kip        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JAMAICAN_DOLLAR   |   Jamaican Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JAPANESE_YEN   |   Japanese Yen        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_KOREAN_WON   |   South Korean Won        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KUWAITI_DINAR   |   Kuwaiti Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NICARAGUAN_CORDOBA   |   Nicaraguan Cordoba        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PARAGUAYAN_GUARANI   |   Paraguayan Guarani        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KYRGYZSTAN_SOM   |   Kyrgyzstan Som        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUINEAN_FRANC   |   Guinean Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    POUND_STERLING   |   Pound Sterling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SINGAPORE_DOLLAR   |   Singapore Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DJIBOUTIAN_FRANC   |   Djiboutian Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CROTIAN_KUNA   |   Crotian Kuna        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    YEMENI_RIAL   |   Yemeni Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAWIAN_KWACHA   |   Malawian Kwacha        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZIMBABWE_DOLLAR   |   Zimbabwe Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NORWEGIAN_KRONE   |   Norwegian Krone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ALBANIAN_LEK   |   Albanian Lek        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BARBADOS_DOLLAR   |   Barbados Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UGANDAN_SHILLING   |   Ugandan Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHINESE_YUAN   |   Chinese Yuan        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DOMINCAN_PESO   |   Domincan Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ETHIOPIAN_BIRR   |   Ethiopian Birr        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AZERBAIJANI_MANAT   |   Azerbaijani Manat        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TANZANIAN_SHILLING   |   Tanzanian Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_SUDANESE_POUNT   |   South Sudanese Pount        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOMALI_SHILLING   |   Somali Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUANESE_DOLLAR   |   Guanese Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HONG_KONG_DOLLAR   |   Hong Kong Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SIERRA_LEONEAN_LEONE   |   Sierra Leonean Leone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INDOSEIAN_RUPIAH   |   Indoseian Rupiah        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOLDOVAN_LEU   |   Moldovan Leu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BANGLADESHI_TAKA   |   Bangladeshi Taka        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BOLIVIANO   |   Boliviano        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARMENIAN_DRAM   |   Armenian Dram        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFP_FRANC   |   Cfp Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FIJI_DOLLAR   |   Fiji Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HUNGARIAN_FORINT   |   Hungarian Forint        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INDIAN_RUPEE   |   Indian Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LEBANEESE_POUNT   |   Lebaneese Pount        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LESHTHO_LOTI   |   Leshtho Loti        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PAPUA_NEW_GUINEAN_KINA   |   Papua New Guinean Kina        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MEXICAN_PESO   |   Mexican Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUINEA_BISSAU_PESO   |   Guinea Bissau Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_TAIWAN_DOLLAR   |   New Taiwan Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TURKISH_LIRA   |   Turkish Lira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ANGOLAN_KWANZA   |   Angolan Kwanza        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EURO   |   Euro        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAMBODIAN_FRANC   |   Cambodian Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LIBERIAN_DOLLAR   |   Liberian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UKRANIAN_HRYVNIA   |   Ukranian Hryvnia        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAYMAN_ISLANDS_DOLLAR   |   Cayman Islands Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAURITANIAN_OUGUIYA   |   Mauritanian Ouguiya        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KENYAN_SHILLING   |   Kenyan Shilling        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWEDISH_KRONA   |   Swedish Krona        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BULGARIAN_LEV   |   Bulgarian Lev        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GEORGIAN_LARI   |   Georgian Lari        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    THAI_BAHT   |   Thai Baht        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VANUATU_VATU   |   Vanuatu Vatu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SERBIAN_DINAR   |   Serbian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BERMUDIAN_DOLLAR   |   Bermudian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    URUGUAYAN_PESO   |   Uruguayan Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DANISH_KRONE   |   Danish Krone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    LIBYAN_DINAR   |   Libyan Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VIETNAMESE_DONG   |   Vietnamese Dong        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ERITREAN_NAFKA   |   Eritrean Nafka        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NIGERIAN_NAIRA   |   Nigerian Naira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MACEDONIAN_DENAR   |   Macedonian Denar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHILEAN_PESO   |   Chilean Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    KAZAKHSTANI_TENGE   |   Kazakhstani Tenge        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BAHRANI_DINAR   |   Bahrani Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EL_SALVADORE_COLON   |   El Salvadore Colon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    POLISH_ZLOTY   |   Polish Zloty        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZAMBIAN_KWACHA   |   Zambian Kwacha        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MACANESE_PATACA   |   Macanese Pataca        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BOTSWANA_PULA   |   Botswana Pula        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TONGAN_PAANGA   |   Tongan Paanga        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOUTH_AFRICAN_RAND   |   South African Rand        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MYANMAR_KYAT   |   Myanmar Kyat        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COSTA_RICAN_COLON   |   Costa Rican Colon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GHANAIAN_CEDI   |   Ghanaian Cedi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SOLOMON_ISLANDS_DOLLAR   |   Solomon Islands Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MOZQAMBICAN_METICAL   |   Mozqambican Metical        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALAGASY_ARIARY   |   Malagasy Ariary        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    JORDANIAN_DINAR   |   Jordanian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWAZI_LILANGENI   |   Swazi Lilangeni        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CZECH_KORUNA   |   Czech Koruna        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SWISS_FRANC   |   Swiss Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    RWANDA_FRANC   |   Rwanda Franc        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_RUBLE   |   New Ruble        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PAKASTANI_RUPEE   |   Pakastani Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SRI_LANKA_RUPEE   |   Sri Lanka Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HAITIAN_GOURDE   |   Haitian Gourde        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ICELANDIC_KRONA   |   Icelandic Krona        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GAMBIAN_DALASI   |   Gambian Dalasi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CAPE_VERDE_ESCUDO   |   Cape Verde Escudo        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BELIZE_DOLLAR   |   Belize Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    IRAQI_DINAR   |   Iraqi Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TAJIKISTANI_SOMONI   |   Tajikistani Somoni        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ROMANIAN_LEU   |   Romanian Leu        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BELARUSSIAN_RUBLE   |   Belarussian Ruble        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BRAZILIAN_REAL   |   Brazilian Real        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VENEZLA_BOLIVAR_SOBERANO   |   Venezla Bolivar Soberano        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PHILIPPINE_PESO   |   Philippine Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    OMANI_RIAL   |   Omani Rial        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GUATEMALAN_QUETZAL   |   Guatemalan Quetzal        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MALDIVIAN_RUFIYAA   |   Maldivian Rufiyaa        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EAST_CARIBBEAN_DOLLAR   |   East Caribbean Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SURINAMESE_DOLLAR   |   Surinamese Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CFA_FRANC_BCEAO   |   Cfa Franc Bceao        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CONVERTIBLE_MARK   |   Convertible Mark        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NTHLNDS_ANTILIES_GUILDER   |   Nthlnds Antilies Guilder        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NAMIBIAN_DOLLAR   |   Namibian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ALGERIAN_DINAR   |   Algerian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UZBEKISTAN_SUM   |   Uzbekistan Sum        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAO_TOME_PRINCIPE_DOBRA   |   Sao Tome Principe Dobra        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    GIBRALTAR_POUND   |   Gibraltar Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    OFFSHORE_REMNIBI   |   Offshore Remnibi        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BHUTANESE_NGULTRUM   |   Bhutanese Ngultrum        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BAHAMIAN_DOLLAR   |   Bahamian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AUSTRALIAN_DOLLAR   |   Australian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ESTONIAN_KROON   |   Estonian Kroon        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AFGHAN_AFGHANI   |   Afghan Afghani        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FALKLAND_ISLAND_POUND   |   Falkland Island Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MONGOLIAN_TOGROG   |   Mongolian Togrog        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TUNISIAN_DINAR   |   Tunisian Dinar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SEYCHELLES_RUPEE   |   Seychelles Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TRINADAD_+_TOBAGO_DOLLAR   |   Trinadad + Tobago Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ARGENTINIAN_PESO   |   Argentinian Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    PANAMANIAN_BALBOA   |   Panamanian Balboa        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEW_ZEALAND_DOLLAR   |   New Zealand Dollar        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    COLOMBIAN_PESO   |   Colombian Peso        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAMOAN_TALA   |   Samoan Tala        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EGYPTIAN_POUND   |   Egyptian Pound        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    HONDURAN_LEMPIRA   |   Honduran Lempira        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NEPALESE_RUPEE   |   Nepalese Rupee        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    UNT_ARAB_EMERATES_DIRHAM   |   Unt Arab Emerates Dirham        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SAUDI_RIYAL   |   Saudi Riyal        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TURKMENISTANI_MANAT   |   Turkmenistani Manat        |    Available     | Optional     | Allowed |    NA |
| fundingDailyOverrideDate| Funding Daily Override Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingDailyOverrideIndicator| Funding Override Indicator        |    OVERRIDE   |   Override        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NOT_OVERRIDE   |   Not Override        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
| fundingExclude30DayLimitAmount| Merchant funding exclusion monthly sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingExcludeCode| Merchant funding exclusion code        |    DIVERT   |   Divert        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| fundingExcludeDailyLimitAmount| Merchant funding exclusion daily sales limit amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingMethodCode| Funding method code Code determining how funds will be settled        |    CHK_TO_MAIN_BLK_LVL   |   Chk To Main Blk Lvl        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_CHAIN_AUTO_NEG   |   Bnkwire Chain Auto Neg        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SPLIT_OUTLET_BNKWIRE_ACH   |   Split Outlet Bnkwire Ach        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_BANK   |   Ach Bank        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    AGENT_BANK_SPLIT_FUNDING   |   Agent Bank Split Funding        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_MER_BLK_CHAIN   |   Ach Mer Blk Chain        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    SPLIT_CHAIN_BNKWIRE_ACH   |   Split Chain Bnkwire Ach        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_AGENT_AUTO_NEG   |   Bnkwire Agent Auto Neg        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_OUTLET   |   Bnkwire Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_BANK   |   Bnkwire Bank        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ACH_OUTLET   |   Ach Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BY_CHK_TO_OUTLET   |   By Chk To Outlet        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BNKWIRE_MER_BLK_CHAIN   |   Bnkwire Mer Blk Chain        |    Available     | Optional     | Allowed |    NA |
|            |         |    BANKWIRE_OUTLET_ACH   |   Bankwire Outlet ACH    |    Available     | Optional     | Allowed |    NA   |
| fundingNotifyContactName| Funding notification contact name        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyFaxNumber| Funding notification contact name        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyIndicator| Funding notification indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|       |      |    HIERARCHY   |   Hierarchy        |    Available     | Optional     | Allowed |    NA    |
| fundingNotifyMethodCode| Funding notification method code        |    NOT_USED   |   Not Used        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TELEPHONE   |   Telephone        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EMAIL   |   Email        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FAX   |   Fax        |    Available     | Optional     | Allowed |    NA |
| fundingNotifyPhoneNumber| Funding notification phone number        |    STRING containing digits only (max - 15, min - 10)   |   String Containing Digits Only (Max - 15, Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingRollupCode| Indicates how the funding transactions will be combined on DDA statement        |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    VIA_CATGRY   |   Via Catgry        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| fundingRppChangeDate| Merchant funding revolving payment plan change date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fundingRppDelayDays| Revolving payment plan delay days        |    STRING - Digits only - no decimal (max length - 2, min - 1)   |   String - Digits Only - No Decimal (Max Length: 2, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppMinimumAmount| Revolving payment plan minimum dollar amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppMinimumReserveAmount| Revolving payment plan minimum reserve amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRppPercent| Revolving payment plan percent        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Optional     | Allowed |    NA |
| fundingRunCode| Merchant Funding Run        |    FUNDING_RUN6   |   Funding Run6        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Runs        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run4        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run1        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run2        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |   Funding Run3        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsBankSequenceNumber| Funding Bank Sequence  |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |  
| interchangeAssessmentsFundingCategoryCode | Funding Category Code |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                                        |                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| interchangeAssessmentsFundingRollupCode | Indicates how the transactions will be combined on DDA statement |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit |    Available | Optional | Allowed |  NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| nonBankcardAdjustmentsFundingCategoryCode | Funding Category Code |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsFundingDivertCode   | Funding Divert Code  |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
| nonBankcardAdjustmentsFundingRollupCode   | Indicates how the transactions will be combined on DDA statement |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
| ptsLimitsIndicator                        | PTS Limits Indicator  |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|                                           |                       |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| reversalsBankSequenceNumber| Funding Bank Sequence |    REMIT   |   Remit  |    Available     | Optional     | Allowed |    NA |
|       |      |    DDA1   |   DDA#1   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA2   |   DDA#2   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA3   |   DDA#3   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA4   |   DDA#4   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA5   |   DDA#5   |    Available     | Optional     | Allowed |  NA |
|       |      |    DDA9   |   DDA#9   |    Available     | Optional     | Allowed |  NA |
| reversalsFundingCategoryCode| Funding Category Code        |    REVERSALS   |   Reversals        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    INTERCHANGE_ASSESSMENTS   |   Interchange Assessments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FEES   |   Fees        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NON_BANKCARD_ADJUSTMENTS   |   Non Bankcard Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FINANCIAL_ADJUSTMENTS   |   Financial Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSITS   |   Deposits        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_ADJUSTMENTS   |   Deposit Adjustments        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DISCOUNTS   |   Discounts        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    CHARGEBACKS   |   Chargebacks        |    Available     | Optional     | Allowed |    NA |
| reversalsFundingDivertCode| Funding Divert Code        |    CARS   |   Cars        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| reversalsFundingRollupCode| Indicates how the transactions will be combined on DDA statement        |    VIA_CATEGORY   |   Via Category        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    EACH_TRANSFER   |   Each Transfer        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEBIT_CREDIT   |   Debit Credit        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_FEE_TRANS   |   Net Fee Trans        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    NET_ROLLUP   |   Net Rollup        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    DEPOSIT_BATCH   |   Deposit Batch        |    Available     | Optional     | Allowed |    NA |
| settleTimeframeCode| Settlement Timeframe Code        |    BACS_SUPER   |   Bacs Super        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    BACS_OR_NA   |   Bacs Or Na        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    FASTER_PYMNT_METHOD   |   Faster Pymnt Method        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    TWO_DAY_HOLD   |   Two Day Hold        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ZERO_DAY_HOLD   |   Zero Day Hold        |    Available     | Optional     | Allowed |    NA |
|                     |                                            |    ONE_DAY_HOLD   |   One Day Hold        |    Available     | Optional     | Allowed |    NA |
|             |          |    DEFERRED   |   Deferred        |    Available     | Optional     | Allowed |    NA |
| temporary30DayLimitAmount| Temporary monthly limit amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| temporaryDailyLimitAmount| Temporary Daily Limit Amount        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| temporaryFromDate| Temporary From Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| temporaryToDate| Temporary To Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### globalCurrencySolutions
---
tags: [globalCurrencySolutions]
---
- Description: Global Currency Solutions
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringSubType1| Offering Sub Type        |    NORTH_RATES_PLUS_DCCLUS_DCC   |   North Rates Plus Dcclus Dcc        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EXCEPTION_RATE_MCPE_MCP   |   Exception Rate Mcpe Mcp        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VI/MC_RATE_MCPP   |   Vi/Mc Rate Mcpp        |    Available     | Required     | Allowed |    NA |    
| offeringSubType2| Globally Used For All North Backend Sales Channels        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    PRISMATIC   |   Prismatic        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringSubType1| Offering Sub Type        |    NORTH_RATES_PLUS_DCCLUS_DCC   |   North Rates Plus Dcclus Dcc        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    EXCEPTION_RATE_MCPE_MCP   |   Exception Rate Mcpe Mcp        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    VI/MC_RATE_MCPP   |   Vi/Mc Rate Mcpp        |    Available     | Required     | Allowed |    NA |    
| offeringSubType2| Globally Used For All North Backend Sales Channels        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    PRISMATIC   |   Prismatic        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
    
<!--  type: tab-end  -->

### highRiskMonitoring
---
tags: [highRiskMonitoring]
---
- Description: High Risk Monitoring
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### inHouseAuthConfig
---
tags: [inHouseAuthConfig]
---
- Description: InHouse Auth Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| inHouseAuthCaptureCode| InHouse Authorization Capture Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseBankCode| InHouse Bank Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseNonMerchantCode| InHouse NonMerchant Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
 
<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| inHouseAuthCaptureCode| InHouse Authorization Capture Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseBankCode| InHouse Bank Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| inHouseNonMerchantCode| InHouse NonMerchant Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
 
<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### indemnification
---
tags: [indemnification]
---
- Description: Indemnification
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### independentSoftwareVendor
---
tags: [independentSoftwareVendor]
---
- Description: Independent Software Vendor (Isv) Global Indicator
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    BYPASS_CLOVER_ISV   |   Bypass Clover Isv        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    BYPASS_CLOVER_ISV   |   Bypass Clover Isv        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### internalItUse
---
tags: [internalItUse]
---
- Description: Internal It Use - Trigger Feeds And Save Data
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| discoverTrigger| Registration Merchant Feed To Discover        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| spomiTrigger| Sponsored Merchant Feed To Amex        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REPROCESS   |   Reprocess        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| discoverTrigger| Registration Merchant Feed To Discover        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| spomiTrigger| Sponsored Merchant Feed To Amex        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|                                           |                       |    REPROCESS   |   Reprocess        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### iolCanadianVatRegNumber
---
tags: [iolCanadianVatRegNumber]
---
- Description: Iol Canadian Vat Reg Number
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| canadianVatRegNumber| Canadian Vat Registration Number        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| canadianVatRegNumber| Canadian Vat Registration Number        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



### irsSupplementalInformation
---
tags: [irsSupplementalInformation]
---
- Description: Irs Supplemental Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### isoServices
---
tags: [isoServices]
---
- Description: Iso Services
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

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

<!-- type: tab -->


**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### keyReferenceNumber
---
tags: [keyReferenceNumber]
---
- Description: Key Reference Number
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->


**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| keyReferenceNumber| Credit Only Key Reference Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| tbd| Tbd        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| keyReferenceNumber| Credit Only Key Reference Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Required     | Allowed |    NA |    
| tbd| Tbd        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->

### merchantCountryOfOrigin

---
tags: [merchantCountryOfOrigin]
---
- Description: Merchant Country Of Origin
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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
<!-- type: tab -->

**North Specification**

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
<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->




### merchantFraudAndSecurity

---
tags: [merchantFraudAndSecurity]
---
- Description: Merchant Fraud And Security
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| afdsMerchantAuthBlockStatus| Afds Merchant Auth Block Status        |    AFDS_AUTH_BLOCK   |   Afds Auth Block        |    Available     | Required     | Allowed |    NA |    
|          -                 |                 -                      |    AFDS_AUTH_UNBLOCK   |   Afds Auth Unblock        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| afdsMerchantAuthBlockStatus| Afds Merchant Auth Block Status        |    AFDS_AUTH_BLOCK   |   Afds Auth Block        |    Available     | Required     | Allowed |    NA |    
|          -                 |                 -                      |    AFDS_AUTH_UNBLOCK   |   Afds Auth Unblock        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->




### merchantFrontEnds

---
tags: [merchantFrontEnds]
---
- Description: Merchant Front Ends
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->




### merchantLiteConfig

---
tags: [merchantLiteConfig]
---
- Description: Merchant Lite Configuration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| merchantLiteAuthLimitAmount  | Merchant Lite Auth Limit Amount                   |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteCreditLimitAmount| Merchant Lite Credit Limit Amount                 |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteSalesLimitAmount | Merchant Lite Sales Limit Amount                  |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| merchantLiteAuthLimitAmount  | Merchant Lite Auth Limit Amount                   |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteCreditLimitAmount| Merchant Lite Credit Limit Amount                 |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| merchantLiteSalesLimitAmount | Merchant Lite Sales Limit Amount                  |    STRING - Digits only - no decimal (max length - 5, min - 1)   |   String - Digits Only - No Decimal (Max Length: 5, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### merchantMunicipality

---
tags: [merchantMunicipality]
---
- Description: Merchant Municipality
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| municipalityTaxInd| Municipality Tax Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| municipilatityCode| Municipality Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!-- type: tab -->

**GMA Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| municipalityTaxInd| Municipality Tax Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| municipilatityCode| Municipality Code        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    



<!--  type: tab-end  -->




### merchantPortfolioType

---
tags: [merchantPortfolioType]
---
- Description: Merchant Portfolio Type
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| byTransactionCount| Transaction Count Portfolio Size        |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| byTransactionCount| Transaction Count Portfolio Size        |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    NATIONAL   |   National        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SMB   |   Smb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDMARKET   |   Midmarket        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->




### merchantPricingStructure

---
tags: [merchantPricingStructure]
---
- Description: Merchant Pricing Structure
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->




### miniPromoForStationOutage

---
tags: [miniPromoForStationOutage]
---
- Description: Mini Promo For Station Outage
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**


| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| contractDate| Contract Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    


<!--  type: tab-end  -->


### miscReporting

---
tags: [miscReporting]
---
- Description: MISC
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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

<!-- type: tab -->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### miscellaneous
---
tags: [miscellaneous]
---
- Description: miscellaneous
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->
**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| SECURITY_EMAIL| Security contact email        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| accountingUnitCode| Accounting Unit Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| aggregatorMerchantIndicator| Aggregator Merchant Indicator        |    NOT_AN_AGGREGATOR   |   Not An Aggregator        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_CHARITABLE_MERCHANT   |   Psp Charitable Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_SELECTIVE_ACCEPTANCE   |   Psp Selective Acceptance        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHARITABLE_MERCHANT   |   Charitable Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SELECTIVE_ACCEPTANCE   |   Selective Acceptance        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_MERCHANT   |   Psp Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GOVT_AND_EDU_PAYMENT_PROGRAM   |   Govt And Edu Payment Program        |    Available     | Optional     | Allowed |    NA |
| arpCode| ARP Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| bankingCategoryCode| Banking Category Code        |    OTHER_SILVER   |   Other Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_SILVER   |   Bbg Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_BRONZE   |   Wholesale Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_SILVER   |   Retail Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER_BRONZE   |   Other Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG   |   Bbg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER_GOLD   |   Other Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_GOLD   |   Wholesale Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_GOLD   |   Retail Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL   |   Retail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE   |   Wholesale        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_SILVER   |   Wholesale Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_BRONZE   |   Bbg Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_GOLD   |   Bbg Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_BRONZE   |   Retail Bronze        |    Available     | Optional     | Allowed |    NA |
|  -  |    -    |    NONE   |   Blank Value        |    Available     | Optional     | Allowed |    NA |
| branchDepositorIndicator| Branch Depositor Indicator  |    YES   |   Yes  |  Available | Optional | Allowed | NA |
|   -  |   -   |    NO   |   No        |    Available     | Optional     | Allowed |  NA |
|   -  |   -   |    NONE   |   None    |    Available     | Optional     | Allowed |  NA |
| branchLongNumber| Branch Long Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| branchShortNumber| Branch Short Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| caseManagementIndicator| Case Management Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| cashManagementIndicator| Cash Management Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| cmsServiceCodes| CMS Service Codes        |       |           |    Available     | Optional     | Allowed |    NA |
| descriptorEntitledIndicator| Descriptor Entitled Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| domesticForeignIndicator| DomesticForeignIndicator        |    DOM_MASTER_DESCRIPTION   |   Dom Master Description        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DOM_FGN_INTERCHANGE_DESC   |   Dom Fgn Interchange Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FGN_MASTER_DESCRIPTION   |   Fgn Master Description        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AAFES_NAVY_MASTER_DESC   |   Aafes Navy Master Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AAFES_NAVY_USENEW_DESC   |   Aafes Navy Usenew Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DOM_FGN_USENEW_DESC   |   Dom Fgn Usenew Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FGN_USENEW_DESCRIPTION   |   Fgn Usenew Description        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DOM_USENEW_DESCRIPTION   |   Dom Usenew Description        |    Available     | Optional     | Allowed |    NA |
|   -    |    -    |    DOM_USENEW_DESCRIPTION   |   Dom Usenew Description   |    Available  | Optional  | Allowed |  NA |
|   -    |    -    |    DOM_FGN_ALT_DESC   |   Dom FGN ALT Description   |    Available  | Optional  | Allowed |  NA |
|   -    |    -    |    DOM_FGN_DBA_DESC   |   Dom FGN DBA Description   |    Available  | Optional  | Allowed |  NA |
| emailtypecode| Type of Email Address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| emvIndicator| EMV Chip Enabled Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|             |                                   |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| faxIndicator| Fax Indicator        |    EIDS_EMAIL   |   Eids Email        |    Available     | Optional     | Allowed |    NA |
|             |                      |    INFO_FAX   |   Info Fax        |    Available     | Optional     | Allowed |    NA |
|             |                      |    FAX   |   Fax        |    Available     | Optional     | Allowed |    NA |
|             |                      |    CM_ALERT   |   Cm Alert        |    Available     | Optional     | Allowed |    NA |
|             |                      |    EIDS   |   Eids        |    Available     | Optional     | Allowed |    NA |
|             |                      |    PC_TO_PC   |   Pc To Pc        |    Available     | Optional     | Allowed |    NA |
|             |                      |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|             |                      |    EIDS_AUTOFAX   |   Eids Autofax        |    Available     | Optional     | Allowed |    NA |
| fireSafetyActIndicator| Fire Safety Act Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|             |                      |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|             |              |    NONE   |   Blank Value        |    Available     | Optional     | Allowed |    NA    |  
| imprintersCount| Imprinter Quantity Bill Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |  
| internetCode| Internet Code        |    INTERNET_MERCHANT   |   Internet Merchant        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    FISERV_GATEWAY   |   Fiserv Gateway        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    DIAL_SOLUTION   |   Dial Solution        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    LEASED_LINE   |   Leased Line        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CERT_GATEWAY   |   Cert Gateway        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NON_PARTICIPANT   |   Non Participant        |    Available     | Optional     | Allowed |    NA |
|       |         |    NONE   |   None        |    Available     | Optional     | Allowed |    NA    | 
| leaseCompanyCode| Lease Company Code   |    CIT   |   CIT    |    Available     | Optional     | Allowed |    NA   |
|    |   |    FDLS   |   FDLS    |    Available     | Optional     | Allowed |   NA  |
|    |   |    3RD_PARTY   |   3RD_PARTY    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NORTHERN   |   NORTHERN    |    Available     | Optional     | Allowed |   NA  |
|    |   |    LADCO   |   LADCO    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NONE   |   Blank Value    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NOT_SPECIFIED   |   Not Specified    |    Available     | Optional     | Allowed |   NA  |
| loyaltyProcessingCode| Loyalty Processing Code |    NO   |   No   |    Available     | Optional     | Allowed |  NA |  
|                    |            |    YES   |   Yes       |    Available     | Optional     | Allowed |    NA |  
|                    |            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |  
| ncptAmount| Anticipated Mc/Visa® net contribution per transaction        |       |           |    Available     | Optional     | Allowed |    NA |  
| nrptAmount| Anticipated Mc/Visa® net revenue percentage        |       |           |    Available     | Optional     | Allowed |    NA |  
| oilTradeClassCode| Class of Trade code for specific client usage        |    YES, NO   |   Yes, No        |    Available     | Optional     | Allowed |    NA |  
| paymentEssentialsCode| Payment essentials bundle code        |    BUNDLE8   |   Bundle8        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_1   |   Wells Bundle 1        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE9   |   Bundle9        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE6   |   Bundle6        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE1   |   Bundle1        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE14   |   Bundle14        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE3   |   Bundle3        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_4   |   Wells Bundle 4        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE18   |   Bundle18        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_5   |   Wells Bundle 5        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE11   |   Bundle11        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE16   |   Bundle16        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE12   |   Bundle12        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_2   |   Wells Bundle 2        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE7   |   Bundle7        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE19   |   Bundle19        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE13   |   Bundle13        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE10   |   Bundle10        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE2   |   Bundle2        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_6   |   Wells Bundle 6        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE20   |   Bundle20        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_3   |   Wells Bundle 3        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE5   |   Bundle5        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE17   |   Bundle17        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE15   |   Bundle15        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE4   |   Bundle4        |    Available     | Optional     | Allowed |    NA |  
| rawDataAddendumIndicator| Raw Data Addendum Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
| rejectNotifyCode| Reject Notification Code        |    OUTLET_DBA_ADDR   |   Outlet Dba Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    OUTLET_BILLTO_ADDR   |   Outlet Billto Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CHAIN_BILLTO_ADDR   |   Chain Billto Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CHAIN_DBA_ADDR   |   Chain Dba Addr        |    Available     | Optional     | Allowed |    NA |  
| restaurantGroupCode| Restaurant Group Code        |    NOT_MEMBER   |   Not Member        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    SIG_Optional   |   Sig Optional        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    GOLDEN_RETRIEVER   |   Golden Retriever        |    Available     | Optional     | Allowed |    NA |  
| revenueBookedDate| Revenue Booked Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |  
| specialNationalAccountIndicator| Special National Account Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
| techEmail| Tech Email        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |  
| volumeTierIndicator| Volume Tier Indicator        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Optional     | Allowed |    NA |  
| volumeTierInterchangeFeeIndicator| Volume Tier Interchange Fee Indicator        |    TIER_10   |   Tier 10        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_17   |   Tier 17        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_04   |   Tier 04        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_41   |   Tier 41        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    MP   |   Mp        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_09   |   Tier 09        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NOT_PARTICIPATING   |   Not Participating        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_18   |   Tier 18        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_22   |   Tier 22        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_33   |   Tier 33        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_20   |   Tier 20        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_11   |   Tier 11        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_30   |   Tier 30        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_19   |   Tier 19        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_08   |   Tier 08        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_01   |   Tier 01        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_39   |   Tier 39        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_21   |   Tier 21        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_13   |   Tier 13        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_23   |   Tier 23        |    Available     | Optional     | Allowed |    NA |  
| xrefIndicator| Xref Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| doNotChargeVee | Do Not Charge Vee for Omnipay  |    STRING   |   String   |    Available     | Optional | Allowed |    NA |
| online | Online Indicator for Omnipay Merchant |    NO   |   No  |    Available     | Optional     | Allowed |    NA |
|  -  |  -  |  YES   |   Yes  |  Available | Optional | Allowed |    NA  |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| SECURITY_EMAIL| Security contact email        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| accountingUnitCode| Accounting Unit Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| aggregatorMerchantIndicator| Aggregator Merchant Indicator        |    NOT_AN_AGGREGATOR   |   Not An Aggregator        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_CHARITABLE_MERCHANT   |   Psp Charitable Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_SELECTIVE_ACCEPTANCE   |   Psp Selective Acceptance        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHARITABLE_MERCHANT   |   Charitable Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SELECTIVE_ACCEPTANCE   |   Selective Acceptance        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PSP_MERCHANT   |   Psp Merchant        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GOVT_AND_EDU_PAYMENT_PROGRAM   |   Govt And Edu Payment Program        |    Available     | Optional     | Allowed |    NA |
| arpCode| ARP Code        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| bankingCategoryCode| Banking Category Code        |    OTHER_SILVER   |   Other Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER   |   Other        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_SILVER   |   Bbg Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_BRONZE   |   Wholesale Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_SILVER   |   Retail Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER_BRONZE   |   Other Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG   |   Bbg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OTHER_GOLD   |   Other Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_GOLD   |   Wholesale Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_GOLD   |   Retail Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL   |   Retail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE   |   Wholesale        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    WHOLESALE_SILVER   |   Wholesale Silver        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_BRONZE   |   Bbg Bronze        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BBG_GOLD   |   Bbg Gold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RETAIL_BRONZE   |   Retail Bronze        |    Available     | Optional     | Allowed |    NA |
|  -  |    -    |    NONE   |   Blank Value        |    Available     | Optional     | Allowed |    NA |
| branchDepositorIndicator| Branch Depositor Indicator  |    YES   |   Yes  |  Available | Optional | Allowed | NA |
|   -  |   -   |    NO   |   No        |    Available     | Optional     | Allowed |  NA |
|   -  |   -   |    NONE   |   None    |    Available     | Optional     | Allowed |  NA |
| branchLongNumber| Branch Long Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| branchShortNumber| Branch Short Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| caseManagementIndicator| Case Management Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| cashManagementIndicator| Cash Management Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| cmsServiceCodes| CMS Service Codes        |       |           |    Available     | Optional     | Allowed |    NA |
| descriptorEntitledIndicator| Descriptor Entitled Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| domesticForeignIndicator| DomesticForeignIndicator        |    DOM_MASTER_DESCRIPTION   |   Dom Master Description        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DOM_FGN_INTERCHANGE_DESC   |   Dom Fgn Interchange Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FGN_MASTER_DESCRIPTION   |   Fgn Master Description        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AAFES_NAVY_MASTER_DESC   |   Aafes Navy Master Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AAFES_NAVY_USENEW_DESC   |   Aafes Navy Usenew Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DOM_FGN_USENEW_DESC   |   Dom Fgn Usenew Desc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FGN_USENEW_DESCRIPTION   |   Fgn Usenew Description        |    Available     | Optional     | Allowed |    NA |
|   -    |    -    |    DOM_USENEW_DESCRIPTION   |   Dom Usenew Description   |    Available  | Optional  | Allowed |  NA |
|   -    |    -    |    DOM_FGN_ALT_DESC   |   Dom FGN ALT Description   |    Available  | Optional  | Allowed |  NA |
|   -    |    -    |    DOM_FGN_DBA_DESC   |   Dom FGN DBA Description   |    Available  | Optional  | Allowed |  NA |
| emailtypecode| Type of Email Address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| emvIndicator| EMV Chip Enabled Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|             |                                   |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| faxIndicator| Fax Indicator        |    EIDS_EMAIL   |   Eids Email        |    Available     | Optional     | Allowed |    NA |
|             |                      |    INFO_FAX   |   Info Fax        |    Available     | Optional     | Allowed |    NA |
|             |                      |    FAX   |   Fax        |    Available     | Optional     | Allowed |    NA |
|             |                      |    CM_ALERT   |   Cm Alert        |    Available     | Optional     | Allowed |    NA |
|             |                      |    EIDS   |   Eids        |    Available     | Optional     | Allowed |    NA |
|             |                      |    PC_TO_PC   |   Pc To Pc        |    Available     | Optional     | Allowed |    NA |
|             |                      |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|             |                      |    EIDS_AUTOFAX   |   Eids Autofax        |    Available     | Optional     | Allowed |    NA |
| fireSafetyActIndicator| Fire Safety Act Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|             |                      |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|             |              |    NONE   |   Blank Value        |    Available     | Optional     | Allowed |    NA    |  
| imprintersCount| Imprinter Quantity Bill Number        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |  
| internetCode| Internet Code        |    INTERNET_MERCHANT   |   Internet Merchant        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    FISERV_GATEWAY   |   Fiserv Gateway        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    DIAL_SOLUTION   |   Dial Solution        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    LEASED_LINE   |   Leased Line        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CERT_GATEWAY   |   Cert Gateway        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NON_PARTICIPANT   |   Non Participant        |    Available     | Optional     | Allowed |    NA |
|       |         |    NONE   |   None        |    Available     | Optional     | Allowed |    NA    |  
| leaseCompanyCode| Lease Company Code   |    CIT   |   CIT    |    Available     | Optional     | Allowed |    NA   |
|    |   |    FDLS   |   FDLS    |    Available     | Optional     | Allowed |   NA  |
|    |   |    3RD_PARTY   |   3RD_PARTY    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NORTHERN   |   NORTHERN    |    Available     | Optional     | Allowed |   NA  |
|    |   |    LADCO   |   LADCO    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NONE   |   Blank Value    |    Available     | Optional     | Allowed |   NA  |
|    |   |    NOT_SPECIFIED   |   Not Specified    |    Available     | Optional     | Allowed |   NA  | 
| loyaltyProcessingCode| Loyalty Processing Code |    NO   |   No   |    Available     | Optional     | Allowed |  NA |  
|                    |            |    YES   |   Yes       |    Available     | Optional     | Allowed |    NA |  
|                    |            |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |  
| ncptAmount| Anticipated Mc/Visa® net contribution per transaction        |       |           |    Available     | Optional     | Allowed |    NA |  
| nrptAmount| Anticipated Mc/Visa® net revenue percentage        |       |           |    Available     | Optional     | Allowed |    NA |  
| oilTradeClassCode| Class of Trade code for specific client usage        |    YES, NO   |   Yes, No        |    Available     | Optional     | Allowed |    NA |  
| paymentEssentialsCode| Payment essentials bundle code        |    BUNDLE8   |   Bundle8        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_1   |   Wells Bundle 1        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE9   |   Bundle9        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE6   |   Bundle6        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE1   |   Bundle1        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE14   |   Bundle14        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE3   |   Bundle3        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_4   |   Wells Bundle 4        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE18   |   Bundle18        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_5   |   Wells Bundle 5        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE11   |   Bundle11        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE16   |   Bundle16        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE12   |   Bundle12        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_2   |   Wells Bundle 2        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE7   |   Bundle7        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE19   |   Bundle19        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE13   |   Bundle13        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE10   |   Bundle10        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE2   |   Bundle2        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_6   |   Wells Bundle 6        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE20   |   Bundle20        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    WELLS_BUNDLE_3   |   Wells Bundle 3        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE5   |   Bundle5        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE17   |   Bundle17        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE15   |   Bundle15        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    BUNDLE4   |   Bundle4        |    Available     | Optional     | Allowed |    NA |  
| rawDataAddendumIndicator| Raw Data Addendum Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
| rejectNotifyCode| Reject Notification Code        |    OUTLET_DBA_ADDR   |   Outlet Dba Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    OUTLET_BILLTO_ADDR   |   Outlet Billto Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CHAIN_BILLTO_ADDR   |   Chain Billto Addr        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    CHAIN_DBA_ADDR   |   Chain Dba Addr        |    Available     | Optional     | Allowed |    NA |  
| restaurantGroupCode| Restaurant Group Code        |    NOT_MEMBER   |   Not Member        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    SIG_Optional   |   Sig Optional        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    GOLDEN_RETRIEVER   |   Golden Retriever        |    Available     | Optional     | Allowed |    NA |  
| revenueBookedDate| Revenue Booked Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |  
| specialNationalAccountIndicator| Special National Account Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
| techEmail| Tech Email        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |  
| volumeTierIndicator| Volume Tier Indicator        |    STRING - Alphanumeric   |   String - Alphanumeric        |    Available     | Optional     | Allowed |    NA |  
| volumeTierInterchangeFeeIndicator| Volume Tier Interchange Fee Indicator        |    TIER_10   |   Tier 10        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_17   |   Tier 17        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_04   |   Tier 04        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_41   |   Tier 41        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    MP   |   Mp        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_09   |   Tier 09        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NOT_PARTICIPATING   |   Not Participating        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_18   |   Tier 18        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_22   |   Tier 22        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_33   |   Tier 33        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_20   |   Tier 20        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_11   |   Tier 11        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_30   |   Tier 30        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_19   |   Tier 19        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_08   |   Tier 08        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_01   |   Tier 01        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_39   |   Tier 39        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_21   |   Tier 21        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_13   |   Tier 13        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    TIER_23   |   Tier 23        |    Available     | Optional     | Allowed |    NA |  
| xrefIndicator| Xref Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |  
|                    |                                       |    NO   |   No        |    Available     | Optional     | Allowed |    NA |  

<!-- type: tab -->

**GMA Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| doNotChargeVee| Do Not Charge Vee for Omnipay        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |
| online| Online Indicator for Omnipay Merchant        |    NO   |   No        |    Available     | Required     | Allowed |    NA |
|                    |                                       |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |

<!--  type: tab-end  -->



### modelAfterMerchant

---
tags: [modelAfterMerchant]
---
- Description: Model After Merchant For Boarding Usage
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    


<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



### msipDetails

---
tags: [msipDetails]
---
- Description: MSIP Details
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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
| msipMaestroCashbackIndicator | MSIP Maestro Cashback Indicator   |    2   |   2        |    Available     | Required     | Allowed |    NA |    
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


<!-- type: tab -->

**North Specification**

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
| msipMaestroCashbackIndicator | MSIP Maestro Cashback Indicator   |    2   |   2        |    Available     | Required     | Allowed |    NA |    
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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### mvbEmergingMarkets

---
tags: [mvbEmergingMarkets]
---
- Description: Mvb Emerging Markets
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    VISA_MC_HBR   |   Visa Mc Hbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGAL_GAMBLING   |   Legal Gambling        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DFS   |   Dfs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_PFAC   |   Single Mid Pfac        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    VISA_MC_HBR   |   Visa Mc Hbr        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CBD_CANNABIS   |   Cbd Cannabis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEGAL_GAMBLING   |   Legal Gambling        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DFS   |   Dfs        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MSB   |   Msb        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGLE_MID_PFAC   |   Single Mid Pfac        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



### nationalAccountId

---
tags: [nationalAccountId]
---
- Description: National Account Underwriting Account Id
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| nationalAccountId| National account id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| nationalAccountId| National account id        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->



### omahaDebitSuspenseItemsRelease

---
tags: [omahaDebitSuspenseItemsRelease]
---
- Description: Omaha Dd-623 Debit  Suspense Items Release - Channel Level
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    

<!--  type: tab-end  -->


### onBoardingDetails

---
tags: [onBoardingDetails]
---
- Description: OnBoarding Details
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| boardingOriginCode| Legacy field boarding origin code        |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |
|          -            |                 -                    |    EMERALD   |   Emerald        |    Available     | Required     | Allowed |    NA |
|   -   |    -   |    NONE   |   Blank Value  |    Available     | Required     | Allowed |    NA    |
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
|   -   |   -  |    VAPP_BRICK_AND_MORTAR   |   VAPP Brick and Mortar   |    Available     | Required     | Allowed |  NA |
|   -   |   -  |    TRACES   |   Traces   |    Available     | Required     | Allowed |  NA |
|   -   |   -  |    NONE   |   Blank Value   |    Available     | Required     | Allowed |  NA |
| boardingTypeCode| Boarding Type Code |    NEW_ACCOUNT   |  New Account |  Available | Required  | Allowed | NA |
|   -   |    -   |    ADDITIONAL_OUTLET   |   Additional Outlet  |    Available     | Required  | Allowed |  NA |
|   -   |    -   |    BATCH_FEED   |   Batch Feed  |    Available     | Required  | Allowed |  NA |
| convertedAccountDate| Converted Account Date        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| convertedAccountIndicator| Converted Account Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| linkBackwardMerchantId| Link Backward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| linkForwardMerchantId| Link Forward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| boardingOriginCode| Legacy field boarding origin code        |    MERCURY   |   Mercury        |    Available     | Required     | Allowed |    NA |
|          -            |                 -                    |    BAM   |   Bam        |    Available     | Required     | Allowed |    NA |
|          -            |                 -                    |    EMERALD   |   Emerald        |    Available     | Required     | Allowed |    NA |
|   -   |    -   |    NONE   |   Blank Value  |    Available     | Required     | Allowed |    NA    |
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
|   -   |   -  |    VAPP_BRICK_AND_MORTAR   |   VAPP Brick and Mortar   |    Available     | Required     | Allowed |  NA |
|   -   |   -  |    TRACES   |   Traces   |    Available     | Required     | Allowed |  NA |
|   -   |   -  |    NONE   |   Blank Value   |    Available     | Required     | Allowed |  NA |
| boardingTypeCode| Boarding Type Code |    NEW_ACCOUNT   |  New Account |  Available | Required  | Allowed | NA |
|   -   |    -   |    ADDITIONAL_OUTLET   |   Additional Outlet  |    Available     | Required  | Allowed |  NA |
|   -   |    -   |    BATCH_FEED   |   Batch Feed  |    Available     | Required  | Allowed |  NA |
| convertedAccountDate| Converted Account Date        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| convertedAccountIndicator| Converted Account Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| linkBackwardMerchantId| Link Backward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| linkForwardMerchantId| Link Forward Merchant Id        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->


### panMasking

---
tags: [panMasking]
---
- Description: Pan Masking
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|       offeringType       |              Offering Type          |    APPLY_PAN_MASKING   |   Apply Pan Masking        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|       offeringType       |              Offering Type          |    APPLY_PAN_MASKING   |   Apply Pan Masking        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->


### pathwardBankwire

---
tags: [pathwardBankwire]
---
- Description: Pathward Bankwire
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| beneficiaryCity| Beneficiary City        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryStateCode| Beneficiary State Code        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryStreetAddress| Beneficiary Street Address(No Po Box)        |       |           |    Available     | Required     | Allowed |    NA |    
| beneficiaryZipCode| Beneficiary Zip Code        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse1| Future Use 1        |       |           |    Available     | Required     | Allowed |    NA |    
| futureUse2| Future Use 2        |       |           |    Available     | Required     | Allowed |    NA |    
| seeBnfOnFndTab| See Bnf On Fnd Tab        |    SEE_BNF_ON_FND_TAB   |   See Bnf On Fnd Tab        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->


### pathwardEmergingMarkets

---
tags: [pathwardEmergingMarkets]
---
- Description: Pathward Emerging Markets
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**North Specification**

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

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |   

<!--  type: tab-end  -->


### paymentFacilitator

---
tags: [paymentFacilitator]
---
- Description: Payment Service Provider/Payment Facilitator
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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
|       |                                  |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdUpi| Payment Facilitator Id Upi        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdVi| Payment Facilitator Id-Marketplace Id Vi        |       |           |    Available     | Required     | Allowed |    NA |    


<!-- type: tab -->

**North Specification**

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
|       |                                  |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdUpi| Payment Facilitator Id Upi        |       |           |    Available     | Required     | Allowed |    NA |    
| pfIdVi| Payment Facilitator Id-Marketplace Id Vi        |       |           |    Available     | Required     | Allowed |    NA |    


<!-- type: tab -->

**GMA Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| serviceType| Service Type for Omnipay        |    HYBRID   |   Hybrid        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FULL_SERVICE   |   Full Service        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SELF_SERVICE   |   Self Service        |    Available     | Required     | Allowed |    NA |    
| pfIdVi| Payment Facilitator Id-Marketplace Id Vi        |       |           |    Available     | Required     | Allowed |    NA |    
| pspIndicator| Payment Service Provider Indicator        |    SELF_SERVICE   |   Self Service        |    Available     | Required     | Allowed |    NA |    
|                    |                                       |    FUND_PF   |   Fund Pf        |    Available     | Required     | Allowed |    NA |    
|                    |                                       |    HYBRID_SERVICE   |   Hybrid Service        |    Available     | Required     | Allowed |    NA |    
|                    |                                       |    FUND_SUB   |   Fund Sub        |    Available     | Required     | Allowed |    NA |    
| subMerchantId| Sub Merchant ID for Omnipay        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |   

<!--  type: tab-end  -->


### platformSwitch3CrossReference

---
tags: [platformSwitch3CrossReference]
---
- Description: Platform Switch 3 Cross Reference
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northChainBank| North Chain Bank        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northChainBank| North Chain Bank        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          |    
<!--  type: tab-end  -->

### pricingMthdDisclosures

---
  tags: [pricingMthdDisclosures]
---
- Description: Pricing Method Disclosures
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

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


<!-- type: tab -->

**North Specification**

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


<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 
<!--  type: tab-end  -->



### promotion

---
tags: [promotion]
---
- Description: Promotion Tracking
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| promotionName1| Promotion Name One        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName2| Promotion Name Two        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName3| Promotion Name Three        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName4| Promotion Name Four        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName5| Promotion Name Five        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| promotionName1| Promotion Name One        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName2| Promotion Name Two        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName3| Promotion Name Three        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName4| Promotion Name Four        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| promotionName5| Promotion Name Five        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
 

<!-- type: tab -->

**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 

<!--  type: tab-end  -->




### prop51Conversion

---
tags: [prop51Conversion]
---
- Description: Prop 51 Conversion
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northShellMid| Original North Shell Mid/N        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| propMerchantId| Original Prop Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| northShellMid| Original North Shell Mid/N        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| propMerchantId| Original Prop Merchant Id        |    Digits only - MERCHANT ID   |   Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### purchaseReturnAuthAutomation

---
tags: [purchaseReturnAuthAutomation]
---
- Description: Purchase Return Authorization Automation
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ENABLED   |   Not Enabled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ENABLED   |   Enabled        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ENABLED   |   Not Enabled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ENABLED   |   Enabled        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### rapidDepositExceptionStatus

---
tags: [rapidDepositExceptionStatus]
---
- Description: Rapid Deposit Exception Status
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO_RAPID_DEP_OVERRIDE   |   No Rapid Dep Override        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RAPID_DEP_NOT_ALLOWED   |   Rapid Dep Not Allowed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RAPID_DEP_IS_ALLOWED   |   Rapid Dep Is Allowed        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    NO_RAPID_DEP_OVERRIDE   |   No Rapid Dep Override        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RAPID_DEP_NOT_ALLOWED   |   Rapid Dep Not Allowed        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RAPID_DEP_IS_ALLOWED   |   Rapid Dep Is Allowed        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### rateLock

---
tags: [rateLock]
---
- Description: Rate Lock
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billingEffectiveDate| Billing Effective Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| billingExpirationDate| Billing Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| rateLockLength| Number Of Years The Rate Lock Is In Place        |    TWO_YEARS   |   Two Years        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THREE_YEARS   |   Three Years        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONE_YEAR   |   One Year        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billingEffectiveDate| Billing Effective Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| billingExpirationDate| Billing Expiration Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| rateLockLength| Number Of Years The Rate Lock Is In Place        |    TWO_YEARS   |   Two Years        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THREE_YEARS   |   Three Years        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONE_YEAR   |   One Year        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### recurringPayment

---
tags: [recurringPayment]
---
- Description: Recurring Payment
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| recurringPaymentsIndicator| Hosted Recurring Payments Indicator        |    HPR_MC_VISA_CAU   |   Hpr Mc Visa Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_PARTICIPATING_HRP   |   Not Participating Hrp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_ALL_CAU   |   Hrp All Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_DISCOVER_CAU   |   Hrp Discover Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_VISA_CAU   |   Hrp Visa Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARTICIPATING_HRP   |   Participating Hrp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_MC_DISCOVER_CAU   |   Hrp Mc Discover Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_NC_CAU   |   Hrp Nc Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_VISA_DISCOVER_CAU   |   Hrp Visa Discover Cau        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| recurringPaymentsIndicator| Hosted Recurring Payments Indicator        |    HPR_MC_VISA_CAU   |   Hpr Mc Visa Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_PARTICIPATING_HRP   |   Not Participating Hrp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_ALL_CAU   |   Hrp All Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_DISCOVER_CAU   |   Hrp Discover Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_VISA_CAU   |   Hrp Visa Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARTICIPATING_HRP   |   Participating Hrp        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_MC_DISCOVER_CAU   |   Hrp Mc Discover Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_NC_CAU   |   Hrp Nc Cau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HRP_VISA_DISCOVER_CAU   |   Hrp Visa Discover Cau        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### referencedDeposit

---
tags: [referencedDeposit]
---
- Description: Referenced Deposit
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| depositReferenceNumber| Deposit Reference Number        |       |           |    Available     | Required     | Allowed |    NA |    
| referenceNumberType| Reference Number Type        |    ALPHANUMERIC   |   Alphanumeric        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NUMERIC   |   Numeric        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| depositReferenceNumber| Deposit Reference Number        |       |           |    Available     | Required     | Allowed |    NA |    
| referenceNumberType| Reference Number Type        |    ALPHANUMERIC   |   Alphanumeric        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NUMERIC   |   Numeric        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### restrictedUseTransmatchRewards

---
tags: [restrictedUseTransmatchRewards]
---
- Description: Restricted Use Transmatch Rewards Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### retrievalConfig

---
tags: [retrievalConfig]
---
- Description: Retrievals Config
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| email| email address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| reversal24HourProcessIndicator| Reversal 24Hour Process Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| reversalDaylightSavingsIndicator| Reversal Daylight Savings Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| reversalTimeZoneCode| Reversal TimeZone Code        |    BAKER_ISLAND   |   Baker Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EAST_AFRICA   |   East Africa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NEPAL_TIME   |   Nepal Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EASTERN_GREENLAND   |   Eastern Greenland        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAWSON_STANDARD   |   Mawson Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    HAWAII_ALEUTIAN   |   Hawaii Aleutian        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PACIFIC_TIME   |   Pacific Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHRISTMAS_ISLAND   |   Christmas Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_EUROPEAN   |   Central European        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT-0430   |   Gmt 0430        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MARQUESAS_TIME   |   Marquesas Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EASTERN_TIME   |   Eastern Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    INDIAN_STANDARD   |   Indian Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IRAN_DAYLIGHT   |   Iran Daylight        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUS_CENTRAL_SUMMER   |   Aus Central Summer        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_AFRICA   |   Central Africa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MOUNTAIN_TIME   |   Mountain Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    LINE_ISLAND   |   Line Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FIJI_TIME   |   Fiji Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    JAPAN_TIME   |   Japan Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT-0330   |   Gmt 0330        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PHOENIX_ISLAND   |   Phoenix Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PAPAU_NEW_GUINEA   |   Papau New Guinea        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ALASKAN_TIME   |   Alaskan Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_TIME   |   Central Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GREENWICH_MEAN   |   Greenwich Mean        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUSTRAILIAN_CST   |   Austrailian Cst        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GEORGIA_STANDARD   |   Georgia Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NORFOLK_TIME   |   Norfolk Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHINA_TIME   |   China Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    COCOS_ISLAND   |   Cocos Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ATLANTIC_TIME   |   Atlantic Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHATHAM_STANDARD   |   Chatham Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT+1130   |   Gmt+1130        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BRASILIA_DAYLIGHT   |   Brasilia Daylight        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SAMOA_STANDARD   |   Samoa Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BHUTAN_TIME   |   Bhutan Time  |    Available     | Optional     | Allowed |    NA   |
|          -            |                 -                    |    ATLANTIC_DAYLIGHT   |   Atlantic Daylight  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0100   |   G-0100  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0200   |   G-0200  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0400   |   G-0400  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0500   |   G-0500  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0600   |   G-0600  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0700   |   G-0700  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0800   |   G-0800  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0900   |   G-0900  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0930   |   G-0930  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1000   |   G-1000  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1100   |   G-1100  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1200   |   G-1200  |    Available     | Optional     | Allowed |    NA   |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| email| email address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| reversal24HourProcessIndicator| Reversal 24Hour Process Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| reversalDaylightSavingsIndicator| Reversal Daylight Savings Indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| reversalTimeZoneCode| Reversal TimeZone Code        |    BAKER_ISLAND   |   Baker Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EAST_AFRICA   |   East Africa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NEPAL_TIME   |   Nepal Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EASTERN_GREENLAND   |   Eastern Greenland        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAWSON_STANDARD   |   Mawson Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    HAWAII_ALEUTIAN   |   Hawaii Aleutian        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PACIFIC_TIME   |   Pacific Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHRISTMAS_ISLAND   |   Christmas Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_EUROPEAN   |   Central European        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT-0430   |   Gmt 0430        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MARQUESAS_TIME   |   Marquesas Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EASTERN_TIME   |   Eastern Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    INDIAN_STANDARD   |   Indian Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IRAN_DAYLIGHT   |   Iran Daylight        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUS_CENTRAL_SUMMER   |   Aus Central Summer        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_AFRICA   |   Central Africa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MOUNTAIN_TIME   |   Mountain Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    LINE_ISLAND   |   Line Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FIJI_TIME   |   Fiji Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    JAPAN_TIME   |   Japan Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT-0330   |   Gmt 0330        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PHOENIX_ISLAND   |   Phoenix Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PAPAU_NEW_GUINEA   |   Papau New Guinea        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ALASKAN_TIME   |   Alaskan Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CENTRAL_TIME   |   Central Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GREENWICH_MEAN   |   Greenwich Mean        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUSTRAILIAN_CST   |   Austrailian Cst        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GEORGIA_STANDARD   |   Georgia Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NORFOLK_TIME   |   Norfolk Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHINA_TIME   |   China Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    COCOS_ISLAND   |   Cocos Island        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ATLANTIC_TIME   |   Atlantic Time        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHATHAM_STANDARD   |   Chatham Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GMT+1130   |   Gmt+1130        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BRASILIA_DAYLIGHT   |   Brasilia Daylight        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SAMOA_STANDARD   |   Samoa Standard        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BHUTAN_TIME   |   Bhutan Time  |    Available     | Optional     | Allowed |    NA   |
|          -            |                 -                    |    ATLANTIC_DAYLIGHT   |   Atlantic Daylight  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0100   |   G-0100  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0200   |   G-0200  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0400   |   G-0400  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0500   |   G-0500  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0600   |   G-0600  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0700   |   G-0700  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0800   |   G-0800  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0900   |   G-0900  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-0930   |   G-0930  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1000   |   G-1000  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1100   |   G-1100  |    Available     | Optional     | Allowed |    NA   |
|    -    |     -     |    G-1200   |   G-1200  |    Available     | Optional     | Allowed |    NA   |

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### rtp

---
tags: [rtp]
---
- Description: Rtp
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|         status               |          Program Status                           |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|         status               |          Program Status                           |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 

<!--  type: tab-end  -->


### sameDaySettlement

---
tags: [sameDaySettlement]
---
- Description: Same Day Settlement
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| currencyCd| Currency Code        |    EURO   |   Euro        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    GRT_BRITISH_POUND   |   Grt British Pound        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    USA_DOLLAR   |   Usa Dollar        |    Available     | Required     | Allowed |    NA |    
|         status               |          Program Status                           |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| currencyCd| Currency Code        |    EURO   |   Euro        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    CANADIAN_DOLLAR   |   Canadian Dollar        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    GRT_BRITISH_POUND   |   Grt British Pound        |    Available     | Required     | Allowed |    NA |    
| currencyCd| Currency Code        |    USA_DOLLAR   |   Usa Dollar        |    Available     | Required     | Allowed |    NA |    
|         status               |          Program Status                           |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### selectiveDivert

---
tags: [selectiveDivert]
---
- Description: Negative Bankwire Selective Divert
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|         status               |          Program Status                           |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|         status               |          Program Status                           |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### settlementConfig

---
tags: [settlementConfig]
---
- Description: Settlement Config
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billbackCode| Billback Code        |    AUTO_BILLBK_OFF   |   Auto Billbk Off        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    LEGACY   |   Legacy        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_ON   |   Auto Billbk On        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_WITH_REVERSAL   |   Auto Billbk With Reversal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_AUTO_BILLBK   |   Not Auto Billbk        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_NO_REVERSAL   |   Auto Billbk No Reversal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUEL_CARD   |   Fuel Card        |    Available     | Optional     | Allowed |    NA |
| billbackHierarchyCode| Billback Hierarchy Code        |    OUTLET   |   Outlet        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHAIN   |   Chain        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BANK   |   Bank        |    Available     | Optional     | Allowed |    NA |
| billbackRoundingIndicator| Bill Back Rounding Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| billbackSurchargeCode| Billback Surcharge Code        |    AUTO_BILL_SRCHRG_BSNS   |   Auto Bill Srchrg Bsns        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUEL_CARD_PALN_CODE_VI   |   Fuel Card Paln Code Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EXCLUDE_AUTO_FUEL_VI   |   Exclude Auto Fuel Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GOVT_PLAN_CODE_VI   |   Govt Plan Code Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CORP_CARD_PLAN_CODE_MC_VI   |   Corp Card Plan Code Mc Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    COMMERCIAL_CARD_PLAN_CODE_MC_VI   |   Commercial Card Plan Code Mc Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_AUTO_BILL_SRCHRG   |   No Auto Bill Srchrg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLSRCHRG_MER   |   Auto Billsrchrg Mer        |    Available     | Optional     | Allowed |    NA |
| processingTypeCode| Processing Type Code        |    PAPER_TERMINAL   |   Paper Terminal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EDC   |   Edc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CASH_ADV_OUTLET_ON_US   |   Cash Adv Outlet On Us        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DIRECT_SOLUTIONS   |   Direct Solutions        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUNDING_ACCT   |   Funding Acct        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ECR   |   Ecr        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TAPE_DEPOSITOR   |   Tape Depositor        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PAPER_VOICE   |   Paper Voice        |    Available     | Optional     | Allowed |    NA |
| settleFrequencyCode| Settle Frequency Code        |    AT_SETTLEMENT   |   At Settlement        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DAILY_DISC   |   Daily Disc        |    Available     | Optional     | Allowed |    NA |
|    -    |    -    |    2X_WEEKLY_CHAIN   |   2X Weekly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_WEEKLY_OUTLET   |   2X Weekly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    WEEKLY_CHECK_CHAIN   |   Weekly Check Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    WEEKLY_CHECK_OUTLET   |   Weekly Check Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_MONTHLY_CHAIN   |   2X Monthly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_MONTHLY_OUTLET   |   2X Monthly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    MONTHLY_CHAIN   |   Monthly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    MONTHLY_OUTLET   |   Monthly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    FLEX_FUND   |   Flex Fund   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    FLEX_FUND_ONUS   |   Flex Fund Onus   |    Available     | Optional     | Allowed |    NA    |
| surchargeExceptionCode| Determine If A Billback Surcharge Should Be Applied        |    NO_SCHG_VISA_SIG_COMM   |   No Schg Visa Sig Comm        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_INF_MC   |   No Schg Visa Inf Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_SIG_MC   |   No Schg Visa Sig Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_INF_COMM   |   No Schg Visa Inf Comm        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ALLOW_SCHG   |   Allow Schg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SPEC_SCHG_VISA_INF_COMM   |   Special Schg Visa Inf Comm F20A        |    Available     | Optional     | Allowed |    NA |
| chargeBarer| Charge Barer for Omnipay |    CRED | Creditor pays all charges | Available | Optional | Allowed |  NA |
|   -   |  -  |    SLEV | Charges Follow The Service Level; The Only Allowed Alternative For Sepa Payments  |    Available     | Optional     | Allowed |  NA |  
|  -  |  -  |    DEBT |    Debt - Debtor Pays All Charges        |    Available     | Optional     | Allowed |  NA |  
|  -  |  -  |    SHAR | Shar - Debtor And Creditor Pay Their Own Charges |    Available     | Optional  | Allowed |  NA |
| dcc| DCC Merchant for Omnipay        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| settlementMethod| The settlement method assigned to for the merchant        |    IFS_MONTHLY_NEG   |   Ifs Monthly Neg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DE_DAILY_CUP   |   De Daily Cup        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DAILY   |   Daily        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IFS_DAILY_CUP   |   Ifs Daily Cup        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DE_DAILY   |   De Daily        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IFS_TREASURY   |   Ifs Treasury        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IFS_DAILY   |   Ifs Daily        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IFS_DAILY_NEG   |   Ifs Daily Neg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DAILY_CUP   |   Daily Cup        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    IFS_DAILY_NEG_CUP   |   Ifs Daily Neg Cup        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billbackCode| Billback Code        |    AUTO_BILLBK_OFF   |   Auto Billbk Off        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    LEGACY   |   Legacy        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_ON   |   Auto Billbk On        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_WITH_REVERSAL   |   Auto Billbk With Reversal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_AUTO_BILLBK   |   Not Auto Billbk        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLBK_NO_REVERSAL   |   Auto Billbk No Reversal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUEL_CARD   |   Fuel Card        |    Available     | Optional     | Allowed |    NA |
| billbackHierarchyCode| Billback Hierarchy Code        |    OUTLET   |   Outlet        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CHAIN   |   Chain        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BANK   |   Bank        |    Available     | Optional     | Allowed |    NA |
| billbackRoundingIndicator| Bill Back Rounding Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| billbackSurchargeCode| Billback Surcharge Code        |    AUTO_BILL_SRCHRG_BSNS   |   Auto Bill Srchrg Bsns        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_SPECIFIED   |   Not Specified        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUEL_CARD_PALN_CODE_VI   |   Fuel Card Paln Code Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EXCLUDE_AUTO_FUEL_VI   |   Exclude Auto Fuel Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    GOVT_PLAN_CODE_VI   |   Govt Plan Code Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CORP_CARD_PLAN_CODE_MC_VI   |   Corp Card Plan Code Mc Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    COMMERCIAL_CARD_PLAN_CODE_MC_VI   |   Commercial Card Plan Code Mc Vi        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_AUTO_BILL_SRCHRG   |   No Auto Bill Srchrg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    AUTO_BILLSRCHRG_MER   |   Auto Billsrchrg Mer        |    Available     | Optional     | Allowed |    NA |
| processingTypeCode| Processing Type Code        |    PAPER_TERMINAL   |   Paper Terminal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EDC   |   Edc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CASH_ADV_OUTLET_ON_US   |   Cash Adv Outlet On Us        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DIRECT_SOLUTIONS   |   Direct Solutions        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FUNDING_ACCT   |   Funding Acct        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ECR   |   Ecr        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TAPE_DEPOSITOR   |   Tape Depositor        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PAPER_VOICE   |   Paper Voice        |    Available     | Optional     | Allowed |    NA |
| settleFrequencyCode| Settle Frequency Code        |    AT_SETTLEMENT   |   At Settlement        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DAILY_DISC   |   Daily Disc        |    Available     | Optional     | Allowed |    NA |
|    -    |    -    |    2X_WEEKLY_CHAIN   |   2X Weekly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_WEEKLY_OUTLET   |   2X Weekly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    WEEKLY_CHECK_CHAIN   |   Weekly Check Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    WEEKLY_CHECK_OUTLET   |   Weekly Check Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_MONTHLY_CHAIN   |   2X Monthly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    2X_MONTHLY_OUTLET   |   2X Monthly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    MONTHLY_CHAIN   |   Monthly Chain   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    MONTHLY_OUTLET   |   Monthly Outlet   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    FLEX_FUND   |   Flex Fund   |    Available     | Optional     | Allowed |    NA    |
|    -    |    -    |    FLEX_FUND_ONUS   |   Flex Fund Onus   |    Available     | Optional     | Allowed |    NA    |
| surchargeExceptionCode| Determine If A Billback Surcharge Should Be Applied        |    NO_SCHG_VISA_SIG_COMM   |   No Schg Visa Sig Comm        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_INF_MC   |   No Schg Visa Inf Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_SIG_MC   |   No Schg Visa Sig Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SCHG_VISA_INF_COMM   |   No Schg Visa Inf Comm        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ALLOW_SCHG   |   Allow Schg        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SPEC_SCHG_VISA_INF_COMM   |   Special Schg Visa Inf Comm F20A        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billbackIndicatorCode| Billback Indicator Code        |       |           |    Available     | Required     | Allowed |    NA |    
| chargeBarer| Charge Barer for Omnipay        |    CRED - Creditor pays all charges        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLEV - Charges follow the service level; the only allowed alternative for Sepa payments      |    Slev - Charges Follow The Service Level; The Only Allowed Alternative For Sepa Payments        |    Available     | Required     | Allowed |    NA |  
|          -            |                 -                    |    DEBT - Debtor pays all charges      |    Debt - Debtor Pays All Charges        |    Available     | Required     | Allowed |    NA |  
|          -            |                 -                    |    SHAR - Debtor and Creditor pay their own charges   |   Cred - Creditor Pays All Charges      |    Shar - Debtor And Creditor Pay Their Own Charges        |    Available     | Required     | Allowed |    NA |  

| dcc| DCC Merchant for Omnipay        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| settlementMethod| The settlement method assigned to for the merchant        |    IFS_MONTHLY_NEG   |   Ifs Monthly Neg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DE_DAILY_CUP   |   De Daily Cup        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DAILY   |   Daily        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IFS_DAILY_CUP   |   Ifs Daily Cup        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DE_DAILY   |   De Daily        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IFS_TREASURY   |   Ifs Treasury        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IFS_DAILY   |   Ifs Daily        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IFS_DAILY_NEG   |   Ifs Daily Neg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DAILY_CUP   |   Daily Cup        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IFS_DAILY_NEG_CUP   |   Ifs Daily Neg Cup        |    Available     | Required     | Allowed |    NA |    


<!--  type: tab-end  -->

### signatureCapture

---
tags: [signatureCapture]
---
- Description: Signature Capture
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| signatureCaptureIndicator| Signature Capture Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| signatureCaptureRejectsIndicator| Signature Capture Rejects Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| signatureCaptureIndicator| Signature Capture Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| signatureCaptureRejectsIndicator| Signature Capture Rejects Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO   |   No        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### southFrontEndBridge

---
tags: [southFrontEndBridge]
---
- Description: Sfe Sunset Bridge Merchant Conversions
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          status         |           Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          status         |           Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### southHdcLateCutC

---
tags: [southHdcLateCutC]
---
- Description: South Platform Hdc Late Batch Cut C
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          status         |           Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          status         |           Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### statementConfig

---
tags: [statementConfig]
---
- Description: Statement Config
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cardAlternateCity| Card Alternate City        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| cardAlternateName| Card Alternate Name        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| cardAlternateStateCode| Card Alternate State Code        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| email| Statement email address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| icplusStatementFormatCode| Code determining the interchange fee information the System prints on the merchant statement        |    ICPLUS_LONG_STMT   |   Icplus Long Stmt        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| statementDeliveryCode| Statement delivery method        |    BULK_MAIL   |   Bulk Mail  |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    HOLD   |   Hold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PRINT   |   Print        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ONLINE   |   Online        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EMAIL   |   Email        |    Available     | Optional     | Allowed |    NA |
| statementFaxIndicator| Statement Fax Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| statementFaxNumber| Statement fax number        |    STRING (max - 15/min length - 10)   |   String (Max - 15/Min Length - 10)        |    Available     | Optional     | Allowed |    NA |
| statementMailToCode| Indicates where printed statement will be sent        |    RECAP_CORP_STMT_OUTLET   |   Recap Corp Stmt Outlet        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_CORP_NO_RECAP   |   Mail To Corp No Recap        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SUPP_STMT_RECAP   |   Supp Stmt Recap        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_CORP   |   Mail To Corp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RECAP_NO_STMT   |   Recap No Stmt        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_OUTLET   |   Mail To Outlet        |    Available     | Optional     | Allowed |    NA |
|   -   |    -    |    ROLLUP_TO_OUTLET   |   RollUp To Outlet   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    ROLLUP_TO_CHAIN   |   RollUp To Chain   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    ROLLUP_TO_CORPORATION   |   RollUp To Corporation   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    DBA_RECAP_BILL_TO   |   DBA Recap Bill To   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    18   |   Value - 18   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    19   |   Value - 19   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    20   |   Value - 20   |    Available     | Optional     | Allowed |    NA   |
| statementTypeCode| Statement type summary or detail        |    FISERV_DETAIL   |   Fiserv Detail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FISERV_SUMMUARY   |   Fiserv Summuary        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONCORD_SUMMARY   |   Concord Summary        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONCORD_DETAIL   |   Concord Detail        |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    PTI   |   PTI   |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    FDMS   |   FDMS  |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    BAMS_CHAIN_SUMMARY   |   BAMS Chain Summary  |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cardAlternateCity| Card Alternate City        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| cardAlternateName| Card Alternate Name        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| cardAlternateStateCode| Card Alternate State Code        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| email| Statement email address        |    STRING   |   String        |    Available     | Optional     | Allowed |    NA |
| icplusStatementFormatCode| Code determining the interchange fee information the System prints on the merchant statement        |    ICPLUS_LONG_STMT   |   Icplus Long Stmt        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
| statementDeliveryCode| Statement delivery method        |    BULK_MAIL   |   Bulk Mail  |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL   |   Mail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    HOLD   |   Hold        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PRINT   |   Print        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ONLINE   |   Online        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    EMAIL   |   Email        |    Available     | Optional     | Allowed |    NA |
| statementFaxIndicator| Statement Fax Indicator        |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| statementFaxNumber| Statement fax number        |    STRING (max - 15/min length - 10)   |   String (Max - 15/Min Length - 10)        |    Available     | Optional     | Allowed |    NA |
| statementMailToCode| Indicates where printed statement will be sent        |    RECAP_CORP_STMT_OUTLET   |   Recap Corp Stmt Outlet        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_CORP_NO_RECAP   |   Mail To Corp No Recap        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SUPP_STMT_RECAP   |   Supp Stmt Recap        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_CORP   |   Mail To Corp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    RECAP_NO_STMT   |   Recap No Stmt        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAIL_TO_OUTLET   |   Mail To Outlet        |    Available     | Optional     | Allowed |    NA |
|   -   |    -    |    ROLLUP_TO_OUTLET   |   RollUp To Outlet   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    ROLLUP_TO_CHAIN   |   RollUp To Chain   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    ROLLUP_TO_CORPORATION   |   RollUp To Corporation   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    DBA_RECAP_BILL_TO   |   DBA Recap Bill To   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    18   |   Value - 18   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    19   |   Value - 19   |    Available     | Optional     | Allowed |    NA   |
|   -   |    -    |    20   |   Value - 20   |    Available     | Optional     | Allowed |    NA   |
| statementTypeCode| Statement type summary or detail        |    FISERV_DETAIL   |   Fiserv Detail        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FISERV_SUMMUARY   |   Fiserv Summuary        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONCORD_SUMMARY   |   Concord Summary        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONCORD_DETAIL   |   Concord Detail        |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    PTI   |   PTI   |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    FDMS   |   FDMS  |    Available     | Optional     | Allowed |    NA |
|   -   |    -   |    BAMS_CHAIN_SUMMARY   |   BAMS Chain Summary  |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### stockExchange

---
tags: [stockExchange]
---
- Description: Stock Exchange/Ctry Name
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| countryName| Country Name        |    GUADELOUPE   |   Guadeloupe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIBRALTAR   |   Gibraltar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GHANA   |   Ghana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GABON   |   Gabon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FAROE_ISLANDS   |   Faroe Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FIJI   |   Fiji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANGOLA   |   Angola        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAMIBIA   |   Namibia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIECHTENSTEIN   |   Liechtenstein        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUNISIA   |   Tunisia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONTSERRAT   |   Montserrat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIBYA   |   Libya        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BULGARIA   |   Bulgaria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAYOTTE   |   Mayotte        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAURITANIA   |   Mauritania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALDIVES   |   Maldives        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LITHUANIA   |   Lithuania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LAOS   |   Laos        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIRGIN_ISLANDS_BRITI   |   Virgin Islands Briti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOREA_SOUTH   |   Korea South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOREA_NORTH   |   Korea North        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JARVIS_ISLAND   |   Jarvis Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAMAICA   |   Jamaica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INDONESIA   |   Indonesia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HUNGARY   |   Hungary        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUINEA   |   Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WALLIS_AND_FUTUNA   |   Wallis And Futuna        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOLIVIA   |   Bolivia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHUTAN   |   Bhutan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAMEROON   |   Cameroon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWEDEN   |   Sweden        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SYRIA   |   Syria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TANZANIA   |   Tanzania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VENEZUELA   |   Venezuela        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIMOR_LESTE   |   Timor Leste        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINT_MAARTEN   |   Sint Maarten        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUVALU   |   Tuvalu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_STATES   |   United States        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHILE   |   Chile        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CLIPPERTON_ISLAND   |   Clipperton Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONGO_KINSHASA   |   Congo Kinshasa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EQUATORIAL_GUINEA   |   Equatorial Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THAILAND   |   Thailand        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANTIGUA_AND_BARBUDA   |   Antigua And Barbuda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIETNAM   |   Vietnam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAMBIA   |   Zambia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N/A   |   N/A        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DENMARK   |   Denmark        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DHEKELIA   |   Dhekelia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EL_SALVADOR   |   El Salvador        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAMOA   |   Samoa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESTONIA   |   Estonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ETHIOPIA   |   Ethiopia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VANUATU   |   Vanuatu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELARUS   |   Belarus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ASHMORE_N_CARTIER_ISL   |   Ashmore N Cartier Isl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARMENIA   |   Armenia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARGENTINA   |   Argentina        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SRI_LANKA   |   Sri Lanka        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WAKE_ISLAND   |   Wake Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIRGIN_ISLANDS_US   |   Virgin Islands Us        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKEY   |   Turkey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TOGO   |   Togo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    URUGUAY   |   Uruguay        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_KINGDOM   |   United Kingdom        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKS_AND_CAICOS_ISLA   |   Turks And Caicos Isla        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOLOMON_ISLANDS   |   Solomon Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TRINIDAD_AND_TOBAGO   |   Trinidad And Tobago        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TOKELAU   |   Tokelau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVALBARD   |   Svalbard        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARUBA   |   Aruba        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPRATLY_ISLANDS   |   Spratly Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPAIN   |   Spain        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_SUDAN   |   South Sudan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AZERBAIJAN   |   Azerbaijan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GREECE   |   Greece        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLOVAKIA   |   Slovakia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGAPORE   |   Singapore        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SERBIA   |   Serbia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PANAMA   |   Panama        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_PIERRE_N_MIQUEL   |   Saint Pierre N Miquel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JERSEY   |   Jersey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KIRIBATI   |   Kiribati        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOMALIA   |   Somalia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SURINAME   |   Suriname        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEYCHELLES   |   Seychelles        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_KITTS_AND_NEVIS   |   Saint Kitts And Nevis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    POLAND   |   Poland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAJIKISTAN   |   Tajikistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BARBADOS   |   Barbados        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURUNDI   |   Burundi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_POLYNESIA   |   French Polynesia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GAMBIA_THE   |   Gambia The        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GERMANY   |   Germany        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UKRAINE   |   Ukraine        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALTA   |   Malta        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRANCE   |   France        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAUDI_ARABIA   |   Saudi Arabia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UGANDA   |   Uganda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_AFRICA   |   South Africa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALESTINIAN_TERRITORY   |   Palestinian Territory        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARACEL_ISLANDS   |   Paracel Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PERU   |   Peru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PORTUGAL   |   Portugal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZIMBABWE   |   Zimbabwe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_LUCIA   |   Saint Lucia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SIERRA_LEONE   |   Sierra Leone        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWITZERLAND   |   Switzerland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PHILIPPINES   |   Philippines        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_GEORGIA_N_S_SAN   |   South Georgia N S San        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UZBEKISTAN   |   Uzbekistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_ARAB_EMIRATES   |   United Arab Emirates        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKMENISTAN   |   Turkmenistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TONGA   |   Tonga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUDAN   |   Sudan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAIWAN   |   Taiwan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COOK_ISLANDS   |   Cook Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLOVENIA   |   Slovenia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_VINCENT_N_THE_G   |   Saint Vincent N The G        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SENEGAL   |   Senegal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAO_TOME_AND_PRINCIPE   |   Sao Tome And Principe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAN_MARINO   |   San Marino        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_MARTIN   |   Saint Martin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALAU   |   Palau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RUSSIA   |   Russia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ROMANIA   |   Romania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REUNION   |   Reunion        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAKISTAN   |   Pakistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORTH_MACEDONIA   |   North Macedonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIGERIA   |   Nigeria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARSHALL_ISLANDS   |   Marshall Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WESTERN_SAHARA   |   Western Sahara        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HAITI   |   Haiti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOLDOVA   |   Moldova        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KAZAKHSTAN   |   Kazakhstan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAPAN   |   Japan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISRAEL   |   Israel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUINEA_BISSAU   |   Guinea Bissau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUATEMALA   |   Guatemala        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_STHERN_ANTAR   |   French Sthern Antar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDWAY_ISLANDS   |   Midway Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANGUILLA   |   Anguilla        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOROCCO   |   Morocco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAURU   |   Nauru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAVASSA_ISLAND   |   Navassa Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_CALEDONIA   |   New Caledonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MACAU   |   Macau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURMA   |   Burma        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIGER   |   Niger        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALI   |   Mali        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KUWAIT   |   Kuwait        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KENYA   |   Kenya        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JOHNSTON_ATOLL   |   Johnston Atoll        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HONG_KONG   |   Hong Kong        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZ_FALKLAND_ISLANDS   |   Cz Falkland Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ICELAND   |   Iceland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BENIN   |   Benin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMERICAN_SAMOA   |   American Samoa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MEXICO   |   Mexico        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARTINIQUE   |   Martinique        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZECHIA   |   Czechia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LUXEMBOURG   |   Luxembourg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIBERIA   |   Liberia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEBANON   |   Lebanon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LATVIA   |   Latvia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRUNEI   |   Brunei        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISLE_OF_MAN   |   Isle Of Man        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRAQ   |   Iraq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUSTRALIA   |   Australia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANADA   |   Canada        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAMBODIA   |   Cambodia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CABO_VERDE   |   Cabo Verde        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRITISH_INDIAN_OCEAN   |   British Indian Ocean        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AFGHANISTAN   |   Afghanistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KYRGYZSTAN   |   Kyrgyzstan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CENTRAL_AFRICAN_REPUB   |   Central African Repub        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHINA   |   China        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CORAL_SEA_ISLANDS   |   Coral Sea Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COSTA_RICA   |   Costa Rica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CROATIA   |   Croatia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUBA   |   Cuba        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOSNIA_AND_HERZEGOVIN   |   Bosnia And Herzegovin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRAZIL   |   Brazil        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORFOLK_ISLAND   |   Norfolk Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORTHERN_MARIANA_ISLE   |   Northern Mariana Isle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPUA_NEW_GUINEA   |   Papua New Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARAGUAY   |   Paraguay        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QATAR   |   Qatar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALGERIA   |   Algeria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOTSWANA   |   Botswana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JORDAN   |   Jordan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_ZEALAND   |   New Zealand        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BERMUDA   |   Bermuda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELIZE   |   Belize        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELGIUM   |   Belgium        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BANGLADESH   |   Bangladesh        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAKER_ISLAND   |   Baker Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAHRAIN   |   Bahrain        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEPAL   |   Nepal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURKINA_FASO   |   Burkina Faso        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HOWLAND_ISLAND   |   Howland Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HONDURAS   |   Honduras        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HOLY_SEE   |   Holy See        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONGOLIA   |   Mongolia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUAM   |   Guam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_BARTHELEMY   |   Saint Barthelemy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOZAMBIQUE   |   Mozambique        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YEMEN   |   Yemen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALAWI   |   Malawi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALAYSIA   |   Malaysia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAURITIUS   |   Mauritius        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MICRONESIA_FEDERATED   |   Micronesia Federated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONACO   |   Monaco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONTENEGRO   |   Montenegro        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KINGMAN_REEF   |   Kingman Reef        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOMINICA   |   Dominica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LESOTHO   |   Lesotho        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRENADA   |   Grenada        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GEORGIA   |   Georgia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FINLAND   |   Finland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ERITREA   |   Eritrea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ECUADOR   |   Ecuador        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOUVET_ISLAND   |   Bouvet Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIUE   |   Niue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_HELENA_ASCENSI   |   Saint Helena Ascensi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RWANDA   |   Rwanda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PUERTO_RICO   |   Puerto Rico        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PITCAIRN_ISLANDS   |   Pitcairn Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALMYRA_ATOLL   |   Palmyra Atoll        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OMAN   |   Oman        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORWAY   |   Norway        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAHAMAS_THE   |   Bahamas The        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NETHERLANDS   |   Netherlands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AKROTIRI   |   Akrotiri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRAN   |   Iran        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRELAND   |   Ireland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ITALY   |   Italy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAN_MAYEN   |   Jan Mayen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MADAGASCAR   |   Madagascar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMOROS   |   Comoros        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DJIBOUTI   |   Djibouti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUSTRIA   |   Austria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAYMAN_ISLANDS   |   Cayman Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANTARCTICA   |   Antarctica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALBANIA   |   Albania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INDIA   |   India        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANDORRA   |   Andorra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GREENLAND   |   Greenland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NICARAGUA   |   Nicaragua        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EGYPT   |   Egypt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONGO_BRAZZAVILLE   |   Congo Brazzaville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CURAÇAO   |   Curaçao        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOMINICAN_REPUBLIC   |   Dominican Republic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHAD   |   Chad        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHRISTMAS_ISLAND   |   Christmas Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COLOMBIA   |   Colombia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HEARD_ISLAND_AND_MCD   |   Heard Island And Mcd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUYANA   |   Guyana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COCOS_KEELING_ISLAND   |   Cocos Keeling Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUERNSEY   |   Guernsey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOSOVO   |   Kosovo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_GUIANA   |   French Guiana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESWATINI   |   Eswatini        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYPRUS   |   Cyprus        |    Available     | Required     | Allowed |    NA |    
| stockExchangeName| Stock Exchange Name        |    EDGA_EXCHANGE_INC   |   Edga Exchange Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDGX_EXCHANGE_INC   |   Edgx Exchange Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASDAQ_OMX_BX_INC   |   Nasdaq Omx Bx Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHICAGO_BOARD_OPTIONS   |   Chicago Board Options        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL_STOCK_EXCHG   |   National Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INTERNATIONAL_SECURITY   |   International Security        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N/A   |   N/A        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASDAQ_OMX_PHLX_INC   |   Nasdaq Omx Phlx Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHICAGO_STOCK_EXCHG   |   Chicago Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C2_OPTIONS_EXCHG_INC   |   C2 Options Exchg Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THE_NASDAQ_STOCK_MKT   |   The Nasdaq Stock Mkt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NYSE_ARCA_INC   |   Nyse Arca Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NYSE_MKT_LLC   |   Nyse Mkt Llc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_YORK_STOCK_EXCHG   |   New York Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BATS_EXCHANGE_INC_F2   |   Bats Exchange Inc F2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BATS_Y_EXCHANGE_INC   |   Bats Y Exchange Inc        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| countryName| Country Name        |    GUADELOUPE   |   Guadeloupe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GIBRALTAR   |   Gibraltar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GHANA   |   Ghana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GABON   |   Gabon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FAROE_ISLANDS   |   Faroe Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FIJI   |   Fiji        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANGOLA   |   Angola        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAMIBIA   |   Namibia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIECHTENSTEIN   |   Liechtenstein        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUNISIA   |   Tunisia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONTSERRAT   |   Montserrat        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIBYA   |   Libya        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BULGARIA   |   Bulgaria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAYOTTE   |   Mayotte        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAURITANIA   |   Mauritania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALDIVES   |   Maldives        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LITHUANIA   |   Lithuania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LAOS   |   Laos        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIRGIN_ISLANDS_BRITI   |   Virgin Islands Briti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOREA_SOUTH   |   Korea South        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOREA_NORTH   |   Korea North        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JARVIS_ISLAND   |   Jarvis Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAMAICA   |   Jamaica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INDONESIA   |   Indonesia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HUNGARY   |   Hungary        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUINEA   |   Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WALLIS_AND_FUTUNA   |   Wallis And Futuna        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOLIVIA   |   Bolivia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BHUTAN   |   Bhutan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAMEROON   |   Cameroon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWEDEN   |   Sweden        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SYRIA   |   Syria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TANZANIA   |   Tanzania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VENEZUELA   |   Venezuela        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TIMOR_LESTE   |   Timor Leste        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINT_MAARTEN   |   Sint Maarten        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TUVALU   |   Tuvalu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_STATES   |   United States        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHILE   |   Chile        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CLIPPERTON_ISLAND   |   Clipperton Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONGO_KINSHASA   |   Congo Kinshasa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EQUATORIAL_GUINEA   |   Equatorial Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THAILAND   |   Thailand        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANTIGUA_AND_BARBUDA   |   Antigua And Barbuda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIETNAM   |   Vietnam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZAMBIA   |   Zambia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N/A   |   N/A        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DENMARK   |   Denmark        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DHEKELIA   |   Dhekelia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EL_SALVADOR   |   El Salvador        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAMOA   |   Samoa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESTONIA   |   Estonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ETHIOPIA   |   Ethiopia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VANUATU   |   Vanuatu        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELARUS   |   Belarus        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ASHMORE_N_CARTIER_ISL   |   Ashmore N Cartier Isl        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARMENIA   |   Armenia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARGENTINA   |   Argentina        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SRI_LANKA   |   Sri Lanka        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WAKE_ISLAND   |   Wake Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    VIRGIN_ISLANDS_US   |   Virgin Islands Us        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKEY   |   Turkey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TOGO   |   Togo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    URUGUAY   |   Uruguay        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_KINGDOM   |   United Kingdom        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKS_AND_CAICOS_ISLA   |   Turks And Caicos Isla        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOLOMON_ISLANDS   |   Solomon Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TRINIDAD_AND_TOBAGO   |   Trinidad And Tobago        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TOKELAU   |   Tokelau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SVALBARD   |   Svalbard        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ARUBA   |   Aruba        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPRATLY_ISLANDS   |   Spratly Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SPAIN   |   Spain        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_SUDAN   |   South Sudan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AZERBAIJAN   |   Azerbaijan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GREECE   |   Greece        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLOVAKIA   |   Slovakia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SINGAPORE   |   Singapore        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SERBIA   |   Serbia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PANAMA   |   Panama        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_PIERRE_N_MIQUEL   |   Saint Pierre N Miquel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JERSEY   |   Jersey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KIRIBATI   |   Kiribati        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOMALIA   |   Somalia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SURINAME   |   Suriname        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SEYCHELLES   |   Seychelles        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_KITTS_AND_NEVIS   |   Saint Kitts And Nevis        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    POLAND   |   Poland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAJIKISTAN   |   Tajikistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BARBADOS   |   Barbados        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURUNDI   |   Burundi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_POLYNESIA   |   French Polynesia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GAMBIA_THE   |   Gambia The        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GERMANY   |   Germany        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UKRAINE   |   Ukraine        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALTA   |   Malta        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRANCE   |   France        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAUDI_ARABIA   |   Saudi Arabia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UGANDA   |   Uganda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_AFRICA   |   South Africa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALESTINIAN_TERRITORY   |   Palestinian Territory        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARACEL_ISLANDS   |   Paracel Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PERU   |   Peru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PORTUGAL   |   Portugal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ZIMBABWE   |   Zimbabwe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_LUCIA   |   Saint Lucia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SIERRA_LEONE   |   Sierra Leone        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SWITZERLAND   |   Switzerland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PHILIPPINES   |   Philippines        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SOUTH_GEORGIA_N_S_SAN   |   South Georgia N S San        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UZBEKISTAN   |   Uzbekistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    UNITED_ARAB_EMIRATES   |   United Arab Emirates        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TURKMENISTAN   |   Turkmenistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TONGA   |   Tonga        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SUDAN   |   Sudan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    TAIWAN   |   Taiwan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COOK_ISLANDS   |   Cook Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SLOVENIA   |   Slovenia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_VINCENT_N_THE_G   |   Saint Vincent N The G        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SENEGAL   |   Senegal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAO_TOME_AND_PRINCIPE   |   Sao Tome And Principe        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAN_MARINO   |   San Marino        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_MARTIN   |   Saint Martin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALAU   |   Palau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RUSSIA   |   Russia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ROMANIA   |   Romania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REUNION   |   Reunion        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAKISTAN   |   Pakistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORTH_MACEDONIA   |   North Macedonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIGERIA   |   Nigeria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARSHALL_ISLANDS   |   Marshall Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WESTERN_SAHARA   |   Western Sahara        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HAITI   |   Haiti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOLDOVA   |   Moldova        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KAZAKHSTAN   |   Kazakhstan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAPAN   |   Japan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISRAEL   |   Israel        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUINEA_BISSAU   |   Guinea Bissau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUATEMALA   |   Guatemala        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_STHERN_ANTAR   |   French Sthern Antar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MIDWAY_ISLANDS   |   Midway Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANGUILLA   |   Anguilla        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOROCCO   |   Morocco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAURU   |   Nauru        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NAVASSA_ISLAND   |   Navassa Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_CALEDONIA   |   New Caledonia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MACAU   |   Macau        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURMA   |   Burma        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIGER   |   Niger        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALI   |   Mali        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KUWAIT   |   Kuwait        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KENYA   |   Kenya        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JOHNSTON_ATOLL   |   Johnston Atoll        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HONG_KONG   |   Hong Kong        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZ_FALKLAND_ISLANDS   |   Cz Falkland Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ICELAND   |   Iceland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BENIN   |   Benin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AMERICAN_SAMOA   |   American Samoa        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MEXICO   |   Mexico        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MARTINIQUE   |   Martinique        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CZECHIA   |   Czechia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LUXEMBOURG   |   Luxembourg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LIBERIA   |   Liberia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LEBANON   |   Lebanon        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LATVIA   |   Latvia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRUNEI   |   Brunei        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ISLE_OF_MAN   |   Isle Of Man        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRAQ   |   Iraq        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUSTRALIA   |   Australia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CANADA   |   Canada        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAMBODIA   |   Cambodia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CABO_VERDE   |   Cabo Verde        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRITISH_INDIAN_OCEAN   |   British Indian Ocean        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AFGHANISTAN   |   Afghanistan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KYRGYZSTAN   |   Kyrgyzstan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CENTRAL_AFRICAN_REPUB   |   Central African Repub        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHINA   |   China        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CORAL_SEA_ISLANDS   |   Coral Sea Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COSTA_RICA   |   Costa Rica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CROATIA   |   Croatia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CUBA   |   Cuba        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOSNIA_AND_HERZEGOVIN   |   Bosnia And Herzegovin        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BRAZIL   |   Brazil        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORFOLK_ISLAND   |   Norfolk Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORTHERN_MARIANA_ISLE   |   Northern Mariana Isle        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PAPUA_NEW_GUINEA   |   Papua New Guinea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PARAGUAY   |   Paraguay        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    QATAR   |   Qatar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALGERIA   |   Algeria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOTSWANA   |   Botswana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JORDAN   |   Jordan        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_ZEALAND   |   New Zealand        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BERMUDA   |   Bermuda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELIZE   |   Belize        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BELGIUM   |   Belgium        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BANGLADESH   |   Bangladesh        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAKER_ISLAND   |   Baker Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAHRAIN   |   Bahrain        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEPAL   |   Nepal        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BURKINA_FASO   |   Burkina Faso        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HOWLAND_ISLAND   |   Howland Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HONDURAS   |   Honduras        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HOLY_SEE   |   Holy See        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONGOLIA   |   Mongolia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUAM   |   Guam        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_BARTHELEMY   |   Saint Barthelemy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MOZAMBIQUE   |   Mozambique        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    YEMEN   |   Yemen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALAWI   |   Malawi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MALAYSIA   |   Malaysia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MAURITIUS   |   Mauritius        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MICRONESIA_FEDERATED   |   Micronesia Federated        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONACO   |   Monaco        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MONTENEGRO   |   Montenegro        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KINGMAN_REEF   |   Kingman Reef        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOMINICA   |   Dominica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    LESOTHO   |   Lesotho        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GRENADA   |   Grenada        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GEORGIA   |   Georgia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FINLAND   |   Finland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ERITREA   |   Eritrea        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ECUADOR   |   Ecuador        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BOUVET_ISLAND   |   Bouvet Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NIUE   |   Niue        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    SAINT_HELENA_ASCENSI   |   Saint Helena Ascensi        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    RWANDA   |   Rwanda        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PUERTO_RICO   |   Puerto Rico        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PITCAIRN_ISLANDS   |   Pitcairn Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    PALMYRA_ATOLL   |   Palmyra Atoll        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    OMAN   |   Oman        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NORWAY   |   Norway        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BAHAMAS_THE   |   Bahamas The        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NETHERLANDS   |   Netherlands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AKROTIRI   |   Akrotiri        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRAN   |   Iran        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    IRELAND   |   Ireland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ITALY   |   Italy        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    JAN_MAYEN   |   Jan Mayen        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    MADAGASCAR   |   Madagascar        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COMOROS   |   Comoros        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DJIBOUTI   |   Djibouti        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    AUSTRIA   |   Austria        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CAYMAN_ISLANDS   |   Cayman Islands        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANTARCTICA   |   Antarctica        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ALBANIA   |   Albania        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INDIA   |   India        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ANDORRA   |   Andorra        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GREENLAND   |   Greenland        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NICARAGUA   |   Nicaragua        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EGYPT   |   Egypt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CONGO_BRAZZAVILLE   |   Congo Brazzaville        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CURAÇAO   |   Curaçao        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    DOMINICAN_REPUBLIC   |   Dominican Republic        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHAD   |   Chad        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHRISTMAS_ISLAND   |   Christmas Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COLOMBIA   |   Colombia        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    HEARD_ISLAND_AND_MCD   |   Heard Island And Mcd        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUYANA   |   Guyana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    COCOS_KEELING_ISLAND   |   Cocos Keeling Island        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    GUERNSEY   |   Guernsey        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    KOSOVO   |   Kosovo        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    FRENCH_GUIANA   |   French Guiana        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ESWATINI   |   Eswatini        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CYPRUS   |   Cyprus        |    Available     | Required     | Allowed |    NA |    
| stockExchangeName| Stock Exchange Name        |    EDGA_EXCHANGE_INC   |   Edga Exchange Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EDGX_EXCHANGE_INC   |   Edgx Exchange Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASDAQ_OMX_BX_INC   |   Nasdaq Omx Bx Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHICAGO_BOARD_OPTIONS   |   Chicago Board Options        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NATIONAL_STOCK_EXCHG   |   National Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    INTERNATIONAL_SECURITY   |   International Security        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    N/A   |   N/A        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NASDAQ_OMX_PHLX_INC   |   Nasdaq Omx Phlx Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    CHICAGO_STOCK_EXCHG   |   Chicago Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    C2_OPTIONS_EXCHG_INC   |   C2 Options Exchg Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    THE_NASDAQ_STOCK_MKT   |   The Nasdaq Stock Mkt        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NYSE_ARCA_INC   |   Nyse Arca Inc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NYSE_MKT_LLC   |   Nyse Mkt Llc        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NEW_YORK_STOCK_EXCHG   |   New York Stock Exchg        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BATS_EXCHANGE_INC_F2   |   Bats Exchange Inc F2        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    BATS_Y_EXCHANGE_INC   |   Bats Y Exchange Inc        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### sunocoAutoboarding

---
tags: [sunocoAutoboarding]
---
- Description: Sunoco Autoboarding
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| posPartnerName| Pos Partner Name        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| rollback5CentIndicator| Rollback 5 Cent Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| posPartnerName| Pos Partner Name        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| rollback5CentIndicator| Rollback 5 Cent Indicator        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### transactionControl

---
tags: [transactionControl]
---
- Description: Transaction Control
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cardActivatedTerminalCode| Merchant identified type of cardholders activated terminals that will be accepted         |    No   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    Yes   |   Yes        |    Available     | Optional     | Allowed |    NA |
| commercialCardInterchangeServiceCode| Indicates the level of participation in the mastercard or visa commercial card interchange service        |    DERIVE_TAX_MC   |   Derive Tax Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_PARTICIPATING   |   Not Participating        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DERIVE_TAX_VISA   |   Derive Tax Visa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DERIVE_TAX_MC_VISA   |   Derive Tax Mc Visa        |    Available     | Optional     | Allowed |    NA |
| efraudServiceCode| EFraud Service level code        |    BASIC   |   Basic        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DEACTIVATE_SERVICE   |   Deactivate Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PREMIUM   |   Premium        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PREMIUM_PLUS   |   Premium Plus        |    Available     | Optional     | Allowed |    NA |
| fraudFlexEffectiveDate| Fraud Flex Effective Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fraudFlexIndicator| Fraud Flex Detect Indicator        |    FRAUD_SCORE_PROD   |   Fraud Score Prod        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_FRAUD_SCORE   |   No Fraud Score        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FRAUS_SCORE_CERT   |   Fraus Score Cert        |    Available     | Optional     | Allowed |    NA |
|   -   |     -    |    PAYEEZY   |   Payeezy        |    Available     | Optional     | Allowed |    NA |
| globalGatewayE4EffectiveDate| Payeezy gateway effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| globalGatewayE4Indicator |  Indicates if the merchant uses the Payeezy Gateway  |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    STAGED   |   Staged        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| mastercardIramIndicator| Mastercard Incremental Reversal Auth Match indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| mastercardTieredMerchantId| Mastercard tiered merchant ID        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| visaDebitAcceptIndicator| Describes level of Visa Debit Acceptance         |    VISA_DEBIT_POS   |   Visa Debit Pos        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    VISA_DEBIT_CNP   |   Visa Debit Cnp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_VISA_DEBIT   |   No Visa Debit        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    VISA_DEBIT_ALL   |   Visa Debit All        |    Available     | Optional     | Allowed |    NA |
| visaIramIndicator| Visa Incremental Reversal Auth Match indicator         |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| visaMerchantVerificationValue| Visa merchant verification value        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| visaMviReserveAmount| VISA MVI Reserve amount        |    STRING containing digits with decimal. Format: 00.00   |   String Containing Digits With Decimal. Format: 00.00        |    Available     | Optional     | Allowed |    NA |
| visaRelationshipIndicator| Visa relationship particpant indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramAuthSourceCode| Visa Technology Migration Program  authorization source code        |    OFFLINE   |   Offline        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    REFFERAL   |   Refferal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONTMP_NONAPPRVD_TRANS   |   Nontmp Nonapprvd Trans        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ISS_APPRVD   |   Iss Apprvd        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramCardholderIdCode| Visa Technology Migration Program  cardholder ID code        |    UNATTENDED_NOPIN_4   |   Unattended Nopin 4        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    UNATTENDED_NOPIN_3   |   Unattended Nopin 3        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PIN_ENTERED   |   Pin Entered        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SIG_VERIFIED   |   Sig Verified        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramEntryMode| Visa Technology Migration Program terminal entry mode code        |    MAG_STRP_TRACK_READ_XMIT   |   Mag Strp Track Read Xmit        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TERM_NOT_USED   |   Term Not Used        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP_TRACK2   |   Mag Strp Track2        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP_TRACK1   |   Mag Strp Track1        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    KEY_ENTERED   |   Key Entered        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramPointofsaleCapabilityCode| Visa Technology Migration Program terminal capability code         |    CHIP_CARD   |   Chip Card        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    UNKNOWNOWN   |   Unknownown        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP   |   Mag Strp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CARD_DATA_NOT_READ   |   Card Data Not Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OCR_READ   |   Ocr Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONTACTLESS   |   Contactless        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BAR_CODE_READ   |   Bar Code Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TERM_NOT_USED   |   Term Not Used        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramRequestCode| Visa Technology Migration Program request code        |    NOT_TMP_QUAL   |   Not Tmp Qual        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    USE_MASTER_VALUES   |   Use Master Values        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TMP_QUAL   |   Tmp Qual        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramServiceLevelCode| Visa Technology Migration Program service level code        |    SERVICE   |   Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SERVICE   |   No Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TIIF2_M3   |   Tiif2 M3        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cardActivatedTerminalCode| Merchant identified type of cardholders activated terminals that will be accepted         |    No   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    Yes   |   Yes        |    Available     | Optional     | Allowed |    NA |
| commercialCardInterchangeServiceCode| Indicates the level of participation in the mastercard or visa commercial card interchange service        |    DERIVE_TAX_MC   |   Derive Tax Mc        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NOT_PARTICIPATING   |   Not Participating        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DERIVE_TAX_VISA   |   Derive Tax Visa        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DERIVE_TAX_MC_VISA   |   Derive Tax Mc Visa        |    Available     | Optional     | Allowed |    NA |
| efraudServiceCode| EFraud Service level code        |    BASIC   |   Basic        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    DEACTIVATE_SERVICE   |   Deactivate Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PREMIUM   |   Premium        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONE   |   None        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PREMIUM_PLUS   |   Premium Plus        |    Available     | Optional     | Allowed |    NA |
| fraudFlexEffectiveDate| Fraud Flex Effective Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| fraudFlexIndicator| Fraud Flex Detect Indicator        |    FRAUD_SCORE_PROD   |   Fraud Score Prod        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_FRAUD_SCORE   |   No Fraud Score        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    FRAUS_SCORE_CERT   |   Fraus Score Cert        |    Available     | Optional     | Allowed |    NA |
|   -   |     -    |    PAYEEZY   |   Payeezy        |    Available     | Optional     | Allowed |    NA |
| globalGatewayE4EffectiveDate| Payeezy gateway effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Optional     | Allowed |    NA |
| globalGatewayE4Indicator |  Indicates if the merchant uses the Payeezy Gateway  |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    STAGED   |   Staged        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| mastercardIramIndicator| Mastercard Incremental Reversal Auth Match indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| mastercardTieredMerchantId| Mastercard tiered merchant ID        |    STRING containing digits only - MERCHANT ID   |   String Containing Digits Only - Merchant Id        |    Available     | Optional     | Allowed |    NA |
| visaDebitAcceptIndicator| Describes level of Visa Debit Acceptance         |    VISA_DEBIT_POS   |   Visa Debit Pos        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    VISA_DEBIT_CNP   |   Visa Debit Cnp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_VISA_DEBIT   |   No Visa Debit        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    VISA_DEBIT_ALL   |   Visa Debit All        |    Available     | Optional     | Allowed |    NA |
| visaIramIndicator| Visa Incremental Reversal Auth Match indicator         |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| visaMerchantVerificationValue| Visa merchant verification value        |    STRING containing digits only   |   String Containing Digits Only        |    Available     | Optional     | Allowed |    NA |
| visaMviReserveAmount| VISA MVI Reserve amount        |    STRING containing digits with decimal. Format: 00.00   |   String Containing Digits With Decimal. Format: 00.00        |    Available     | Optional     | Allowed |    NA |
| visaRelationshipIndicator| Visa relationship particpant indicator        |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramAuthSourceCode| Visa Technology Migration Program  authorization source code        |    OFFLINE   |   Offline        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    REFFERAL   |   Refferal        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NONTMP_NONAPPRVD_TRANS   |   Nontmp Nonapprvd Trans        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    ISS_APPRVD   |   Iss Apprvd        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramCardholderIdCode| Visa Technology Migration Program  cardholder ID code        |    UNATTENDED_NOPIN_4   |   Unattended Nopin 4        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    UNATTENDED_NOPIN_3   |   Unattended Nopin 3        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    PIN_ENTERED   |   Pin Entered        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    SIG_VERIFIED   |   Sig Verified        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramEntryMode| Visa Technology Migration Program terminal entry mode code        |    MAG_STRP_TRACK_READ_XMIT   |   Mag Strp Track Read Xmit        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TERM_NOT_USED   |   Term Not Used        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP_TRACK2   |   Mag Strp Track2        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP_TRACK1   |   Mag Strp Track1        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    KEY_ENTERED   |   Key Entered        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramPointofsaleCapabilityCode| Visa Technology Migration Program terminal capability code         |    CHIP_CARD   |   Chip Card        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    UNKNOWNOWN   |   Unknownown        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    MAG_STRP   |   Mag Strp        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CARD_DATA_NOT_READ   |   Card Data Not Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    OCR_READ   |   Ocr Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    CONTACTLESS   |   Contactless        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    BAR_CODE_READ   |   Bar Code Read        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TERM_NOT_USED   |   Term Not Used        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramRequestCode| Visa Technology Migration Program request code        |    NOT_TMP_QUAL   |   Not Tmp Qual        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    USE_MASTER_VALUES   |   Use Master Values        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TMP_QUAL   |   Tmp Qual        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    YES   |   Yes        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO   |   No        |    Available     | Optional     | Allowed |    NA |
| visaTechnologyMigrationProgramServiceLevelCode| Visa Technology Migration Program service level code        |    SERVICE   |   Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    NO_SERVICE   |   No Service        |    Available     | Optional     | Allowed |    NA |
|          -            |                 -                    |    TIIF2_M3   |   Tiif2 M3        |    Available     | Optional     | Allowed |    NA |

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### trustKeeper

---
tags: [trustKeeper]
---
- Description: Trust Keeper
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| trustkeeperDate| Trustkeeper Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| trustkeeperIndicator| Trustkeeper Indicator        |    ENROLLED   |   Enrolled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EXPIRED   |   Expired        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_RESPONSE   |   No Response        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REFUSED   |   Refused        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_ENROLLED   |   Not Enrolled        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| trustkeeperDate| Trustkeeper Date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| trustkeeperIndicator| Trustkeeper Indicator        |    ENROLLED   |   Enrolled        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    EXPIRED   |   Expired        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NO_RESPONSE   |   No Response        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    REFUSED   |   Refused        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    NOT_ENROLLED   |   Not Enrolled        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### wfbCanadaEmergingMarkets

---
tags: [wfbCanadaEmergingMarkets]
---
- Description: Wfb Canada Emerging Markets
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType             |       Offering Type           |    DAILY_FANTASY_SPORTS   |   Daily Fantasy Sports        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLINE_GAMBLING   |   Online Gambling        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType             |       Offering Type           |    DAILY_FANTASY_SPORTS   |   Daily Fantasy Sports        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    ONLINE_GAMBLING   |   Online Gambling        |    Available     | Required     | Allowed |    NA |    

<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 


<!--  type: tab-end  -->


### wfbSurcharge

---
tags: [wfbSurcharge]
---
- Description: Wfpg Surcharge Acct
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

**UMM Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType             |       Offering Type           |    EBILL_EXPRESS_SURCHARGE   |   Ebill Express Surcharge        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WFPG_SURCHARGE_ACCT   |   WFPG Surcharge Acct        |    Available     | Required     | Allowed |    NA |   
<!-- type: tab -->

**North Specification**

| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|     offeringType             |       Offering Type           |    EBILL_EXPRESS_SURCHARGE   |   Ebill Express Surcharge        |    Available     | Required     | Allowed |    NA |    
|          -            |                 -                    |    WFPG_SURCHARGE_ACCT   |   WFPG Surcharge Acct        |    Available     | Required     | Allowed |    NA |   
<!-- type: tab -->


**GMA Specification**
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
|          -                   |                 -                                 |               |                                                           |          |          |          |          | 

<!--  type: tab-end  -->
