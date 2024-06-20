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

##  List of Merchant Attributes 

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification

###### accentIntermedia

|Domain|Domain Description|Attribute Name|Attribute Description |
|------|------------------|--------------|----------------------|
|accentIntermedia|Accent Intermedia|miscInfoText|Misc Info Text|
|accentIntermedia|Accent Intermedia|isEnabled|Is Enabled|
|accentIntermedia|Accent Intermedia|effectiveDate|Effective Date|

|Domain|Domain Description|Attribute Name|Attribute Description |
|------|------------------|--------------|----------------------|
|acknowledgementFilePreference|Acknowledgement File Preference|ackFilePreference|Acknowledgement File Preference|
|additionalBusinessInfo|Additional Business Information|rccCode|Merchant Retailer Category|
|additionalTaxInfo|Additional Tax Information|incomeTaxCode|Income Tax Code|
|additionalTaxInfo|Additional Tax Information|vatTaxCode|VAT Tax Code|
|additionalTaxInfo|Additional Tax Information|secondaryTaxId|Secondary Tax ID|
|adrp|Auto Decision Refund Process|adrpCumulativeLimitAmount|Cumulative refund amount on the same card in the past 30 or 60 days |
|adrp|Auto Decision Refund Process|adrpLimitAmount|A dollar limit defined for credits with no offsets |
|adrp|Auto Decision Refund Process|adrpCumulativeLimitCount|ADRP cumulative limit count |
|amexSourceCode|Amex Source Code|sourceCode|Amex SourceCode|
|amexSourceCode|Amex Source Code|effectiveDate|Effective Date|
|authMatchExclusion|Auth Match Exclusion|southAuthMatchExclusion|South Auth Match Exclusion|
|authSettings|Auth Settings|transactionCurrency|Transaction Currency |
|authSettings|Auth Settings|authTypeCode|Auth Type Code|
|avsControl|AVS Control|avsExactIndicator|Address verification service exact indicator|
|avsControl|AVS Control|avsAddressIndicator|Address verification service address indicator|
|avsControl|AVS Control|avsServiceIndicator|Address verification service indicator|
|avsControl|AVS Control|avsUnavailableIndicator|Address verification service unavailable indicator|
|avsControl|AVS Control|avsWholeZipIndicator|Address verification service whole zip indicator|
|avsControl|AVS Control|avsYesIndicator|Address verification service Yes indicator|
|avsControl|AVS Control|avsZipIndicator|Address verification service zip indicator|
|avsControl|AVS Control|avsNoIndicator|Address verification service no indicator|
|avsControl|AVS Control|avsRetryIndicator|Address verification service retry indicator|
|bamsDissolutionHoldingsStatus|Bams Dissolution Holdings Status|offeringType|Offering Type|
|bamsDissolutionHoldingsStatus|Bams Dissolution Holdings Status|status|Program Status|
|billingConfig|Billing cofiguration|billSuppliesShippingIndicator|Bill supplies shipping and handling indicator|
|billingConfig|Billing cofiguration|delayedBillingEffectiveDate|Delayed billing effective date|
|billingConfig|Billing cofiguration|managementFeeDate|Date that management fee will be charged|
|billingConfig|Billing cofiguration|membershipFeeDate|Date that membership fees will be charged |
|billingConfig|Billing cofiguration|crossBorderFeeCode|Indicates whether a Merchant is liable for cross boarder fees for MasterCard, Visa or both|
|billingConfig|Billing cofiguration|zeroInterchangeIndicator|Zero interchange indicator reserved for international banks only|
|billingConfig|Billing cofiguration|billSuppliesIndicator|Bill Supplies Indicator|
|billingConfig|Billing cofiguration|retailerRateCode|Retailer rate code specific client usage|
|billmatrix|Billmatrix|status|Program Status|
|blackhawk|Blackhawk|isEnabled|Is Enabled|
|blackhawk|Blackhawk|effectiveDate|Effective Date|
|blackhawk|Blackhawk|miscInfoText|Misc Info Text|
|boardingAdditionalInfo|Merchant Boarding Additional Information|descriptionOfGoods|Description of goods and services sold by the merchant|
|boardingAdditionalInfo|Merchant Boarding Additional Information|homeBasedBusiness|Defines if the merchants business location is the same as his home location|
|boardingAdditionalInfo|Merchant Boarding Additional Information|wisoSalesRepId|Sales rep id of the wholesale iso employee|
|cardbrandPassThruFees|Cardbrand Pass Thru Fees|offeringType|Offering Type|
|cardconnect|Cardconnect File Identifier|status|Program Status|
|cashAdvance|Cash Advance|cashAdvanceLimitAmount|Cash advance Limit Amount|
|cashAdvance|Cash Advance|dailyWithholdPercentage|Cash Advance Daily Withhold Percentage|
|cashAdvance|Cash Advance|firstPaymentDate|Cash Advance First Payment Date|
|cashAdvance|Cash Advance|finalPaymentDate|Cash Advance Final Payment Date|
|cashAdvance|Cash Advance|fundingDate|Cash Advance Funding Date|
|cashAdvance|Cash Advance|terminationDate|Cash Advance Termination Date|
|cashAdvance|Cash Advance|invDueDate|Cash Advance Invoice Due Date|
|cashAdvance|Cash Advance|businessSegment|Cash Advance Business Segment|
|cashAdvance|Cash Advance|receivedAmount|Cash Advance Received Amount|
|cashAdvance|Cash Advance|branchCode|Cash Advance Branch Code|
|cashAdvance|Cash Advance|relationshipCode|Cash Advance Relationship Code|
|cashAdvance|Cash Advance|priorCashAdvanceId|Prior Cash Advance ID|
|cashAdvance|Cash Advance|estPaybackPeriod|Cash Advance EST Payback Period|
|cashAdvance|Cash Advance|legalStatus|Lease Legal Status|
|cashAdvance|Cash Advance|advanceAmount|Cash Advance Amount|
|cashAdvance|Cash Advance|cashAdvanceBankSequenceNumber|Cash Advance Bank Sequence Number added to Merchant Bank Account|
|cashAdvance|Cash Advance|splitFundingVendorCode|Split funding cash advance vendor code|
|cashAdvance|Cash Advance|splitFundingPercent|Split Funding Percentage|
|cashAdvance|Cash Advance|splitFundingPayToMerchantId|Split funding pay to merchant number|
|cashAdvance|Cash Advance|splitFundingParticipationCode|Split Funding Participation Code|
|cashAdvance|Cash Advance|remainingAmount|Cash Advance Remaining Amount|
|cashAdvance|Cash Advance|payBackAmount|Cash Advance Pay Back Amount|
|cashAdvance|Cash Advance|contractTerm|Cash Advance Contract Term|
|cashAdvance|Cash Advance|netIncome|Cash Advance Net Income|
|cashAdvance|Cash Advance|grossIncome|Cash Advance Gross Income|
|cashAdvance|Cash Advance|splitFundingAdvanceAmount|Split Funding Advance Amount|
|cashAdvanceProgram|Cash Advance Gl Funding Program|offeringType|Offering Type|
|cashAdvanceProgram|Cash Advance Gl Funding Program|status|Program Status|
|channelLevelDiscoverPromotionalPvi|Discover Promotional Program Verification Identifier - Channel Level|status|Program Status|
|channelLevelDiscoverPromotionalPvi|Discover Promotional Program Verification Identifier - Channel Level|offeringType|Offering Type|
|chargebackConfig|chargeback Configuration|chargebackPrenoteDays|Chargeback Prenote Days|
|chargebackConfig|chargeback Configuration|chargebackAddressCode|Indicates where the chargeback advice is directed|
|chargebackConfig|chargeback Configuration|mediaRetrievalCode|Code determining how the bank retrieval and chargeback retrieval advice or requests are processed|
|chargebackConfig|chargeback Configuration|mediaFaxNumber|Media Fax Number|
|chargebackConfig|chargeback Configuration|chargebackPrenoteIndicator|Indicates if the merchants recieves pre-notification before receiving a charge back|
|chargebackConfig|chargeback Configuration|holdChargebackIndicator|Hold Chargebacks Indicator |
|chargebackConfig|chargeback Configuration|email|email|
|chargebackConfig|chargeback Configuration|excessiveChargebackIndicator|Excessive Chargeback Indicator|
|chargebackConfig|chargeback Configuration|disputeDispositionCode|Indicates the disposition option for chargeback disputes|
|chargebackConfig|chargeback Configuration|chargebackReportDestinationCode|Chargeback Report Destination Code|
|checkAcceptanceMethod|Check Acceptance Method|mobileAppWarranty|Mobile App Warranty|
|checkAcceptanceMethod|Check Acceptance Method|onlineWarranty|Online Warranty|
|checkAcceptanceMethod|Check Acceptance Method|trsCollections|Trs Collections|
|checkAcceptanceMethod|Check Acceptance Method|inPersonECAVerificationTRS|InPerson ECA Verification TRS|
|checkAcceptanceMethod|Check Acceptance Method|inPersonPaperVerification|InPerson Paper Verification|
|checkAcceptanceMethod|Check Acceptance Method|mailOrderWarranty|Mail Order Warranty|
|checkAcceptanceMethod|Check Acceptance Method|checkCashingVerification|Check Cashing Verification|
|checkAcceptanceMethod|Check Acceptance Method|checkCashingWarranty|Check Cashing Warranty|
|checkAcceptanceMethod|Check Acceptance Method|codWarranty|Cod Warranty|
|checkAcceptanceMethod|Check Acceptance Method|lockboxVerification|Lockbox Verification|
|checkAcceptanceMethod|Check Acceptance Method|lockboxWarranty|Lockbox Warranty|
|checkAcceptanceMethod|Check Acceptance Method|onlineVerification|Online Verification|
|checkAcceptanceMethod|Check Acceptance Method|miscInfoText|Misc Info Text|
|checkAcceptanceMethod|Check Acceptance Method|tckMerchantId|Tck Merchant Id|
|checkAcceptanceMethod|Check Acceptance Method|cloverGoSettle|Clover Go Settle|
|checkAcceptanceMethod|Check Acceptance Method|cloverGoWarranty|Clover Go Warranty|
|checkAcceptanceMethod|Check Acceptance Method|onlineVerificationTRS|Online Verification TRS|
|checkAcceptanceMethod|Check Acceptance Method|mobileAppSettle|Mobile App Settle|
|checkAcceptanceMethod|Check Acceptance Method|recurringPaymentsVerificationTRS|Recurring Payments Verification TRS|
|checkAcceptanceMethod|Check Acceptance Method|recurringPaymentsVerification|Recurring Payments Verification|
|checkAcceptanceMethod|Check Acceptance Method|inPersonPaperWarranty|InPerson Paper Warranty|
|checkAcceptanceMethod|Check Acceptance Method|mailDropboxWarranty|Mail Dropbox Warranty|
|checkAcceptanceMethod|Check Acceptance Method|mailDropboxVerification|Mail Dropbox Verification|
|checkAcceptanceMethod|Check Acceptance Method|specialtyItemsWarranty|Specialty Items Warranty|
|checkAcceptanceMethod|Check Acceptance Method|specialtyItemsSettle|Specialty Items Settle|
|checkAcceptanceMethod|Check Acceptance Method|holdCheckWarranty|Hold Check Warranty|
|checkAcceptanceMethod|Check Acceptance Method|phoneVerificationTRS|Phone Verification TRS|
|checkAcceptanceMethod|Check Acceptance Method|phoneVerification|Phone Verification|
|checkAcceptanceMethod|Check Acceptance Method|phoneWarranty|Phone Warranty|
|checkAcceptanceMethod|Check Acceptance Method|recurringPaymentsWarranty|Recurring Payments Warranty|
|checkAcceptanceMethod|Check Acceptance Method|inPersonECAVerification|InPerson ECA Verification|
|checkAcceptanceMethod|Check Acceptance Method|inPersonECAWarranty|InPerson ECA Warranty|
|coinstarar|Coinstarar|isEnabled|Is Enabled|
|coinstarar|Coinstarar|miscInfoText|Misc Info Text|
|coinstarar|Coinstarar|effectiveDate|Effective Date|
|commercialCardInterchangeService|Commercial Card Interchange Service|ccisMerchantIncome|Commercial Card Interchange Service Merchant Income|
|compassOnNorth|Compass Podb Functionality On North|forcedDeposit|Eligible For Force Deposits|
|compassOnNorth|Compass Podb Functionality On North|reauthorizations|Eligible For Re-Authorizations|
|compassOnNorth|Compass Podb Functionality On North|status|Program Status|
|compassOnNorth|Compass Podb Functionality On North|partialReversals|Eligible For Partial Reversals|
|compassSpecialFeatures|Compass Front End Generated Refund Auths|amexOnlineRefund|Amex Online Refund|
|compassSpecialFeatures|Compass Front End Generated Refund Auths|compassFrontendGenreFauth|Compass frontend Gen Ref Auth|
|compassSpecialFeatures|Compass Front End Generated Refund Auths|visaToleranceCheckInd|Visa Tolerance Check Ind|
|conditionalApprovalProgram|Conditional Approval Program|offeringType|Offering Type|
|contract|Contract|postingMethod|The posting method assigned to the merchant|
|contract|Contract|clientTariff|This the merchant tariff assigned to the merchant|
|contract|Contract|contractReference|Free format field for information purpose|
|contract|Contract|serviceContractIndex|Service contract defines the processing rules for a merchant|
|contract|Contract|protectAgainstFXChange|Indicate if the Merchant is protected against currency fluctuations on the event the transaction is disputed|
|contract|Contract|salesLead|Secondary Tax ID|
|contractExpirationDate|Contract Expiration Date Notifications/Flag|gcid|Global Client Id|
|contractExpirationDate|Contract Expiration Date Notifications/Flag|contractExpirationDate|Contract Expiration Date|
|conversionInformation|Conversion  Account Source System Data|salesmanCode|Salesman Code|
|conversionInformation|Conversion  Account Source System Data|contractDate|Contract Date|
|conversionInformation|Conversion  Account Source System Data|status|Program Status|
|creditSettings|Credit Settings|cumulativeSalesLimitAmount|Cumulative Sales Limit Amount|
|creditSettings|Credit Settings|creditBinInclusionIndicator|Credit BIN Inclusion Indicator|
|creditSettings|Credit Settings|cumulativeCreditLimitAmount|Cumulative Credit Limit Amount|
|creditSettings|Credit Settings|creditLimitAmount|Credit Limit Amount|
|crossBorderAcquiring|Cross Border Acquiring|viSingleMerchantId|Visa Single Merchant Id|
|crossBorderAcquiring|Cross Border Acquiring|viSmiActivationInd|Visa Smi Activation Indicator|
|dataOnly|Data Only|isEnabled|Is Enabled|
|dataOnly|Data Only|effectiveDate|Effective Date|
|dataOnly|Data Only|miscInfoText|Misc Info Text|
|dccForIab|Dynamic Currency Conversion For International Agent Bank|offeringType|Offering Type|
|depositRequirement|Deposit Requirement|programGuideVersion|Program Guide Version|
|depositRequirement|Deposit Requirement|offeringType|Offering Type|
|disbursementssements|Disbursementssements|pinEntryMethods|Pin Entry Methods|
|disbursementssements|Disbursementssements|miscInfoText|Misc Info Text|
|disregardedEntity|Disregarded Entity|status|Program Status|
|duguesneUniv|Duguesne Univ|miscInfoText|Misc Info Text|
|duguesneUniv|Duguesne Univ|effectiveDate|Effective Date|
|duguesneUniv|Duguesne Univ|isEnabled|Is Enabled|
|earlyTerminationFee|Early Termination Fee|earlyTermFeeAmount|Early termination fee amount|
|earlyTerminationFee|Early Termination Fee|earlyTermFeeIndicator|Early termination fee indicator|
|earlyTerminationFee|Early Termination Fee|earlyTermDate|Early termination date applicable to charging an associated fee|
|ecommercerce|Ecommercerce|miscInfoText|Misc Info Text|
|ecommercerce|Ecommercerce|pinEntryMethods|Pin Entry Methods|
|egiftSocial|EgiftSocial|isEnabled|Is Enabled|
|egiftSocial|EgiftSocial|effectiveDate|Effective Date|
|egiftSocial|EgiftSocial|miscInfoText|Misc Info Text|
|electronicTicketCapture|Electronic Ticket Capture|etcVendorId|Identifies third party vendor used to process electronic data capture transactions|
|electronicTicketCapture|Electronic Ticket Capture|etcMerchantId|Merchant ID used in electronic ticket capture processing on optis frontend|
|electronicTicketCapture|Electronic Ticket Capture|etcBypassEditsIndicator|TellS the edit programs if the Merchant wishes to let all his ETC transactions process|
|electronicTicketCapture|Electronic Ticket Capture|etcCutoffTimeCode|Code indicating what time electronic ticket capture processing is terminated for the day|
|electronicTicketCapture|Electronic Ticket Capture|etcOptionCode|Code identifying the type of electronic ticket capture processing used|
|enhanceDebitCompletionFlow|Enhance Debit Completion Flow For Pts Direct Send Merchants|status|Program Status|
|entitlementAttr|Entitlement attributes|visaAccountUpdater|Visa Account Updater|
|entitlementAttr|Entitlement attributes|interacFlashStatus|Program Status for Interac Flash Entitlementg|
|entitlementAttr|Entitlement attributes|interacFlashMVV|MVV for Interac Flash Entitlement|
|entitlementAttr|Entitlement attributes|bentoBoxStatus|Bento Box Program Status|
|entitlementAttr|Entitlement attributes|paypalVenmoPayerId|Paypal/Venmo Payer ID|
|entitlementAttr|Entitlement attributes|paypalVenmoLocationID|Paypal/Venmo Location ID|
|entitlementAttr|Entitlement attributes|paypalVenmoLatitude|Paypal/Venmo Latitude for Merchant Location|
|entitlementAttr|Entitlement attributes|paypalVenmoLongitude|Paypal/Venmo Longitude for Merchant Location|
|entitlementAttr|Entitlement attributes|paypalVenmoPayerIdStatus|Paypal/Venmo Payer ID Status|
|entitlementAttr|Entitlement attributes|paypalVenmoLocationIDStatus|Paypal/Venmo Location ID Status|
|entitlementAttr|Entitlement attributes|debitRepayment|Debit Repayment|
|entitlementAttr|Entitlement attributes|serviceEstablishmentNumber|Service Establishment Number|
|entitlementAttr|Entitlement attributes|discountMethodCode|Discount Method Code|
|entitlementAttr|Entitlement attributes|achIndicator|ACH Indicator|
|entitlementAttr|Entitlement attributes|settleIndicator|Settlement Indicator|
|entitlementAttr|Entitlement attributes|upiDebitStatus|Program Status for UPI Debit Entitlement|
|entitlementAttr|Entitlement attributes|visaOct|Visa Oct|
|entitlementAttr|Entitlement attributes|mcMoneysend|MC Money Send|
|entitlementAttr|Entitlement attributes|visaCheckout|Visa Checkout|
|entitlementAttr|Entitlement attributes|visaAccountFundingTxn|Visa Account Funding Transaction|
|entitlementAttr|Entitlement attributes|paypalVenmoErrorMessage|Paypal/Venmo Error Message|
|entitlementAttr|Entitlement attributes|iramIndicator|Iram Indicator|
|entitlementAttr|Entitlement attributes|promoPvi|Promo Pvi|
|entitlementAttr|Entitlement attributes|tckCpEntitlement|TckCp Entitlement|
|entitlementAttr|Entitlement attributes|dbtTermId|Dbt TermId|
|entitlementAttr|Entitlement attributes|pinlessEcommDebit|Pinless Ecomm Debit|
|entitlementAttr|Entitlement attributes|interacContactEntitlement|Interac Contact Entitlement|
|entitlementAttr|Entitlement attributes|interacInApp|Interac InApp|
|entitlementAttr|Entitlement attributes|upiCreditEntitlement|Upi Credit Entitlement|
|entitlementAttr|Entitlement attributes|idealSubMerchantId|Ideal Sub Merchant ID for Omnipay|
|entitlementAttr|Entitlement attributes|signedVolumeAmount|Signed Volume Amount|
|entitlementAttr|Entitlement attributes|effectiveDate|Effective Date|
|entitlementAttr|Entitlement attributes|serviceTypeCode|Service Type Code|
|entitlementAttr|Entitlement attributes|mccCode|Merchant Category Code|
|entitlementAttr|Entitlement attributes|clearingPlanCode|Clearing Plan Code|
|entitlementAttr|Entitlement attributes|pricingPlanCode|Pricing Plan Code|
|entitlementAttr|Entitlement attributes|floorLimitAmount|Floor Limit Amount|
|entitlementAttr|Entitlement attributes|edcCode|EDC Code|
|entitlementAttr|Entitlement attributes|miscInfoText|Misc Info Text|
|entitlementAttr|Entitlement attributes|mcIpValue|Mastercard IP Value (RQS-3140)|
|entitlementAttr|Entitlement attributes|visaIpQualification|Visa IP Qualification|
|entitlementAttr|Entitlement attributes|mcIpQualification|Mastercard IP Qualification (RQS-3140)|
|entitlementAttr|Entitlement attributes|isoId|ISO_ ID as assigned by MC|
|entitlementAttr|Entitlement attributes|visaIpValue|Visa IP Value|
|entitlementAttr|Entitlement attributes|upiCreditStatus|Program Status for UPI Credit Entitlement|
|entitlementAttr|Entitlement attributes|intesdsxCode|Intes/DSX code for Omnipay Diners Entitlement|
|entitlementAttr|Entitlement attributes|apfAuthFee|APF Auth Fee for Omnipay Visa Entitlement|
|entitlementAttr|Entitlement attributes|chinaUnionOfferingType|China Union Pay Entitlement|
|entitlementAttr|Entitlement attributes|interacContactStatus|Program Status for Interac Contact Entitlement|
|entitlementAttr|Entitlement attributes|upiDebitEntitlement|Upi Debit Entitlement|
|entitlementAttr|Entitlement attributes|clovergoStatus|Program Status for Clover Go|
|entitlementAttr|Entitlement attributes|clovergoOfferingType|Offering Type for Clover Go|
|entitlementAttr|Entitlement attributes|gyftStatus|Program Status for GYFT|
|entitlementAttr|Entitlement attributes|gyftBillingMethod|Billing Method for GYFT|
|entitlementAttr|Entitlement attributes|paypalEnblOfferingType|offering Type for Paypal Enablement for Discover|
|entitlementAttr|Entitlement attributes|alipayOfferingType|Alipay Entitlement|
|entitlementAttr|Entitlement attributes|valuelinkSeNumber|Value Link SE Number|
|entitlementAttr|Entitlement attributes|interacInAppStatus|Program Status for Interac In App Entitlement|
|equipmentFeatures|Equipment Features|salesRepId|Sales Rep associated with the equipment sale/lease|
|equipmentFeatures|Equipment Features|dialPrefix|Dial prefix|
|equipmentFeatures|Equipment Features|terminalClass|Terminal class|
|equipmentFeatures|Equipment Features|captureType4|Capture 4|
|equipmentFeatures|Equipment Features|captureType3|Capture 3|
|equipmentFeatures|Equipment Features|dldId|Dld id|
|equipmentFeatures|Equipment Features|forceSinglePayToken|Force single pay token|
|equipmentFeatures|Equipment Features|ip|IP|
|equipmentFeatures|Equipment Features|stepupRate|Step up rate|
|equipmentFeatures|Equipment Features|stepupRateType|Step up rate type|
|equipmentFeatures|Equipment Features|taEncryptionType|TA encryption type|
|equipmentFeatures|Equipment Features|transarmorSecurityLevel|Transarmor security level|
|equipmentFeatures|Equipment Features|varPaymentMonths|Var payment months|
|equipmentFeatures|Equipment Features|dateAdded|Date when the equipment was installed|
|equipmentFeatures|Equipment Features|captureType1|Capture 1|
|equipmentFeatures|Equipment Features|requestCreatedDate|Date when the equipment was requested|
|equipmentFeatures|Equipment Features|varPaymentPype|Var payment pype|
|equipmentFeatures|Equipment Features|captureType2|Capture 2|
|equipmentFeatures|Equipment Features|autoTidPopulate|Auto tid populate|
|equipmentFeatures|Equipment Features|autoCloseMethod|Auto close method|
|equipmentFeatures|Equipment Features|autoCloseHhmm|Auto close HHMM|
|equipmentFeatures|Equipment Features|serialNumber|Serial Number|
|equipmentFeatures|Equipment Features|wholesaleMonthlyMaintenanceCharge|Wholesale Monthly Maintenance Charge|
|equipmentFeatures|Equipment Features|leaseTerm|Lease Term|
|equipmentFeatures|Equipment Features|resaleCharge|Resale Charge|
|equipmentFeatures|Equipment Features|wholesaleMonthlyRentalCharge|Wholesale Monthly Rental Charge|
|equipmentFeatures|Equipment Features|maintenanceCharge|Maintenance Charge|
|fdggMigration|First Data Global Gateway Migration|status|Program Status|
|fdggMigration|First Data Global Gateway Migration|offeringType|Offering Type|
|feeAttr|Fee Attributes|processingInd|Procesing Indicator|
|feeAttr|Fee Attributes|frequencyInd|Frequency Indicator|
|feeAttr|Fee Attributes|wholesaleDate|Wholesale Date|
|feeAttr|Fee Attributes|retailDate|Retail Date|
|financialBuAssignmentValues|Financial Bu Assignment Values|fmgMarkerBank|Fmg Marker Bank|
|financialBuAssignmentValues|Financial Bu Assignment Values|profitCenterId|Profit Center Id|
|financialBuAssignmentValues|Financial Bu Assignment Values|profitCenterDescription|Profit Center Description|
|financialBuAssignmentValues|Financial Bu Assignment Values|fmgGroupCode|Fmg Group Code|
|financialBuAssignmentValues|Financial Bu Assignment Values|financeParent|Finance Parent|
|financialBuAssignmentValues|Financial Bu Assignment Values|financeEntity|Finance Entity|
|financialBuAssignmentValues|Financial Bu Assignment Values|financeAlliance|Finance Alliance|
|financialBuAssignmentValues|Financial Bu Assignment Values|financePortfolio|Finance Portfolio|
|financialBuAssignmentValues|Financial Bu Assignment Values|globalClientId|Global Client Id|
|financialBuAssignmentValues|Financial Bu Assignment Values|globalClientDescription|Global Client Description|
|financialBuAssignmentValues|Financial Bu Assignment Values|futureUse1|Future Use 1|
|financialBuAssignmentValues|Financial Bu Assignment Values|futureUse2|Future Use 2|
|financialBuAssignmentValues|Financial Bu Assignment Values|companyCode|Company Code|
|financialBuAssignmentValues|Financial Bu Assignment Values|status|Program Status|
|firstHawaiianBank|First Hawaiian Bank|fhbNaicsNumber|Fhb Naics Number N|
|flexCache|Flex Cache|isEnabled|Is Enabled|
|flexCache|Flex Cache|effectiveDate|Effective Date|
|flexCache|Flex Cache|miscInfoText|Misc Info Text|
|flexCache|Flex Cache|serviceEntlNumber|Service Entl Number|
|foreignLanguageSupport|Foreign Language Support|foreignLanguageSupport|Foreign Language Support|
|franchise|Franchise|offeringType|Offering Type|
|franchiseEnabled|Franchise Enabled|isEnabled|Is Enabled|
|franchiseEnabled|Franchise Enabled|miscInfoText|Misc Info Text|
|franchiseEnabled|Franchise Enabled|effectiveDate|Effective Date|
|fraudAndAccountTakeoverRisk|Fraud And Account Takeover Risk|status|Program Status|
|fraudWatch|Fraud Watch|miscInfoText|Misc Info Text|
|fraudWatch|Fraud Watch|effectiveDate|Effective Date|
|fraudWatch|Fraud Watch|isEnabled|Is Enabled|
|freeProcessing|Free Processing|status|Program Status|
|fundingConfig|Funding Configuration|fundingExcludeCode|Merchant funding exclusion code|
|fundingConfig|Funding Configuration|achSuspenseHoldIndicator|ACH suspense hold indicator|
|fundingConfig|Funding Configuration|bankwireObiText|Bankwire beneficiary OBI Text|
|fundingConfig|Funding Configuration|fundingRppMinimumAmount|Revolving payment plan minimum dollar amount|
|fundingConfig|Funding Configuration|fundingRppMinimumReserveAmount|Revolving payment plan minimum reserve amount|
|fundingConfig|Funding Configuration|ptsLimitsIndicator|PTS Limits Indicator|
|fundingConfig|Funding Configuration|fundingEscrowCode|Indicates how the escrow details will be handled|
|fundingConfig|Funding Configuration|fundingRppChangeDate|Merchant funding revolving payment plan change date|
|fundingConfig|Funding Configuration|fundingRppPercent|Revolving payment plan percent|
|fundingConfig|Funding Configuration|bankwireBnfText|Bankwire beneficiary BNF Text|
|fundingConfig|Funding Configuration|fundingExcludeAccountTypeCode|Merchant funding exclusion financial account code|
|fundingConfig|Funding Configuration|achSuspenseReleaseIndicator|ACH suspense release indicator|
|fundingConfig|Funding Configuration|fundingAchHoldIndicator|Code representing whether the ACH funding is to be put on hold or released|
|fundingConfig|Funding Configuration|fundingAchDelayDays|Retention period for deposits and daily discount before releasing them for ACH processing|
|fundingConfig|Funding Configuration|fundingAchDeficitCode|ACH or deficit file indicator|
|fundingConfig|Funding Configuration|fundingAchDestinationCode|ACH Destination Code|
|fundingConfig|Funding Configuration|fundingAchUsageCode|Indicates how the System produces monthly automatic clearing house tapes for the merchant account |
|fundingConfig|Funding Configuration|fundingDebitCode|Daily Debit Code|
|fundingConfig|Funding Configuration|fundingDiscountCode|Daily Discount Code|
|fundingConfig|Funding Configuration|fundingAdjustmentCode|Daily Adjustment Code|
|fundingConfig|Funding Configuration|fundingDepositCode|Daily Deposit Code|
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|financialAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|feesFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|depositsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|depositAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|reversalsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|fundingExclude30DayLimitAmount|Merchant funding exclusion monthly sales limit amount|
|fundingConfig|Funding Configuration|discountsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|fundingRppDelayDays|Revolving payment plan delay days|
|fundingConfig|Funding Configuration|fundingRollupCode|Indicates how the funding transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|discountsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|chargebacksFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|reversalsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|chargebacksFundingRollupCode|Indicates how the transactions will be combined on DDA statement|
|fundingConfig|Funding Configuration|fundingExcludeBankRoutingNumber|Merchant funding exclusion bank routing number|
|fundingConfig|Funding Configuration|fundingExcludeBankAccountNumber|Merchant funding exclusion bank account number|
|fundingConfig|Funding Configuration|depositAdjustmentsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|bankwireBbkText|Bankwire beneficiary BBK Text|
|fundingConfig|Funding Configuration|agentBankSplitIndicator|Indicates if Bank Client is considered an agent relationship to FDCS|
|fundingConfig|Funding Configuration|depositsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|feesFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|depositsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|depositAdjustmentsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|reversalsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|chargebacksFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|discountsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingDivertCode|Funding Divert Code|
|fundingConfig|Funding Configuration|financialAdjustmentsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|feesBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|depositAdjustmentsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|reversalsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|temporaryToDate|Temporary To Date|
|fundingConfig|Funding Configuration|depositsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|feesFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|financialAdjustmentsFundingCategoryCode|Funding Category Code|
|fundingConfig|Funding Configuration|interchangeAssessmentsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|discountsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|fundingNotifyFaxNumber|Funding notification contact name|
|fundingConfig|Funding Configuration|fundingRunCode|Merchant Funding Run|
|fundingConfig|Funding Configuration|fundingCurrencyCode|Funding Currency Code|
|fundingConfig|Funding Configuration|fundingMethodCode|Funding method code Code determining how funds will be settled|
|fundingConfig|Funding Configuration|fundingExcludeDailyLimitAmount|Merchant funding exclusion daily sales limit amount|
|fundingConfig|Funding Configuration|convenienceFeeCode|Convenience fee code to indicate the ABA or DDA to be charged|
|fundingConfig|Funding Configuration|funding30DayOverrideDate|Funding 30 day daily override date|
|fundingConfig|Funding Configuration|funding30DayOverrideIndicator|Funding 30 day override indicator|
|fundingConfig|Funding Configuration|fundingDailyOverrideDate|Funding Daily Override Date|
|fundingConfig|Funding Configuration|fundingDailyOverrideIndicator|Funding Override Indicator|
|fundingConfig|Funding Configuration|fundingNotifyContactName|Funding notification contact name|
|fundingConfig|Funding Configuration|chargebacksBankSequenceNumber|Funding Bank Sequence|
|fundingConfig|Funding Configuration|fundingNotifyIndicator|Funding notification indicator|
|fundingConfig|Funding Configuration|fundingNotifyMethodCode|Funding notification method code|
|fundingConfig|Funding Configuration|fundingNotifyPhoneNumber|Funding notification phone number|
|fundingConfig|Funding Configuration|settleTimeframeCode|Settlement Timeframe Code|
|fundingConfig|Funding Configuration|temporary30DayLimitAmount|Temporary monthly limit amount|
|fundingConfig|Funding Configuration|temporaryDailyLimitAmount|Temporary Daily Limit Amount|
|fundingConfig|Funding Configuration|temporaryFromDate|Temporary From Date|
|fundingConfig|Funding Configuration|fundingBankCode|Funding Bank Code|
|fundingConfig|Funding Configuration|financialAdjustmentsFundingDivertCode|Funding Divert Code|
|giftangogo|Giftangogo|effectiveDate|Effective Date|
|giftangogo|Giftangogo|isEnabled|Is Enabled|
|giftangogo|Giftangogo|miscInfoText|Misc Info Text|
|globalCurrencySolutions|Global Currency Solutions|offeringSubType1|Offering Sub Type|
|globalCurrencySolutions|Global Currency Solutions|offeringType|Offering Type|
|globalCurrencySolutions|Global Currency Solutions|offeringSubType2|Globally Used For All North Backend Sales Channels|
|greatLakesScript|Great Lakes Script|isEnabled|Is Enabled|
|greatLakesScript|Great Lakes Script|miscInfoText|Misc Info Text|
|greatLakesScript|Great Lakes Script|effectiveDate|Effective Date|
|hcAccel|Hc Accel|miscInfoText|Misc Info Text|
|hcAccel|Hc Accel|healthcare|Healthcare|
|hcAffn|Hc Affn|healthcare|Healthcare|
|hcAffn|Hc Affn|miscInfoText|Misc Info Text|
|hcAth|Hc Ath|healthcare|Healthcare|
|hcAth|Hc Ath|miscInfoText|Misc Info Text|
|hcAts|Hc Ats|miscInfoText|Misc Info Text|
|hcAts|Hc Ats|healthcare|Healthcare|
|hcCu24|Hc Cu24|miscInfoText|Misc Info Text|
|hcCu24|Hc Cu24|healthcare|Healthcare|
|hcInterlink|Hc Interlink|healthcare|Healthcare|
|hcInterlink|Hc Interlink|miscInfoText|Misc Info Text|
|hcJeanie|Hc Jeanie|miscInfoText|Misc Info Text|
|hcJeanie|Hc Jeanie|healthcare|Healthcare|
|hcMaestro|Hc Maestro|healthcare|Healthcare|
|hcMaestro|Hc Maestro|miscInfoText|Misc Info Text|
|hcNyce|Hc Nyce|healthcare|Healthcare|
|hcNyce|Hc Nyce|miscInfoText|Misc Info Text|
|hcPulse|Hc Pulse|healthcare|Healthcare|
|hcPulse|Hc Pulse|miscInfoText|Misc Info Text|
|hcShazam|Hc Shazam|miscInfoText|Misc Info Text|
|hcShazam|Hc Shazam|healthcare|Healthcare|
|hcStarEast|Hc Star East|healthcare|Healthcare|
|hcStarEast|Hc Star East|miscInfoText|Misc Info Text|
|hcStarNortheast|Hc Star Northeast|healthcare|Healthcare|
|hcStarNortheast|Hc Star Northeast|miscInfoText|Misc Info Text|
|hcStarWest|Hc Star West|healthcare|Healthcare|
|hcStarWest|Hc Star West|miscInfoText|Misc Info Text|
|highRiskMonitoring|High Risk Monitoring|offeringType|Offering Type|
|highRiskMonitoring|High Risk Monitoring|status|Program Status|
|highRiskMonitoring|High Risk Monitoring|contractDate|Contract Date|
|inHouseAuthConfig|InHouse Auth Configuration|inHouseNonMerchantCode|InHouse NonMerchant Code|
|inHouseAuthConfig|InHouse Auth Configuration|inHouseBankCode|InHouse Bank Code|
|inHouseAuthConfig|InHouse Auth Configuration|inHouseAuthCaptureCode|InHouse Authorization Capture Code|
|incomm|Incomm|isEnabled|Is Enabled|
|incomm|Incomm|effectiveDate|Effective Date|
|incomm|Incomm|miscInfoText|Misc Info Text|
|indemnification|Indemnification|riskOwnerCode|Risk Owner Code|
|indemnification|Indemnification|indemnificationIndicator|Indemnification Indicator|
|indemnification|Indemnification|indemnificationPercent|Indemnification Risk Ratio Percentage|
|indemnification|Indemnification|indemnificationDate|Indemnification Date|
|independentSoftwareVendor|Independent Software Vendor (Isv) Global Indicator|offeringType|Offering Type|
|internalItUse|Internal It Use - Trigger Feeds And Save Data|discoverTrigger|Registration Merchant Feed To Discover|
|internalItUse|Internal It Use - Trigger Feeds And Save Data|spomiTrigger|Sponsored Merchant Feed To Amex|
|iolCanadianVatRegNumber|Iol Canadian Vat Reg Number|canadianVatRegNumber|Canadian Vat Registration Number|
|irsSupplementalInformation|Irs Supplemental Information|econsentDate|Econsent Date|
|irsSupplementalInformation|Irs Supplemental Information|econsentIndicator|Econsent Indicator|
|irsSupplementalInformation|Irs Supplemental Information|primaryEmailIndicator|Primary Email Indicator|
|irsSupplementalInformation|Irs Supplemental Information|userProvidedEconsentEmail|User Provided Econsent Email|
|irsSupplementalInformation|Irs Supplemental Information|requestGuid|Request Guid|
|isoServices|Iso Services|isoIdDscv|Iso Id Discover|
|isoServices|Iso Services|serviceProvider|Service Provider|
|isoServices|Iso Services|isoIdMc|Iso Id Mc|
|isoServices|Iso Services|isoIdVi|Iso Id Vi|
|isoServices|Iso Services|isoIdAmex|Iso Id Amex|
|jet|Jet|miscInfoText|Misc Info Text|
|jet|Jet|isEnabled|Is Enabled|
|jet|Jet|effectiveDate|Effective Date|
|keyReferenceNumber|Key Reference Number|keyReferenceNumber|Credit Only Key Reference Number|
|keyReferenceNumber|Key Reference Number|tbd|Tbd|
|lcrBillPayment|lcrBill Payment|miscInfoText|Misc Info Text|
|lcrBillPayment|lcrBill Payment|pinEntryMethods|Pin Entry Methods|
|lease|INFOLEASE|leaseContractBalanceAmount|Contract balance remaining after all payments received are applied to the gross contract. This amount is system-calculated.|
|lease|INFOLEASE|leasePaymentOptionCode|This field depicts different options of Lease Payment.|
|lease|INFOLEASE|leasePaymentPaidToDate|Contract payments are paid up to, but not including, this date. This field is based on the due dates of unpaid open items or the next due date (invoicing date plus lead invoicing days) if there are no unpaid open items. |
|lease|INFOLEASE|leaseDelinquentStatusCode|The delinquent status of the contract. This is a system-calculated field. |
|lease|INFOLEASE|leaseFirstPaymentDate|The first payment date. This is a required field. InfoLease calculates the default date based on the commencement date, billing cycle, variable payment schedule, and the payments in arrears code.|
|lease|INFOLEASE|leaseFirstPaymentAmount|If the first payment is different from the regular scheduled payments, enter the amount here; otherwise, InfoLease defaults the regular contract payment. If no payment is due in the first month, enter zero.|
|lease|INFOLEASE|leasePaymentInvoicedCount|The number of payments billed to the customer.|
|lease|INFOLEASE|leasePendingCode|This field identifies outstanding information, e.g., paperwork, correspondence, you expect to receive for the contract.|
|lease|INFOLEASE|leaseVariablePaymentAmount|Variable Payment Amount of the lease|
|lease|INFOLEASE|leaseCustomerDoingBusinessName|The Customerdoing business name|
|lease|INFOLEASE|leaseCustomerShortName|The Short Name is another name to use when referring to the customer. The Short Name cannot be the same as the Customer Name. This field defaults to the Short Name previously entered for the customer.|
|lease|INFOLEASE|leaseWriteOffAmount|The income used to offset the initial expense associated with a new lease. The amount is calculated by multiplying the setup income percentage on the Lessor Parameter File by the gross finance income.|
|lease|INFOLEASE|leaseNextAgingDate|The next date InfoLease will age the contract. You cannot modify this field. |
|lease|INFOLEASE|leaseBranchCode|This 5-character code indicates the branch associated with the contract. You can use the branch as a sort sequence when requesting reports.|
|lease|INFOLEASE|leaseInvoiceDueDate|The day of the month the payment is due. If you do not enter the invoicing due day, the field defaults to the due day on the Customer Default Data Screen. |
|lease|INFOLEASE|leaseFloatingRateIndicator|This yes/no field indicates whether this is a floating rate contract.|
|lease|INFOLEASE|leaseTypeCode|A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.|
|lease|INFOLEASE|leaseFinalPaymentDate|This field identifies the date the last contract payment is due. This is a system-calculated field using the contract term, the number of advance payments, the number of payments in arrears, the commencement date, and the billing cycle.|
|lease|INFOLEASE|leaseActivationDate|The activation date of the contract. Entering this date activates the contract. InfoLease uses this date along with the Contract Term and the Payments in Arrears Code to determine the termination date of the contract.|
|lease|INFOLEASE|leaseLastPaymentDate|The date you received the last payment.|
|lease|INFOLEASE|leaseNumberOfAsset|The number of active assets associated with the contract.|
|lease|INFOLEASE|leaseTotalRentalPaymentNumber|Total number of rental payments made to date.|
|lease|INFOLEASE|leaseVariablePaymentIndicator|This yes/no field indicates whether this contract has a variable payment schedule. |
|lease|INFOLEASE|leaseManagerResidualAmount|An alternate residual amount that you can select when calculating a buyout quote. Managers residual does not accrue income.This field usually projects an optimistic figure for residual. The Amortizable Residual field usually projects a more conservative figure.|
|lease|INFOLEASE|leaseGrossPaymentAmount|The total amount of payments due on the contract. If a commencement date was entered, this field is mandatory.|
|lease|INFOLEASE|leaseInvoiceCode|The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.|
|lease|INFOLEASE|leaseBillingCycle|Billing Cycle of a lease|
|lease|INFOLEASE|leaseFacilityScore|This score represents the credit score of the deal, not the credit score of the customer.|
|lease|INFOLEASE|leaseIncomeStartDate|The date the income on the contract begins to amortize. This date affects how InfoLease calculates the IRR. This date defaults to the commencement date of the contract; however, in cases where interest free periods exist, you can modify this date.|
|lease|INFOLEASE|leaseContractStatusDesc|Contract Status Description|
|lease|INFOLEASE|leaseContractStatusDate|The date the status was assigned to the contract.|
|lease|INFOLEASE|leasePreviousContractNumber|Lease Previous Contract Number|
|lease|INFOLEASE|leaseContractStatus|The status of the contract. |
|lease|INFOLEASE|leaseCustomerPostalCode|The zip code of the city where the customer is located.|
|lease|INFOLEASE|leaseGeneralLedgerBookingDate|Lease General Booking Date|
|lease|INFOLEASE|leaseMonthlyPaymentAmount|The amount of the contract payment. If this is a variable payment contract, do not enter a contract payment here.|
|lease|INFOLEASE|leasePaymentUpfrontAmount|The number of beginning payments paid in advance by the customer at contract commencement. Without the Customer Service Module, this field is informational only.|
|lease|INFOLEASE|leaseEarlyBuyoutAmount|You can enter buyout amounts for the contract in this field. You must first fill in the Date field. The information in this field does not default to the Buyout Quotes module.|
|lease|INFOLEASE|leaseCustomerAddressLine3|The third line of the customers address.|
|lease|INFOLEASE|leaseContractTotalReceivedAmount|The total contract payment amount received from the beginning of the contract. This is a system-calculated amount.~ ~ Note: If a partial disposition has taken place, this represents the payments on the active portion of the contract only.|
|lease|INFOLEASE|leaseCustomerCityName|The city where the customer is located.|
|lease|INFOLEASE|leaseNetInvestmentAmount|The net investment of the contract. The net investment is the loss the lessor would incur if the lessee stopped payment today.|
|lease|INFOLEASE|leaseCustomerStateCode|The state where the customer is located.|
|lease|INFOLEASE|leaseCustomerAddressLine2|The second line of the customers address.|
|lease|INFOLEASE|leasePreviousDelinquentStatusCode|The previous delinquent status of the contract. If the Delinquent Status Code changes, the previous status is moved to the Previous Delinquent Status field.|
|lease|INFOLEASE|leaseNextChargeDate|The next date InfoLease will assess the appropriate late charges during the aging process. You cannot modify this field. InfoLease updates this field whenever you run aging.|
|lease|INFOLEASE|leaseFdmsDecisionInd|UATB.FDMS.DECISION|
|lease|INFOLEASE|leaseCustomerName|The customer name. Use the customer name to create alphabetical listings and locate a name when using Soundex.|
|lease|INFOLEASE|leaseCustomerAccountReceivableName|The accounts receivable name. This name prints on the customers invoice.|
|lease|INFOLEASE|leaseCustomerArAddressLine1|The first line of the accounts receivable address. This address prints on the customers invoice.|
|lease|INFOLEASE|leaseCustomerArAddressLine2|The second line of the accounts receivable address. This address prints on the customers invoice.|
|lease|INFOLEASE|leaseCustomerArAddressLine3|The third line of the accounts receivable address. This address prints on the customers invoice.|
|lease|INFOLEASE|leaseCustomerArAddressCityName|The city for the accounts receivable address.|
|lease|INFOLEASE|leaseCustomerArAddressStateName|The state for accounts receivable address.|
|lease|INFOLEASE|leaseCustomerArAddressPostalCode|The zip code of the city for the accounts receivable address.|
|lease|INFOLEASE|leaseCustomerArAddressAttentionName|Information entered in this field prints on the invoice, i.e., the name of the person to whom you are mailing the invoice.|
|lease|INFOLEASE|leaseCustomerArAddressCountryCode|The country code for the accounts receivable address.|
|lease|INFOLEASE|leaseFdmsDecisionDate|UATB.DATE.FDMS.DECISION|
|lease|INFOLEASE|leaseProvisionForLossAmount|The amount set aside to record in the first month for bad debt expense. Enter an amount or default to the system-calculated amount. Gross Contract x Provision for Loss Percentage (lessor file) = Provision for Loss Enter the provision for loss percentage in the Prov for Loss field accessed via the Lessor Parameter Maintenance Screen and the Lessor Default Fields Screen.|
|lease|INFOLEASE|leaseCompanyName|UATB.LEASING.COMPANY|
|lease|INFOLEASE|leaseAmortizableResidualAmount|The calculation for amortizable residual is as follows.~ ~ Gross Residual~ - Residual Writedown ~ - Discount Residual~ - Present Value Amount~ = Amount of Residual Amortized~ ~ This field usually projects a conservative amount for residual. The Managers Residual field generally projects a more optimistic figure.|
|lease|INFOLEASE|leaseApproverSignatoryName|The name of the person who signs the contract. This field defaults to the name entered in the Contact Name field.|
|lease|INFOLEASE|leaseProgramTypeCode|A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.|
|lease|INFOLEASE|leaseEarlyBuyoutDate|You can enter the buyout date for the contract in this field. Entering information here does not default to the Buyout Quotes module.|
|lease|INFOLEASE|leaseGrossAssetAmount|The total equipment cost for all assets (not including disposed assets) on the contract.|
|lease|INFOLEASE|leaseFollowUpDays|The number of days after the payment due date that you need to contact the customer. InfoLease uses the number of follow-up days to generate follow-up lists for payment collections. This field is used with the Customer Service Module.|
|lease|INFOLEASE|leaseBuyoutQuoteCode|This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.|
|lease|INFOLEASE|leasePlatformCode|PLATFORM|
|lease|INFOLEASE|leaseCustomerCountry|The country where the customer is located.|
|lease|INFOLEASE|leaseContractTerm|The term of the contract in months. If a commencement date was entered, this field is mandatory.The maximum term is 400 months.|
|lease|INFOLEASE|leaseDispositionDate|The last date any disposition or inventory occurred on the contract. InfoLease updates this field at the time of a disposition.|
|lease|INFOLEASE|leaseMerchantId|Lease Merchant ID|
|lease|INFOLEASE|leaseCustomerFedSsnId|The appropriate identification number.  The ability to modify this field depends on your security settings.|
|lease|INFOLEASE|leaseCustomerCreditScore|A user-defined score given by the leasing company extending credit to the lessee. A credit score is based on certain factors, such as age, marital status, length of employment, etc. Each of these factors is assigned a certain point value with the total being the credit score. Based on this score, the lessee is approved for the credit.|
|lease|INFOLEASE|leaseBusinessSegment|This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.|
|lease|INFOLEASE|leaseRelationCode|Lease Relationship code|
|lease|INFOLEASE|leaseTaxExemptIndicator|This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.|
|lease|INFOLEASE|leaseCollateralCode|This code identifies additional collateral (other than the actual equipment) assigned to a contract.|
|lease|INFOLEASE|leaseTermDate|The date the contract expires.This date is system-generated and you cannot enter or maintain it at the contract level. However, a new date is generated if the Commencement Date, Contract Term, or the Payments In Arrears code is changed.|
|lease|INFOLEASE|leaseSecurityDepositAmount|This window displays the Security Deposit and the Down Payment fields.The Security Deposit field represents the amount received from the lessee. The Down Payment field represents the amount received from the lessee. |
|lease|INFOLEASE|leaseResidualAmount|This field displays once information is entered in residual amount at the asset level. This field cannot be entered or maintained at the contract level. However, a residual change at the asset level affects the gross residual.|
|lease|INFOLEASE|leaseSaleLeasebackInd|Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.|
|lease|INFOLEASE|leaseNetFinanceAmount|Net finance is the difference between the gross finance income and the setup income. If Prov Loss Fr Fin = (Y)es, InfoLease also subtracts Provision for Loss from net finance. This amount is system-calculated and you cannot modify it. |
|lease|INFOLEASE|leaseGrossFinanceAmount|The total amount of finance or interest income (difference between the gross contract amount and the equipment cost). If a commencement date was entered, this field is mandatory.|
|lease|INFOLEASE|leaseBankSequenceNumber|Lease Bank Sequence Number added to Merchant Bank Account|
|lease|INFOLEASE|leaseBusinessSegmentCode|This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.|
|lease|INFOLEASE|leaseRenewalStatusCode|Lease Renewal status code|
|lease|INFOLEASE|leaseInterimRentAmount|The amount of interest payments received prior to the commencement of the contract.|
|lease|INFOLEASE|leaseAdditionalMid|This will be the Mainframe MID for ISOs that have a 15 digit MID that contains a zero added to the infolease record for cash advance|
|lease|INFOLEASE|leaseAssetSerialNumber|Lease Asset Serial Number|
|lease|INFOLEASE|leaseCustomerAddressLine1|The first line of the customers address.|
|lease|INFOLEASE|leaseLegalStatus|Lease Legal Status|
|lsn|Lsn|isEnabled|Is Enabled|
|lsn|Lsn|miscInfoText|Misc Info Text|
|lsn|Lsn|effectiveDate|Effective Date|
|merchantCountryOfOrigin|Merchant Country Of Origin|countryOfOrigin|Country Of Origin|
|merchantFraudAndSecurity|Merchant Fraud And Security|afdsMerchantAuthBlockStatus|Afds Merchant Auth Block Status|
|merchantFrontEnds|Merchant Front Ends|authNetworkCode1|Name Of The Network|
|merchantFrontEnds|Merchant Front Ends|authNetworkSecurityCode1|Code Which Can Be Used To Determine The Front End Network|
|merchantFrontEnds|Merchant Front Ends|authNetworkSecurityCode2|Code which is being used to determine the front end network |
|merchantFrontEnds|Merchant Front Ends|authNetworkCode2|Name Of The Secondary Network|
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteAuthLimitAmount|Merchant Lite Auth Limit Amount|
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteCreditLimitAmount|Merchant Lite Credit Limit Amount|
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteSalesLimitAmount|Merchant Lite Sales Limit Amount|
|merchantLocation|Merchant Location Information|city|Merchant City|
|merchantLocation|Merchant Location Information|country|Merchant Country|
|merchantLocation|Merchant Location Information|state|Merchant State|
|merchantMunicipality|Merchant Municipality|municipalityTaxInd|Municipality Tax Indicator|
|merchantMunicipality|Merchant Municipality|municipilatityCode|Municipality Code|
|merchantPortfolioType|Merchant Portfolio Type|byTransactionCount|Transaction Count Portfolio Size|
|merchantPortfolioType|Merchant Portfolio Type|offeringType|Offering Type|
|merchantPricingStructure|Merchant Pricing Structure|offeringType|Offering Type|
|miniPromoForStationOutage|Mini Promo For Station Outage|contractDate|Contract Date|
|miniPromoForStationOutage|Mini Promo For Station Outage|offeringType|Offering Type|
|miscReporting|MISC|enhancedReportingIndicator|Enhanced Reporting Indicator|
|miscReporting|MISC|farsFiscalDate|Financial Account Reporting System Fiscal Date|
|miscReporting|MISC|farsMediaTypeCode|Financial Activity Reporting System Media Type Code|
|miscReporting|MISC|farsReportFrequencyCode|Financial Activity Reporting System Report Frequency Code|
|miscellaneous|miscellaneous|restaurantGroupCode|Restaurant Group Code|
|miscellaneous|miscellaneous|revenueBookedDate|Revenue Booked Date|
|miscellaneous|miscellaneous|techEmail|Tech Email|
|miscellaneous|miscellaneous|branchDepositorIndicator|Branch Depositor Indicator|
|miscellaneous|miscellaneous|oilTradeClassCode|Class of Trade code for specific client usage|
|miscellaneous|miscellaneous|edcCode|edcCode|
|miscellaneous|miscellaneous|branchShortNumber|Branch Short Number|
|miscellaneous|miscellaneous|aggregatorMerchantIndicator|Aggregator Merchant Indicator|
|miscellaneous|miscellaneous|paymentEssentialsCode|Payment essentials bundle code|
|miscellaneous|miscellaneous|rejectNotifyCode|Reject Notification Code|
|miscellaneous|miscellaneous|online|Online Indicator for Omnipay Merchant|
|miscellaneous|miscellaneous|SECURITY_EMAIL|Security contact email|
|miscellaneous|miscellaneous|specialNationalAccountIndicator|Special National Account Indicator|
|miscellaneous|miscellaneous|xrefIndicator|Xref Indicator|
|miscellaneous|miscellaneous|emailtypecode|Type of Email Address|
|miscellaneous|miscellaneous|faxIndicator|Fax Indicator|
|miscellaneous|miscellaneous|volumeTierInterchangeFeeIndicator|Volume Tier Interchange Fee Indicator|
|miscellaneous|miscellaneous|emvIndicator|EMV Chip Enabled Indicator|
|miscellaneous|miscellaneous|loyaltyProcessingCode|Loyalty Processing Code|
|miscellaneous|miscellaneous|rawDataAddendumIndicator|Raw Data Addendum Indicator|
|miscellaneous|miscellaneous|arpCode|ARP Code|
|miscellaneous|miscellaneous|internetCode|Internet Code|
|miscellaneous|miscellaneous|volumeTierIndicator|Volume Tier Indicator|
|miscellaneous|miscellaneous|cmsServiceCodes|CMS Service Codes|
|miscellaneous|miscellaneous|fireSafetyActIndicator|Fire Safety Act Indicator|
|miscellaneous|miscellaneous|bankingCategoryCode|Banking Category Code|
|miscellaneous|miscellaneous|cashManagementIndicator|Cash Management Indicator|
|miscellaneous|miscellaneous|descriptorEntitledIndicator|Descriptor Entitled Indicator|
|miscellaneous|miscellaneous|branchLongNumber|Branch Long Number|
|miscellaneous|miscellaneous|caseManagementIndicator|Case Management Indicator|
|miscellaneous|miscellaneous|imprintersCount|Imprinter Quantity Bill Number|
|miscellaneous|miscellaneous|ncptAmount|Anticipated Mc/Visa® net contribution per transaction|
|miscellaneous|miscellaneous|domesticForeignIndicator|DomesticForeignIndicator|
|miscellaneous|miscellaneous|leaseCompanyCode|Lease Company Code|
|miscellaneous|miscellaneous|nrptAmount|Anticipated Mc/Visa® net revenue percentage|
|miscellaneous|miscellaneous|accountingUnitCode|Accounting Unit Code|
|miscellaneous|miscellaneous|pagobancomatIndex|Indicates when pagobancomat transactions are flagged as bill payment|
|miscellaneous|miscellaneous|paymentLowValue|Indicates if the Merchant is eligible to Qualify for UK domestic low value E-Commerce|
|miscellaneous|miscellaneous|doNotChargeVee|Do Not Charge Vee for Omnipay|
|modelAfterMerchant|Model After Merchant For Boarding Usage|offeringType|Offering Type|
|mondex|Mondex|miscInfoText|Misc Info Text|
|mondex|Mondex|effectiveDate|Effective Date|
|mondex|Mondex|isEnabled|Is Enabled|
|moneyTransfers|Money Transfers|pinEntryMethods|Pin Entry Methods|
|moneyTransfers|Money Transfers|miscInfoText|Misc Info Text|
|msipDetails|MSIP Details|msipFax2Number|MSIP Fax2 Number|
|msipDetails|MSIP Details|msipPlasticRegenerateIndicator|MSIP Plastic Regenerate Indicator|
|msipDetails|MSIP Details|msipCategoryLevelCode|MSIP Category Level Code|
|msipDetails|MSIP Details|msipNewAccountIndicator|MSIP New Account Indicator|
|msipDetails|MSIP Details|msipMaestroFloorAmount|MSIP Maestro Floor Amount|
|msipDetails|MSIP Details|msipContactName|MSIP Contact Name|
|msipDetails|MSIP Details|msipMaestroId|MSIP Maestro Id|
|msipDetails|MSIP Details|msipFax1Number|MSIP Fax1 Number|
|msipDetails|MSIP Details|msipAlternateCityName|MSIP Alternate City Name|
|msipDetails|MSIP Details|msipMailToOutletIndicator|MSIP Mail To Outlet Indicator|
|msipDetails|MSIP Details|msipMaestroFraudProneIndicator|MSIP Maestro Fraud Prone Indicator|
|msipDetails|MSIP Details|msipBacsIndicator|MSIP Bacs Indicator|
|msipDetails|MSIP Details|msipMailToChainIndicator|MSIP Mail To Chain Indicator|
|msipDetails|MSIP Details|msipVisaFloorAmount|MSIP Visa Floor Amount|
|msipDetails|MSIP Details|msipMailToBankIndicator|MSIP Mail To Bank Indicator|
|msipDetails|MSIP Details|msipChainRollupIndicator|MSIP Chain Rollup Indicator|
|msipDetails|MSIP Details|msipChainRollupDate|MSIP Chain Rollup Date|
|msipDetails|MSIP Details|msipTerminalCount|MSIP Terminal Count|
|msipDetails|MSIP Details|msipMaestroCeilingAmount|MSIP Maestro Ceiling Amount|
|msipDetails|MSIP Details|msipMastercardCurrencyCode|MSIP Mastercard Currency Code|
|msipDetails|MSIP Details|msipAlternateMerchantName|MSIP Alternate Merchant Name|
|msipDetails|MSIP Details|msipRecourseCode|MSIP Recourse Code|
|msipDetails|MSIP Details|msipHotCardIndicator|MSIP Hot Card Indicator|
|msipDetails|MSIP Details|msipMailToBusinessIndicator|MSIP Mail To Business Indicator|
|msipDetails|MSIP Details|msipVisaCeilingAmount|MSIP Visa Ceiling Amount|
|msipDetails|MSIP Details|msipInternationalDialNumber|MSIP International Dial Number|
|msipDetails|MSIP Details|msipVisaCurrencyCode|MSIP Visa Currency Code|
|msipDetails|MSIP Details|msipMaestroCashbackIndicator|MSIP Maestro Cashback Indicator|
|msipDetails|MSIP Details|msipMaestroMccCode|MSIP Maestro Mcc Code|
|msipDetails|MSIP Details|msipMailToAgentIndicator|MSIP Mail To Agent Indicator|
|msipDetails|MSIP Details|msipVisaCashbackIndicator|MSIP Visa Cashback Indicator|
|msipDetails|MSIP Details|msipPlasticFormatCode|MSIP Plastic Format Code|
|msipDetails|MSIP Details|msipBacsMerchantName|MSIP Bacs Merchant Name|
|msipDetails|MSIP Details|msipMailToCorporationIndicator|MSIP Mail To Corporation Indicator|
|mvbEmergingMarkets|Mvb Emerging Markets|offeringType|Offering Type|
|nationalAccountId|National Account Underwriting Account Id|nationalAccountId|National account id|
|nearRealTimeMessaging|Near RealTime Messaging|effectiveDate|Effective Date|
|nearRealTimeMessaging|Near RealTime Messaging|miscInfoText|Misc Info Text|
|nearRealTimeMessaging|Near RealTime Messaging|isEnabled|Is Enabled|
|omahaDebitSuspenseItemsRelease|Omaha Dd-623 Debit  Suspense Items Release - Channel Level|status|Program Status|
|onBoardingDetails|OnBoarding Details|linkForwardMerchantId|Link Forward Merchant Id|
|onBoardingDetails|OnBoarding Details|linkBackwardMerchantId|Link Backward Merchant Id|
|onBoardingDetails|OnBoarding Details|boardingOriginCode|Legacy field boarding origin code|
|onBoardingDetails|OnBoarding Details|convertedAccountDate|Converted Account Date|
|onBoardingDetails|OnBoarding Details|convertedAccountIndicator|Converted Account Indicator|
|onBoardingDetails|OnBoarding Details|boardingTypeCode|Boarding Type Code|
|onBoardingDetails|OnBoarding Details|boardingSourceCode|Code which indicates what boarding tool or process was used|
|panMasking|Pan Masking|offeringType|Offering Type|
|pathwardBankwire|Pathward Bankwire|futureUse2|Future Use 2|
|pathwardBankwire|Pathward Bankwire|futureUse1|Future Use 1|
|pathwardBankwire|Pathward Bankwire|beneficiaryZipCode|Beneficiary Zip Code|
|pathwardBankwire|Pathward Bankwire|beneficiaryStateCode|Beneficiary State Code|
|pathwardBankwire|Pathward Bankwire|beneficiaryCity|Beneficiary City|
|pathwardBankwire|Pathward Bankwire|beneficiaryStreetAddress|Beneficiary Street Address(No Po Box)|
|pathwardBankwire|Pathward Bankwire|seeBnfOnFndTab|See Bnf On Fnd Tab|
|pathwardEmergingMarkets|Pathward Emerging Markets|offeringType|Offering Type|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|participantType|Participant Type|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdUpi|Payment Facilitator Id Upi|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|offeringType|Offering Type|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|serviceType|Service Type for Omnipay|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|subMerchantId|Sub Merchant ID for Omnipay|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pspIndicator|Payment Service Provider Indicator|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|directPfFlag|Direct Pf Flag|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdDscv|Payment Facilitator Id Discover|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|parentId|Parent ID|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdAmex|Payment Facilitator Id Amex|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdVi|Payment Facilitator Id-Marketplace Id Vi|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdMc|Payment Facilitator Id Mc|
|paypalOptOutReason|Paypal Opt Out Reason|effectiveDate|Effective Date|
|paypalOptOutReason|Paypal Opt Out Reason|reasonCode|Opt Out Reason Code|
|platformSwitch3CrossReference|Platform Switch 3 Cross Reference|northChainBank|North Chain Bank|
|pos|Pos|miscInfoText|Misc Info Text|
|pos|Pos|pinEntryMethods|Pin Entry Methods|
|premiumPrepaid|Premium Prepaid|serviceEntlNumber|Service Entl Number|
|premiumPrepaid|Premium Prepaid|isEnabled|Is Enabled|
|premiumPrepaid|Premium Prepaid|effectiveDate|Effective Date|
|premiumPrepaid|Premium Prepaid|miscInfoText|Misc Info Text|
|pricingModel|Pricing Model|nonSwipedFee|Non Swiped Transaction Fee|
|pricingModel|Pricing Model|nonSwipedRate|Non Swiped Discount|
|pricingModel|Pricing Model|swipedRate|Swiped Discount|
|pricingModel|Pricing Model|swipedFee|Swiped Transaction Fee|
|pricingModel|Pricing Model|pricingModelType|Pricing Model Type|
|pricingMthdDisclosures|Pricing Method Disclosures|offeringType|Offering Type|
|pricingMthdDisclosures|Pricing Method Disclosures|pricingSchedule|Pricing Schedule|
|promotion|Promotion Tracking|promotionName1|Promotion Name One|
|promotion|Promotion Tracking|promotionName2|Promotion Name Two|
|promotion|Promotion Tracking|promotionName3|Promotion Name Three|
|promotion|Promotion Tracking|promotionName4|Promotion Name Four|
|promotion|Promotion Tracking|promotionName5|Promotion Name Five|
|prop51Conversion|Prop 51 Conversion|northShellMid|Original North Shell Mid/N|
|prop51Conversion|Prop 51 Conversion|propMerchantId|Original Prop Merchant Id|
|purchaseReturnAuthAutomation|Purchase Return Authorization Automation|status|Program Status|
|rapidDepositExceptionStatus|Rapid Deposit Exception Status|offeringType|Offering Type|
|rateLock|Rate Lock|billingExpirationDate|Billing Expiration Date|
|rateLock|Rate Lock|billingEffectiveDate|Billing Effective Date|
|rateLock|Rate Lock|rateLockLength|Number Of Years The Rate Lock Is In Place|
|recurringPayment|Recurring Payment|recurringPaymentsIndicator|Hosted Recurring Payments Indicator|
|referencedDeposit|Referenced Deposit|referenceNumberType|Reference Number Type|
|referencedDeposit|Referenced Deposit|depositReferenceNumber|Deposit Reference Number|
|restrictedUseTransmatchRewards|Restricted Use Transmatch Rewards Program|status|Program Status|
|retrievalConfig|Retrievals Config|email|email address|
|reversalConfig|Reversal Config|reversalTimeZoneCode|Reversal TimeZone Code|
|reversalConfig|Reversal Config|reversalDaylightSavingsIndicator|Reversal Daylight Savings Indicator|
|reversalConfig|Reversal Config|reversal24HourProcessIndicator|Reversal 24Hour Process Indicator|
|robertMorrisCollege|Robert Morris College|miscInfoText|Misc Info Text|
|robertMorrisCollege|Robert Morris College|isEnabled|Is Enabled|
|robertMorrisCollege|Robert Morris College|effectiveDate|Effective Date|
|rtp|Rtp|status|Program Status|
|sameDaySettlement|Same Day Settlement|currencyCd|Currency Code|
|sameDaySettlement|Same Day Settlement|status|Program Status|
|selectiveDivert|Negative Bankwire Selective Divert|status|Program Status|
|serviceAttr|Service Attribute|analyticsProductType|Product Offering That A Merchant Is Enrolled To Use.|
|serviceAttr|Service Attribute|clubNum|SAMS Club - Club Number|
|serviceAttr|Service Attribute|nxtRnwlDt|SAMS Club Next Renewal Date|
|serviceAttr|Service Attribute|rnwlAmtPaid|SAMS Club Renewal Amount Paid|
|serviceAttr|Service Attribute|newUpgRnwlInd|SAMS Club New/Upgrade/Renewal Indicator|
|serviceAttr|Service Attribute|ceoLPreference|Wells Ceo Preference Field|
|serviceAttr|Service Attribute|bobPreference|Wells Bob Preference Field|
|serviceAttr|Service Attribute|companyId|Wells Company Id Field|
|serviceAttr|Service Attribute|emvProgramStatus|EMV Program Status|
|serviceAttr|Service Attribute|memberShipId|SAMS Club Membership ID|
|serviceAttr|Service Attribute|mainStreetProgramstatus|Program Status|
|serviceAttr|Service Attribute|primaryEmailInd|Primary Email Indicator|
|serviceAttr|Service Attribute|cloverInsightsEmail|User Provided Clover Insights Email|
|serviceAttr|Service Attribute|mainStreetbillingEffectiveDate|Billing Effective Date|
|serviceAttr|Service Attribute|perkaProductType|Perka Product Type|
|serviceAttr|Service Attribute|contractSignDateTime|Date Time Contract Signed|
|serviceAttr|Service Attribute|perkaAccountNum|Perka Account Number|
|serviceAttr|Service Attribute|requestNewVruIdCd|Request New VRU Id For Compromised One|
|serviceAttr|Service Attribute|pinlessEcomStatus|Program Status for Pinless Ecomm|
|serviceAttr|Service Attribute|perkaUniqueId|Perka Unique Identifier|
|serviceAttr|Service Attribute|perkaTrainInd|Perka Training Indicator|
|serviceAttr|Service Attribute|perkaBillingEffectiveDate|Billing Effective Date for Perka|
|serviceAttr|Service Attribute|tckCpStatus|Program Status for Telecheck CP|
|serviceAttr|Service Attribute|tckCpSettlInd|Settlement Indicator for Telecheck CP|
|serviceAttr|Service Attribute|tckCpPrcsInd|Process Indicator Telecheck CP|
|serviceAttr|Service Attribute|tckCpServEntl|Service Entitlement for Telecheck CP|
|serviceAttr|Service Attribute|perkaAccountStatus|Account Status|
|serviceAttr|Service Attribute|payezeeyBillingEffectiveDate|Billing Effective Date|
|serviceAttr|Service Attribute|dbtTermIdStatus|Program Status for Debit Term Id|
|serviceAttr|Service Attribute|discPrmPrgOfferingType|offering Type for Discover Prm Prg|
|serviceAttr|Service Attribute|discPrmPrgStatus|Program Status for Discover Prm Prg|
|serviceAttr|Service Attribute|discPrmPrgPVI|PVI for Discover Prm Prg|
|serviceAttr|Service Attribute|discPrmPrgExpiryDate|Expiry Date for Discover Prm Prg|
|serviceAttr|Service Attribute|discPrmPrgEffectiveDate|Effective Date for Discover Prm Prg|
|serviceAttr|Service Attribute|discIncAuthOfferingType|Offering Type for Discover Inc Auth|
|serviceAttr|Service Attribute|dataRightsOptOutCode|Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.|
|serviceAttr|Service Attribute|mcMoneySendOfferingType|Offering Type for MC Moneysend|
|serviceAttr|Service Attribute|discIncAuthStatus|Program Status for Discover Inc Auth|
|serviceAttr|Service Attribute|discDbtAcpStatus|Program Status for Discover Debit Acceptance|
|serviceAttr|Service Attribute|visaActFndOfferingType|Offering Type for Visa Account Funding|
|serviceAttr|Service Attribute|visaActFndStatus|Program Status for Visa Account Funding|
|serviceAttr|Service Attribute|visaChkOutStatus|Program Sttatus for Visa Check Out|
|serviceAttr|Service Attribute|visaOctOfferingType|Offering Type for Visa Oct|
|serviceAttr|Service Attribute|visaOctStatus|Program Status for Visa Oct|
|serviceAttr|Service Attribute|visaAcctUpdStatus|Program Status for VISA Account Update|
|serviceAttr|Service Attribute|payezeeyOfferingType|Payeezy Offering Type|
|serviceAttr|Service Attribute|mcMoneySendStatus|Program Status for MC Moneysend|
|serviceAttr|Service Attribute|vspDomain|VSP domain Indicates the Corporate Identifier for TransArmor VeriFone Edition|
|serviceAttr|Service Attribute|vspBrand|VSP brand indicates the TransArmor VeriFone VSP Brand|
|serviceAttr|Service Attribute|veteransProgramType|Veterans Program Offering Type|
|serviceAttr|Service Attribute|veteransProgramstatus|Veterans Program Account Status|
|serviceAttr|Service Attribute|referralCode|Referral Code|
|serviceAttr|Service Attribute|payezeeyProgramStatus|Payeezy Program Status|
|serviceAttr|Service Attribute|webStore|Web Store|
|serviceAttr|Service Attribute|encryptTypeCode|Encryption type code|
|serviceAttr|Service Attribute|developerId|Developer ID|
|serviceAttr|Service Attribute|developerEmailId|Developer Email ID|
|serviceAttr|Service Attribute|masterpassstatus|Masterpass Status|
|serviceAttr|Service Attribute|masterpassofferingType|Masterpass Offering Type|
|serviceAttr|Service Attribute|vruServiceofferingType|VRU Services Offering Type|
|serviceAttr|Service Attribute|encryptTokenOverrideIndicator|Encryption multipay token override indicator|
|serviceAttr|Service Attribute|encryptExceptionKeyId|Encryption exception key ID|
|serviceAttr|Service Attribute|discDbtAcpOfferingType|Offering Type for Discover Debit Acceptance|
|serviceAttr|Service Attribute|term|Term|
|serviceAttr|Service Attribute|encryptTokenCode|Encryption token type code|
|serviceAttr|Service Attribute|encryptTokenHierarchyCode|Encryption multipay token hierarchy level code|
|serviceAttr|Service Attribute|encryptServiceLevelCode|Encryption security level code|
|serviceAttr|Service Attribute|transarmorProgramstatus|Transarmor Program Status|
|serviceAttr|Service Attribute|transarmorofferingType|Transarmor Offering Type|
|serviceAttr|Service Attribute|rebateAmount|EMV Rebate Amount|
|serviceAttr|Service Attribute|emvOfferingType|EMV Offering Type|
|serviceAttr|Service Attribute|gatewayApi|Fraud Detect Entry Point|
|serviceAttr|Service Attribute|fraudFlexStatus|Program Status for Fraud Flex|
|serviceAttr|Service Attribute|emvBillingEffectiveDate|EMV Billing Effective Date|
|serviceAttr|Service Attribute|fraudFlexOfferingType|Offering Type for Fraud Flex|
|serviceAttr|Service Attribute|fraudFlexBillingEffectiveDate|Billing Effective Date for Fraud Flex|
|serviceAttr|Service Attribute|emvEnablementStatus|Program Status for EMV Enablement|
|serviceAttr|Service Attribute|fraudDetectstatus|Program Status for Fraud Detect|
|serviceAttr|Service Attribute|verifoneProtectWsp|Verifone Protect W/SP for  Transarmor|
|serviceAttr|Service Attribute|fraudDetectBillingEffectiveDate|Billing Effective Date for Fraud Detect|
|serviceAttr|Service Attribute|tempusProgramStatus|Tempus Program Status|
|serviceAttr|Service Attribute|lcrDebitStatus|Program Status for LCR Debit Flags (Optional)|
|serviceAttr|Service Attribute|mobInd|Mobile Indicator for BP Mobile|
|serviceAttr|Service Attribute|enrollmentStatus|Enrollment Status for Wisely Entitlement|
|serviceAttr|Service Attribute|merchantIdentifier|Merchant Identifier for Wisely Entitlement|
|serviceAttr|Service Attribute|networkTokenBillingEffectiveDate|Billing Effective Date for Network Tokens|
|serviceAttr|Service Attribute|networkTokenOfferingType|Offering Type for Network Tokens|
|serviceAttr|Service Attribute|transactionInsightStatus|Program Status for Transaction Insights|
|serviceAttr|Service Attribute|entInsightBillingEffectiveDate|Billing Effective Date for Enterprise Insights|
|serviceAttr|Service Attribute|terminalType01|Terminal Type 01 for BP Mobile|
|serviceAttr|Service Attribute|networkTokenStatus|Program Status for Network Tokens|
|serviceAttr|Service Attribute|discover|Discover Token|
|serviceAttr|Service Attribute|americanExpress|American Express Network Tokens|
|serviceAttr|Service Attribute|convenienceFeeInd|Convenience Fee Indicator for BP Mobile|
|serviceAttr|Service Attribute|chargebackInd|OEMV Chargeback Writeoff Indicator for BP Mobile|
|serviceAttr|Service Attribute|masterCard|Master Card Network Tokens|
|serviceAttr|Service Attribute|bpMobiletermType|Mobile Terminal Type for BP Mobile|
|serviceAttr|Service Attribute|fiservTokenRequesterId|Fiserv Token Requester ID for Network Tokens|
|serviceAttr|Service Attribute|entInsightOfferingType|Offering Type for Enterprise Insights|
|serviceAttr|Service Attribute|lcrStatus|Program Status of LCR Fallback|
|serviceAttr|Service Attribute|terminalType03|Terminal Type 03 for BP Mobile|
|serviceAttr|Service Attribute|ebtFnsNum|EBT FNS Number for BP Mobile|
|serviceAttr|Service Attribute|transarmorP2peStatus|Transrmor P2PE Pragram Status|
|serviceAttr|Service Attribute|rsavpki|rsavpki for Transarmor|
|serviceAttr|Service Attribute|verifoneProtect|Verifone Protect for Transarmor|
|serviceAttr|Service Attribute|fraudDetectofferingType|Offering Type for Fraud Detect|
|serviceAttr|Service Attribute|emvBillingExpirationDate|EMV Billing Expiration Date|
|serviceAttr|Service Attribute|ingenicoOnguard|Ingenico On-Guard for Transarmor|
|serviceAttr|Service Attribute|gbsPosInsofferingType|Offering Type for GBS POS Installment|
|serviceAttr|Service Attribute|gbsPosInsStatus|Program Status for GBS POS Installment|
|serviceAttr|Service Attribute|channel|Channel for GBS POS Installments|
|serviceAttr|Service Attribute|ecommercePlatform|Ecommerce Platform for GBS POS Installments|
|serviceAttr|Service Attribute|partner|Partner for GBS POS Installments|
|serviceAttr|Service Attribute|merchSurchargeProgSolutionType|Solution Type for Merchant Surcharge Program|
|serviceAttr|Service Attribute|merchSurchargeProgEffectiveDate|Surcharge Effective Date for Merchant Surcharge Program|
|serviceAttr|Service Attribute|entInsightDemographicStatus|Program Status for Enterprise Insights Demographic|
|serviceAttr|Service Attribute|3des|3DES for Transarmor|
|serviceAttr|Service Attribute|aesDukpt|AES DUKPT for Transarmor|
|serviceAttr|Service Attribute|merchSurchargeProgOfferingType|Offering Type for Merchant Surcharge Program|
|serviceAttr|Service Attribute|merchSurchargeProgStatus|Program Status for Merchant Surcharge Program|
|serviceAttr|Service Attribute|merchSurchargeProgSurchargeRate|Surcharge Rate for Merchant Surcharge Program|
|serviceAttr|Service Attribute|personalDataProtectionBillingEffectiveDate|Billing Effective Date for Personal Data Protection|
|serviceAttr|Service Attribute|personalDataProtectionOfferingType|Offering Type for Personal Data Protection|
|serviceAttr|Service Attribute|tckCpPrdct|Product for Telecheck CP|
|serviceAttr|Service Attribute|reccuringCharge|Recurring Charge|
|serviceAttr|Service Attribute|entInsightLobbyOfferingType|Offering Type for Enterprise Insights Lobby|
|serviceAttr|Service Attribute|entInsightStatus|Program Status for Enterprise Insights|
|serviceAttr|Service Attribute|advInsightBillingEffectiveDate|Billing Effective Date for Advertising Insights|
|serviceAttr|Service Attribute|advInsightOfferingType|Offering Type for Advertising Insights|
|serviceAttr|Service Attribute|advInsightStatus|Program Status for Advertising Insights|
|serviceAttr|Service Attribute|transactionInsightBillingEffectiveDate|Billing Effective Date for Transaction Insights|
|serviceAttr|Service Attribute|transactionInsightOfferingType|Offering Type for Transaction Insights|
|serviceAttr|Service Attribute|personalDataProtectionStatus|Program Status for Personal Data Protection|
|serviceAttr|Service Attribute|entInsightLobbyBillingEffectiveDate|Billing Effective Date for Enterprise Insights Lobby|
|serviceAttr|Service Attribute|visa|Visa Network Tokens|
|serviceAttr|Service Attribute|entInsightLobbyStatus|Program Status for Enterprise Insights Lobby|
|serviceAttr|Service Attribute|entInsightBenchBillingEffectiveDate|Billing Effective Date for Enterprise Insights Bench|
|serviceAttr|Service Attribute|entInsightBenchofferingType|Offering Type for Enterprise Insights Bench|
|serviceAttr|Service Attribute|entInsightBenchStatus|Program Status for Enterprise Insights Bench|
|serviceAttr|Service Attribute|entInsightDemographicbillingEffectiveDate|Billing Effective Date for Enterprise Insights Demographic|
|serviceAttr|Service Attribute|entInsightDemographicOfferingType|Offering Type for Enterprise Insights Demographic|
|serviceAttr|Service Attribute|thirdParty|Third Party for Merchant Surcharge Program|
|settlementConfig|Settlement Config|billbackIndicatorCode|Billback Indicator Code|
|settlementConfig|Settlement Config|surchargeExceptionCode|Determine If A Billback Surcharge Should Be Applied|
|settlementConfig|Settlement Config|batchCaptureIndicator|Batch Capture Indicator|
|settlementConfig|Settlement Config|chargeBarer|Charge Barer for Omnipay|
|settlementConfig|Settlement Config|dcc|DCC Merchant for Omnipay|
|settlementConfig|Settlement Config|billbackSurchargeRate|Billback Surcharge Rate|
|settlementConfig|Settlement Config|billbackRoundingIndicator|Bill Back Rounding Indicator|
|settlementConfig|Settlement Config|processingTypeCode|Processing Type Code|
|settlementConfig|Settlement Config|settleNetworkCode|Settle Network Code|
|settlementConfig|Settlement Config|settleFrequencyCode|Settle Frequency Code|
|settlementConfig|Settlement Config|discountCalculationCode|Discount Calculation Code|
|settlementConfig|Settlement Config|billbackCode|Billback Code|
|settlementConfig|Settlement Config|billbackHierarchyCode|Billback Hierarchy Code|
|settlementConfig|Settlement Config|billbackSurchargeCode|Billback Surcharge Code|
|settlementConfig|Settlement Config|settlementMethod|The settlement method assigned to for the merchant|
|settlementSwitch|Settlement Switch|isEnabled|Is Enabled|
|settlementSwitch|Settlement Switch|effectiveDate|Effective Date|
|settlementSwitch|Settlement Switch|miscInfoText|Misc Info Text|
|signatureCapture|Signature Capture|signatureCaptureRejectsIndicator|Signature Capture Rejects Indicator|
|signatureCapture|Signature Capture|signatureCaptureIndicator|Signature Capture Indicator|
|southFrontEndBridge|Sfe Sunset Bridge Merchant Conversions|status|Program Status|
|southHdcLateCutC|South Platform Hdc Late Batch Cut C|status|Program Status|
|specialProgramIndicators|Special Program Indicators|chase|Chase|
|specialProgramIndicators|Special Program Indicators|walmartSamsClub|Walmart SamsClub|
|specialProgramIndicators|Special Program Indicators|syncronyPL|Syncrony PL|
|specialProgramIndicators|Special Program Indicators|upi|Upi|
|specialProgramIndicators|Special Program Indicators|visaAEO|visa AEO|
|specialProgramIndicators|Special Program Indicators|lbrandss|Lbrandss|
|specialProgramIndicators|Special Program Indicators|toysUs|Toys Us|
|specialProgramIndicators|Special Program Indicators|canadaDebit|Canada Debit|
|specialProgramIndicators|Special Program Indicators|walmartKotak|Walmart Kotak|
|specialProgramIndicators|Special Program Indicators|walmartCommercial|Walmart Commercial|
|specialProgramIndicators|Special Program Indicators|star|Star|
|specialProgramIndicators|Special Program Indicators|chaseNet|Chase Net|
|specialProgramIndicators|Special Program Indicators|valueLink|Value Link|
|specialProgramIndicators|Special Program Indicators|dicksSporting|Dicks Sporting|
|specialProgramIndicators|Special Program Indicators|walmartBusiness|Walmart Business|
|specialProgramIndicators|Special Program Indicators|amexFranchise|Amex Franchise|
|specialProgramIndicators|Special Program Indicators|walmartCobranded|Walmart Cobranded|
|specialProgramIndicators|Special Program Indicators|amexMarketing|Amex Marketing|
|specialProgramIndicators|Special Program Indicators|visaCash|Visa Cash|
|specialProgramIndicators|Special Program Indicators|mondex|Mondex|
|specialProgramIndicators|Special Program Indicators|univofPenn|Univof Penn|
|specialProgramIndicators|Special Program Indicators|robertMorrisCollege|Robert Morris College|
|specialProgramIndicators|Special Program Indicators|duguesneUniv|Duguesne Univ|
|standardGCMisc|Standard GC Misc|effectiveDate|Effective Date|
|standardGCMisc|Standard GC Misc|isEnabled|Is Enabled|
|standardGCMisc|Standard GC Misc|miscInfoText|Misc Info Text|
|standardGCProject|Standard GC Project|miscInfoText|Misc Info Text|
|standardGCProject|Standard GC Project|effectiveDate|Effective Date|
|standardGCProject|Standard GC Project|isEnabled|Is Enabled|
|standardGCReport|Standard GC Report|effectiveDate|Effective Date|
|standardGCReport|Standard GC Report|isEnabled|Is Enabled|
|standardGCReport|Standard GC Report|miscInfoText|Misc Info Text|
|statementConfig|Statement Config|cardAlternateCity|Card Alternate City|
|statementConfig|Statement Config|cardAlternateName|Card Alternate Name|
|statementConfig|Statement Config|statementDeliveryCode|Statement delivery method|
|statementConfig|Statement Config|email|Statement email address|
|statementConfig|Statement Config|cardAlternateStateCode|Card Alternate State Code|
|statementConfig|Statement Config|statementFaxIndicator|Statement Fax Indicator|
|statementConfig|Statement Config|statementTypeCode|Statement type summary or detail|
|statementConfig|Statement Config|statementMailToCode|Indicates where printed statement will be sent|
|statementConfig|Statement Config|statementHoldIndicator|Code determining whether or not to hold the merchant statements|
|statementConfig|Statement Config|statementDebitFeeCode|Code determining whether to print the online debit fees in summary form or broken out by fee class code on the merchant statement|
|statementConfig|Statement Config|icplusStatementFormatCode|Code determining the interchange fee information the System prints on the merchant statement|
|statementConfig|Statement Config|statementFaxNumber|Statement fax number|
|stockExchange|Stock Exchange/Ctry Name|stockExchangeName|Stock Exchange Name|
|stockExchange|Stock Exchange/Ctry Name|countryName|Country Name|
|sunocoAutoboarding|Sunoco Autoboarding|rollback5CentIndicator|Rollback 5 Cent Indicator|
|sunocoAutoboarding|Sunoco Autoboarding|posPartnerName|Pos Partner Name|
|transactionControl|Transaction Control|mastercardTieredMerchantId|Mastercard tiered merchant ID|
|transactionControl|Transaction Control|mastercardIramIndicator|Mastercard Incremental Reversal Auth Match indicator|
|transactionControl|Transaction Control|globalGatewayE4Indicator|Indicates if the merchant uses the Payeezy Gateway|
|transactionControl|Transaction Control|globalGatewayE4EffectiveDate|Payeezy gateway effective date|
|transactionControl|Transaction Control|visaIramIndicator|Visa Incremental Reversal Auth Match indicator |
|transactionControl|Transaction Control|fraudFlexIndicator|Fraud Flex Detect Indicator|
|transactionControl|Transaction Control|globalGatewayE4CurrencyCode|Currency code field used for default Payeezy Gateway currency for US domestic usage|
|transactionControl|Transaction Control|fraudFlexEffectiveDate|Fraud Flex Effective Date|
|transactionControl|Transaction Control|efraudServiceCode|EFraud Service level code|
|transactionControl|Transaction Control|cardActivatedTerminalCode|Merchant identified type of cardholders activated terminals that will be accepted |
|transactionControl|Transaction Control|commercialCardInterchangeServiceCode|Indicates the level of participation in the mastercard or visa commercial card interchange service|
|transactionControl|Transaction Control|visaTechnologyMigrationProgramServiceLevelCode|Visa Technology Migration Program service level code|
|transactionControl|Transaction Control|visaMerchantVerificationValue|Visa merchant verification value|
|transactionControl|Transaction Control|visaDebitAcceptIndicator|Describes level of Visa Debit Acceptance |
|transactionControl|Transaction Control|visaMviReserveAmount|VISA MVI Reserve amount|
|transactionControl|Transaction Control|visaRelationshipIndicator|Visa relationship particpant indicator|
|transactionControl|Transaction Control|visaTechnologyMigrationProgramAuthSourceCode|Visa Technology Migration Program  authorization source code|
|transactionControl|Transaction Control|visaTechnologyMigrationProgramCardholderIdCode|Visa Technology Migration Program  cardholder ID code|
|transactionControl|Transaction Control|visaTechnologyMigrationProgramEntryMode|Visa Technology Migration Program terminal entry mode code|
|transactionControl|Transaction Control|visaTechnologyMigrationProgramPointofsaleCapabilityCode|Visa Technology Migration Program terminal capability code |
|transactionControl|Transaction Control|visaTechnologyMigrationProgramRequestCode|Visa Technology Migration Program request code|
|trustKeeper|Trust Keeper|trustkeeperIndicator|Trustkeeper Indicator|
|trustKeeper|Trust Keeper|trustkeeperDate|Trustkeeper Date|
|univofPenn|Univof Penn|effectiveDate|Effective Date|
|univofPenn|Univof Penn|miscInfoText|Misc Info Text|
|univofPenn|Univof Penn|serviceEntlNumber|Service Entl Number|
|univofPenn|Univof Penn|isEnabled|Is Enabled|
|valueLink|Value Link|miscInfoText|Misc Info Text|
|valueLink|Value Link|effectiveDate|Effective Date|
|valueLink|Value Link|isEnabled|Is Enabled|
|visaCash|Visa Cash|effectiveDate|Effective Date|
|visaCash|Visa Cash|miscInfoText|Misc Info Text|
|visaCash|Visa Cash|isEnabled|Is Enabled|
|wfbCanadaEmergingMarkets|Wfb Canada Emerging Markets|offeringType|Offering Type|
|wfbSurcharge|Wfpg Surcharge Acct|offeringType|Offering Type|



<!-- type: tab-end -->  

