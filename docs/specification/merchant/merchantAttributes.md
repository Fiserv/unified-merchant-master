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

<!-- type: tab-->
##### UMM Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| incomeTaxCode| Income Tax Code        |       |           |    Available     | Required     | Allowed |    NA |    
| secondaryTaxId| Secondary Tax ID        |       |           |    Available     | Required     | Allowed |    NA |    
| vatTaxCode| VAT Tax Code        |       |           |    Available     | Required     | Allowed |    NA |    

<!-- type: tab-->

##### GMA Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  || incomeTaxCode| Income Tax Code        |       |           |    Available     | Required     | Allowed |    NA |    
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| secondaryTaxId| Secondary Tax ID        |       |           |    Available     | Required     | Allowed |    NA |    
| vatTaxCode| VAT Tax Code        |       |           |    Available     | Required     | Allowed |    NA |    

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

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| adrpCumulativeLimitAmount| Cumulative refund amount on the same card in the past 30 or 60 days         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpCumulativeLimitCount| ADRP cumulative limit count         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| adrpLimitAmount| A dollar limit defined for credits with no offsets         |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    


### authMatchExclusion
---
tags: [authMatchExclusion]
---
- Description: Auth Match Exclusion
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| southAuthMatchExclusion| South Auth Match Exclusion        |    ROOT_LEVEL_MATCHING   |   Root Level Matching        |    Available     | Required     | Allowed |    NA |    
| southAuthMatchExclusion| South Auth Match Exclusion        |    FULL_MID_MATCHING   |   Full Mid Matching        |    Available     | Required     | Allowed |    NA |    



### authSettings
---
tags: [authSettings]
---
- Description: Auth Settings
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| authTypeCode| Auth Type Code        |    NOT_SPECIFIED   |   Not Specified        |    Available     | Required     | Allowed |    NA |    
| authTypeCode| Auth Type Code        |    PRE_AUTHORIZATION   |   Pre Authorization        |    Available     | Required     | Allowed |    NA |    
| authTypeCode| Auth Type Code        |    FINAL_AUTHORIZATION   |   Final Authorization        |    Available     | Required     | Allowed |    NA |    
| transactionCurrency| Transaction Currency         |       |           |    Available     | Required     | Allowed |    NA |    

### avsControl
---
tags: [avsControl]
---
- Description: AVS Control
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| avsAddressIndicator| Address verification service address indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsAddressIndicator| Address verification service address indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsExactIndicator| Address verification service exact indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsExactIndicator| Address verification service exact indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsNoIndicator| Address verification service no indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsNoIndicator| Address verification service no indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsRetryIndicator| Address verification service retry indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsRetryIndicator| Address verification service retry indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsServiceIndicator| Address verification service indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsServiceIndicator| Address verification service indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsUnavailableIndicator| Address verification service unavailable indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsUnavailableIndicator| Address verification service unavailable indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsWholeZipIndicator| Address verification service whole zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsWholeZipIndicator| Address verification service whole zip indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsYesIndicator| Address verification service Yes indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| avsYesIndicator| Address verification service Yes indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsZipIndicator| Address verification service zip indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| avsZipIndicator| Address verification service zip indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    



### bamsDissolutionHoldingsStatus
---
tags: [bamsDissolutionHoldingsStatus]
---
- Description: Bams Dissolution Holdings Status
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    FISERV   |   Fiserv        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    OTHER_ASSIGNED   |   Other Assigned        |    Available     | Required     | Allowed |    NA |    
| offeringType| Offering Type        |    BANK_OF_AMERICA   |   Bank Of America        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ALLOCATED   |   Allocated        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    DORMANT_CANCELLED   |   Dormant Cancelled        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    RESERVED_ATTACHED   |   Reserved Attached        |    Available     | Required     | Allowed |    NA |    



### billingConfig
---
tags: [billingConfig]
---
- Description: Billing cofiguration
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| billSuppliesIndicator| Bill Supplies Indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| billSuppliesIndicator| Bill Supplies Indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| billSuppliesShippingIndicator| Bill supplies shipping and handling indicator        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| delayedBillingEffectiveDate| Delayed billing effective date        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| managementFeeDate| Date that management fee will be charged        |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| membershipFeeDate| Date that membership fees will be charged         |    STRING (max/min length - 10)   |   String (Max/Min Length: 10)        |    Available     | Required     | Allowed |    NA |    
| retailerRateCode| Retailer rate code specific client usage        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| zeroInterchangeIndicator| Zero interchange indicator reserved for international banks only        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    



### billmatrix
---
tags: [billmatrix]
---
- Description: Billmatrix
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    NOT_ACCEPTED   |   Not Accepted        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACCEPTED   |   Accepted        |    Available     | Required     | Allowed |    NA |    



### boardingAdditionalInfo
---
tags: [boardingAdditionalInfo]
---
- Description: Merchant Boarding Additional Information
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| descriptionOfGoods| Description of goods and services sold by the merchant        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    NO   |   No        |    Available     | Required     | Allowed |    NA |    
| homeBasedBusiness| Defines if the merchants business location is the same as his home location        |    YES   |   Yes        |    Available     | Required     | Allowed |    NA |    
| wisoSalesRepId| Sales rep id of the wholesale iso employee        |    STRING   |   String        |    Available     | Required     | Allowed |    NA |    


### cardbrandPassThruFees
---
tags: [cardbrandPassThruFees]
---
- Description: Cardbrand Pass Thru Fees
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    


### cardconnect
---
tags: [cardconnect]
---
- Description: Cardconnect File Identifier
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    



### cashAdvance
---
tags: [cashAdvance]
---
- Description: Cash Advance
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| cashAdvanceLimitAmount| Cash advance Limit Amount        |    REJECT_IF_GTE_100000 - Reject if greater than or equal to 100000  |   Reject If Gte 100000 - Reject If Greater Than Or Equal To 100000        |    Available     | Required     | Allowed |    NA |    
| splitFundingAdvanceAmount| Split Funding Advance Amount        |    STRING - Digits only - no decimal (max length - 9, min - 1)   |   String - Digits Only - No Decimal (Max Length: 9, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    ADV_REPAID   |   Adv Repaid        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    NOT_USED   |   Not Used        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
| splitFundingParticipationCode| Split Funding Participation Code        |    SPLIT_FUNDING   |   Split Funding        |    Available     | Required     | Allowed |    NA |    
| splitFundingPayToMerchantId| Split funding pay to merchant number        |    STRING - Digits only - MERCHANT ID   |   String - Digits Only - Merchant Id        |    Available     | Required     | Allowed |    NA |    
| splitFundingPercent| Split Funding Percentage        |    STRING - Digits only - no decimal (max length - 3, min - 1)   |   String - Digits Only - No Decimal (Max Length: 3, Min Length: 1)        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    MER_ADV_FUNDING   |   Mer Adv Funding        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    FDMCA   |   Fdmca        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    NONE   |   None        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    RAPID_ADV   |   Rapid Adv        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    FUND_TREE   |   Fund Tree        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    ADV_ME   |   Adv Me        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    ADV_ME_INC   |   Adv Me Inc        |    Available     | Required     | Allowed |    NA |    
| splitFundingVendorCode| Split funding cash advance vendor code        |    BIZ2_CREDIT   |   Biz2 Credit        |    Available     | Required     | Allowed |    NA |    



### cashAdvanceProgram
---
tags: [cashAdvanceProgram]
---
- Description: Cash Advance Gl Funding Program
- List of Attributes:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### North Specification
| Attribute                    | Description                                       | Values        | Value Description                                         | Inquiry  | Create   | Update   |  Delete  |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|:--------:|:--------:|:--------:|:--------:|
| offeringType| Offering Type        |    STANDARD_OFFERING   |   Standard Offering        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    CANCEL   |   Cancel        |    Available     | Required     | Allowed |    NA |    
| status| Program Status        |    ACTIVE   |   Active        |    Available     | Required     | Allowed |    NA |    
