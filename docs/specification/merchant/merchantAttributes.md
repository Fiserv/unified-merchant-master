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
---
tags: [chargebackConfig]
---
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

|Domain|Domain Description|Attribute Name|Attribute Description |Valid Value |
|------|------------------|--------------|----------------------|-------------|
|billmatrix|Billmatrix|status|Program Status|ACCEPTED,NOT_ACCEPTED|
|conversionInformation|Conversion  Account Source System Data|status|Program Status|ACTIVE,CANCEL|
|wfbSurcharge|Wfpg Surcharge Acct|offeringType|Offering Type|EBILL_EXPRESS_SURCHARGE,WFPG_SURCHARGE_ACCT|
|authMatchExclusion|Auth Match Exclusion|southAuthMatchExclusion|South Auth Match Exclusion|FULL_MID_MATCHING,ROOT_LEVEL_MATCHING|
|disregardedEntity|Disregarded Entity|status|Program Status|NO,YES|
|globalCurrencySolutions|Global Currency Solutions|offeringType|Offering Type|PRISMATIC|
|miscellaneous|miscellaneous|restaurantGroupCode|Restaurant Group Code||
|reversalConfig|Reversal Config|reversal24HourProcessIndicator|Reversal 24Hour Process Indicator||
|statementConfig|Statement Config|statementTypeCode|Statement type summary or detail||
|electronicTicketCapture|Electronic Ticket Capture|etcOptionCode|Code identifying the type of electronic ticket capture processing used||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdMc|Payment Facilitator Id Mc||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdMc|Payment Facilitator Id Mc||
|fundingConfig|Funding Configuration|fundingBankCode|Funding Bank Code||
|settlementConfig|Settlement Config|chargeBarer|Charge Barer for Omnipay||
|msipDetails|MSIP Details|msipFax1Number|MSIP Fax1 Number||
|transactionControl|Transaction Control|globalGatewayE4Indicator|Indicates if the merchant uses the Payeezy Gateway||
|transactionControl|Transaction Control|fraudFlexEffectiveDate|Fraud Flex Effective Date||
|transactionControl|Transaction Control|cardActivatedTerminalCode|Merchant identified type of cardholders activated terminals that will be accepted ||
|fundingConfig|Funding Configuration|financialAdjustmentsFundingCategoryCode|Funding Category Code||
|miscellaneous|miscellaneous|fireSafetyActIndicator|Fire Safety Act Indicator||
|msipDetails|MSIP Details|msipAlternateMerchantName|MSIP Alternate Merchant Name||
|fundingConfig|Funding Configuration|feesFundingDivertCode|Funding Divert Code||
|contract|Contract|clientTariff|This the merchant tariff assigned to the merchant||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramAuthSourceCode|Visa Technology Migration Program  authorization source code||
|purchaseReturnAuthAutomation|Purchase Return Authorization Automation|status|Program Status|ENABLED,NOT_ENABLED|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdDscv|Payment Facilitator Id Discover||
|isoServices|Iso Services|isoIdMc|Iso Id Mc||
|fundingConfig|Funding Configuration|achSuspenseHoldIndicator|ACH suspense hold indicator||
|miscellaneous|miscellaneous|xrefIndicator|Xref Indicator||
|statementConfig|Statement Config|statementMailToCode|Indicates where printed statement will be sent||
|miscReporting|MISC|farsMediaTypeCode|Financial Activity Reporting System Media Type Code||
|fundingConfig|Funding Configuration|temporaryToDate|Temporary To Date||
|fundingConfig|Funding Configuration|depositAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|pathwardBankwire|Pathward Bankwire|beneficiaryCity|Beneficiary City||
|commercialCardInterchangeService|Commercial Card Interchange Service|ccisMerchantIncome|Commercial Card Interchange Service Merchant Income||
|msipDetails|MSIP Details|msipVisaCeilingAmount|MSIP Visa Ceiling Amount||
|msipDetails|MSIP Details|msipNewAccountIndicator|MSIP New Account Indicator||
|miscellaneous|miscellaneous|paymentEssentialsCode|Payment essentials bundle code||
|fundingConfig|Funding Configuration|reversalsBankSequenceNumber|Funding Bank Sequence||
|miscellaneous|miscellaneous|internetCode|Internet Code||
|authSettings|Auth Settings|authTypeCode|Auth Type Code||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramCardholderIdCode|Visa Technology Migration Program  cardholder ID code||
|fundingConfig|Funding Configuration|chargebacksFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|rateLock|Rate Lock|billingExpirationDate|Billing Expiration Date||
|fundingConfig|Funding Configuration|convenienceFeeCode|Convenience fee code to indicate the ABA or DDA to be charged||
|rtp|Rtp|status|Program Status|ACTIVE,CANCEL|
|southFrontEndBridge|Sfe Sunset Bridge Merchant Conversions|status|Program Status|ACTIVE,CANCEL|
|onBoardingDetails|OnBoarding Details|boardingOriginCode|Legacy field boarding origin code||
|fundingConfig|Funding Configuration|fundingRppMinimumAmount|Revolving payment plan minimum dollar amount||
|avsControl|AVS Control|avsUnavailableIndicator|Address verification service unavailable indicator||
|indemnification|Indemnification|indemnificationDate|Indemnification Date||
|depositRequirement|Deposit Requirement|programGuideVersion|Program Guide Version||
|sunocoAutoboarding|Sunoco Autoboarding|rollback5CentIndicator|Rollback 5 Cent Indicator||
|contractExpirationDate|Contract Expiration Date Notifications/Flag|contractExpirationDate|Contract Expiration Date||
|financialBuAssignmentValues|Financial Bu Assignment Values|financeEntity|Finance Entity||
|onBoardingDetails|OnBoarding Details|boardingSourceCode|Code which indicates what boarding tool or process was used||
|msipDetails|MSIP Details|msipVisaCurrencyCode|MSIP Visa Currency Code||
|msipDetails|MSIP Details|msipVisaCashbackIndicator|MSIP Visa Cashback Indicator||
|additionalTaxInfo|Additional Tax Information|incomeTaxCode|Income Tax Code||
|msipDetails|MSIP Details|msipMaestroId|MSIP Maestro Id||
|additionalBusinessInfo|Additional Business Information|rccCode|Merchant Retailer Category||
|creditSettings|Credit Settings|creditBinInclusionIndicator|Credit BIN Inclusion Indicator||
|financialBuAssignmentValues|Financial Bu Assignment Values|futureUse2|Future Use 2||
|nationalAccountId|National Account Underwriting Account Id|nationalAccountId|National account id||
|fundingConfig|Funding Configuration|depositAdjustmentsFundingDivertCode|Funding Divert Code||
|fundingConfig|Funding Configuration|feesFundingCategoryCode|Funding Category Code||
|settlementConfig|Settlement Config|settleFrequencyCode|Settle Frequency Code||
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingDivertCode|Funding Divert Code||
|fundingConfig|Funding Configuration|depositsBankSequenceNumber|Funding Bank Sequence||
|fundingConfig|Funding Configuration|depositAdjustmentsFundingCategoryCode|Funding Category Code||
|channelLevelDiscoverPromotionalPvi|Discover Promotional Program Verification Identifier - Channel Level|status|Program Status|ACTIVE,CANCEL|
|merchantFraudAndSecurity|Merchant Fraud And Security|afdsMerchantAuthBlockStatus|Afds Merchant Auth Block Status|AFDS_AUTH_BLOCK,AFDS_AUTH_UNBLOCK|
|enhanceDebitCompletionFlow|Enhance Debit Completion Flow For Pts Direct Send Merchants|status|Program Status|ENHANCED_DB_FLOW_OFF,ENHANCED_DB_FLOW_ON|
|compassSpecialFeatures|Compass Front End Generated Refund Auths|visaToleranceCheckInd|Visa Tolerance Check Ind|NO,YES|
|inHouseAuthConfig|InHouse Auth Configuration|inHouseAuthCaptureCode|InHouse Authorization Capture Code||
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteAuthLimitAmount|Merchant Lite Auth Limit Amount||
|billingConfig|Billing cofiguration|retailerRateCode|Retailer rate code specific client usage||
|fundingConfig|Funding Configuration|fundingExcludeDailyLimitAmount|Merchant funding exclusion daily sales limit amount||
|fundingConfig|Funding Configuration|fundingRppMinimumReserveAmount|Revolving payment plan minimum reserve amount||
|miscellaneous|miscellaneous|accountingUnitCode|Accounting Unit Code||
|billingConfig|Billing cofiguration|billSuppliesShippingIndicator|Bill supplies shipping and handling indicator||
|miscReporting|MISC|farsReportFrequencyCode|Financial Activity Reporting System Report Frequency Code||
|fundingConfig|Funding Configuration|funding30DayOverrideDate|Funding 30 day daily override date||
|fundingConfig|Funding Configuration|temporaryFromDate|Temporary From Date||
|platformSwitch3CrossReference|Platform Switch 3 Cross Reference|northChainBank|North Chain Bank||
|rateLock|Rate Lock|billingEffectiveDate|Billing Effective Date||
|msipDetails|MSIP Details|msipFax2Number|MSIP Fax2 Number||
|miscellaneous|miscellaneous|ncptAmount|Anticipated Mc/VisaÂ® net contribution per transaction||
|settlementConfig|Settlement Config|billbackIndicatorCode|Billback Indicator Code||
|merchantLocation|Merchant Location Information|city|Merchant City||
|transactionControl|Transaction Control|visaMviReserveAmount|VISA MVI Reserve amount||
|transactionControl|Transaction Control|visaDebitAcceptIndicator|Describes level of Visa Debit Acceptance ||
|highRiskMonitoring|High Risk Monitoring|offeringType|Offering Type|BINGO,CBD_CANNABIS,CNP_PHARMACY,CNP_TOBACCO_VAPE,CRYPTOCURRENCY,GAMBLING,HIGH_RISK,LOTTERY,MSB,NFT,NUTRACEUTICALS,ONLINE_FIREARMS,SKILLED_GAMES,SOCIAL_GAMING|
|merchantFrontEnds|Merchant Front Ends|authNetworkSecurityCode1|Code Which Can Be Used To Determine The Front End Network||
|msipDetails|MSIP Details|msipMastercardCurrencyCode|MSIP Mastercard Currency Code||
|miscellaneous|miscellaneous|techEmail|Tech Email||
|wfbCanadaEmergingMarkets|Wfb Canada Emerging Markets|offeringType|Offering Type|DAILY_FANTASY_SPORTS,ONLINE_GAMBLING|
|financialBuAssignmentValues|Financial Bu Assignment Values|status|Program Status|ACTIVE,CANCEL|
|cardconnect|Cardconnect File Identifier|status|Program Status|ACTIVE,CANCEL|
|mvbEmergingMarkets|Mvb Emerging Markets|offeringType|Offering Type|CBD_CANNABIS,DFS,LEGAL_GAMBLING,MSB,SINGLE_MID_PFAC,VISA_MC_HBR|
|dccForIab|Dynamic Currency Conversion For International Agent Bank|offeringType|Offering Type|DCC,DYNAMIC_PRICING|
|depositRequirement|Deposit Requirement|offeringType|Offering Type|NO,YES|
|franchise|Franchise|offeringType|Offering Type|NO,YES|
|cardbrandPassThruFees|Cardbrand Pass Thru Fees|offeringType|Offering Type|STANDARD_OFFERING|
|chargebackConfig|chargeback Configuration|chargebackReportDestinationCode|Chargeback Report Destination Code||
|onBoardingDetails|OnBoarding Details|linkBackwardMerchantId|Link Backward Merchant Id||
|boardingAdditionalInfo|Merchant Boarding Additional Information|wisoSalesRepId|Sales rep id of the wholesale iso employee||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdVi|Payment Facilitator Id-Marketplace Id Vi||
|fundingConfig|Funding Configuration|fundingMethodCode|Funding method code Code determining how funds will be settled||
|avsControl|AVS Control|avsZipIndicator|Address verification service zip indicator||
|contract|Contract|protectAgainstFXChange|Indicate if the Merchant is protected against currency fluctuations on the event the transaction is disputed||
|fundingConfig|Funding Configuration|fundingNotifyIndicator|Funding notification indicator||
|fundingConfig|Funding Configuration|fundingNotifyMethodCode|Funding notification method code||
|chargebackConfig|chargeback Configuration|email|email||
|keyReferenceNumber|Key Reference Number|keyReferenceNumber|Credit Only Key Reference Number||
|sunocoAutoboarding|Sunoco Autoboarding|posPartnerName|Pos Partner Name||
|referencedDeposit|Referenced Deposit|depositReferenceNumber|Deposit Reference Number||
|msipDetails|MSIP Details|msipMailToBankIndicator|MSIP Mail To Bank Indicator||
|fundingConfig|Funding Configuration|interchangeAssessmentsBankSequenceNumber|Funding Bank Sequence||
|msipDetails|MSIP Details|msipAlternateCityName|MSIP Alternate City Name||
|msipDetails|MSIP Details|msipMaestroCeilingAmount|MSIP Maestro Ceiling Amount||
|promotion|Promotion Tracking|promotionName4|Promotion Name Four||
|fundingConfig|Funding Configuration|discountsFundingCategoryCode|Funding Category Code||
|avsControl|AVS Control|avsYesIndicator|Address verification service Yes indicator||
|fundingConfig|Funding Configuration|fundingDailyOverrideIndicator|Funding Override Indicator||
|conversionInformation|Conversion  Account Source System Data|salesmanCode|Salesman Code||
|miniPromoForStationOutage|Mini Promo For Station Outage|contractDate|Contract Date||
|msipDetails|MSIP Details|msipBacsIndicator|MSIP Bacs Indicator||
|miscellaneous|miscellaneous|emvIndicator|EMV Chip Enabled Indicator||
|miscellaneous|miscellaneous|branchShortNumber|Branch Short Number||
|miscellaneous|miscellaneous|rawDataAddendumIndicator|Raw Data Addendum Indicator||
|fundingConfig|Funding Configuration|discountsBankSequenceNumber|Funding Bank Sequence||
|irsSupplementalInformation|Irs Supplemental Information|econsentDate|Econsent Date||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|directPfFlag|Direct Pf Flag|A_AMOB_1MM,M_MC_1MM,NONE,R_MC_VI_1MM,T_ MC_AMOB_1MM,V_VI_1MM,W_MC_VI_AMOB_1MM,X_VI_AMOB_1MM|
|independentSoftwareVendor|Independent Software Vendor (Isv) Global Indicator|offeringType|Offering Type|BYPASS_CLOVER_ISV|
|sameDaySettlement|Same Day Settlement|currencyCd|Currency Code|CANADIAN_DOLLAR,EURO,GRT_BRITISH_POUND,USA_DOLLAR|
|internalItUse|Internal It Use - Trigger Feeds And Save Data|discoverTrigger|Registration Merchant Feed To Discover|NO,YES|
|compassOnNorth|Compass Podb Functionality On North|partialReversals|Eligible For Partial Reversals|NO_PARTIAL_REVERSALS,PARTIAL_REVERSALS|
|rapidDepositExceptionStatus|Rapid Deposit Exception Status|offeringType|Offering Type|NO_RAPID_DEP_OVERRIDE,RAPID_DEP_IS_ALLOWED,RAPID_DEP_NOT_ALLOWED|
|pathwardBankwire|Pathward Bankwire|seeBnfOnFndTab|See Bnf On Fnd Tab|SEE_BNF_ON_FND_TAB|
|miniPromoForStationOutage|Mini Promo For Station Outage|offeringType|Offering Type|STANDARD_OFFERING|
|onBoardingDetails|OnBoarding Details|convertedAccountDate|Converted Account Date||
|fundingConfig|Funding Configuration|fundingExclude30DayLimitAmount|Merchant funding exclusion monthly sales limit amount||
|chargebackConfig|chargeback Configuration|chargebackPrenoteDays|Chargeback Prenote Days||
|miscReporting|MISC|farsFiscalDate|Financial Account Reporting System Fiscal Date||
|fundingConfig|Funding Configuration|fundingNotifyFaxNumber|Funding notification contact name||
|fundingConfig|Funding Configuration|temporary30DayLimitAmount|Temporary monthly limit amount||
|fundingConfig|Funding Configuration|temporaryDailyLimitAmount|Temporary Daily Limit Amount||
|iolCanadianVatRegNumber|Iol Canadian Vat Reg Number|canadianVatRegNumber|Canadian Vat Registration Number||
|globalCurrencySolutions|Global Currency Solutions|offeringSubType2|Globally Used For All North Backend Sales Channels||
|prop51Conversion|Prop 51 Conversion|northShellMid|Original North Shell Mid/N||
|financialBuAssignmentValues|Financial Bu Assignment Values|fmgGroupCode|Fmg Group Code||
|msipDetails|MSIP Details|msipBacsMerchantName|MSIP Bacs Merchant Name||
|msipDetails|MSIP Details|msipMaestroMccCode|MSIP Maestro Mcc Code||
|miscellaneous|miscellaneous|domesticForeignIndicator|DomesticForeignIndicator||
|merchantMunicipality|Merchant Municipality|municipilatityCode|Municipality Code||
|transactionControl|Transaction Control|efraudServiceCode|EFraud Service level code||
|settlementConfig|Settlement Config|billbackHierarchyCode|Billback Hierarchy Code||
|fundingConfig|Funding Configuration|reversalsFundingDivertCode|Funding Divert Code||
|financialBuAssignmentValues|Financial Bu Assignment Values|futureUse1|Future Use 1||
|irsSupplementalInformation|Irs Supplemental Information|primaryEmailIndicator|Primary Email Indicator|USE_ALTERNATE_EMAIL,USE_PRIMARY_EMAIL|
|earlyTerminationFee|Early Termination Fee|earlyTermDate|Early termination date applicable to charging an associated fee||
|miscellaneous|miscellaneous|doNotChargeVee|Do Not Charge Vee for Omnipay||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramServiceLevelCode|Visa Technology Migration Program service level code||
|financialBuAssignmentValues|Financial Bu Assignment Values|financePortfolio|Finance Portfolio||
|restrictedUseTransmatchRewards|Restricted Use Transmatch Rewards Program|status|Program Status|ACTIVE,CANCEL|
|conditionalApprovalProgram|Conditional Approval Program|offeringType|Offering Type|APP_INCONSISTENCIES,CREDIT_RISK_REVIEW,CRED_DATA_RISK_REV,CRED_RISK_REV_MPA,INACTIVE,MISSING_CREDIT_DATA,MISS_CRED_DATA_MPA,REMOVED_FRM_COND_APP|
|foreignLanguageSupport|Foreign Language Support|foreignLanguageSupport|Foreign Language Support|ARABIC,BURMESE,CAMBODIAN,CANTONESE,FARSI,FRENCH,HAITIANCREOLE,HINDI,JAPANESE,KAREN,KOREAN,MANDARIN,NEPALI,POLISH,PORTUGUESE,RUSSIAN,SOMALI,SPANISH|
|stockExchange|Stock Exchange/Ctry Name|stockExchangeName|Stock Exchange Name|BATS_EXCHANGE_INC_F2,BATS_Y_EXCHANGE_INC,C2_OPTIONS_EXCHG_INC,CHICAGO_BOARD_OPTIONS,CHICAGO_STOCK_EXCHG,EDGA_EXCHANGE_INC,EDGX_EXCHANGE_INC,INTERNATIONAL_SECURITY,N/A,NASDAQ_OMX_BX_INC,NASDAQ_OMX_PHLX_INC,NATIONAL_STOCK_EXCHG,NEW_YORK_STOCK_EXCHG,NYSE_ARCA_INC,NYSE_MKT_LLC,THE_NASDAQ_STOCK_MKT|
|irsSupplementalInformation|Irs Supplemental Information|econsentIndicator|Econsent Indicator|ECONSENT_GIVEN,ECONSENT_REVOKED,EMAIL_DELIVERY_FAILED,NO,ONLY_EMAIL_ACTIVATED,OWNERSHIP_CHANGE,PENDING_STATUS,STATUS_CHANGE,YES|
|globalCurrencySolutions|Global Currency Solutions|offeringSubType1|Offering Sub Type|EXCEPTION_RATE_MCPE_MCP,NORTH_RATES_PLUS_DCCLUS_DCC,VI/MC_RATE_MCPP|
|onBoardingDetails|OnBoarding Details|convertedAccountIndicator|Converted Account Indicator||
|indemnification|Indemnification|indemnificationPercent|Indemnification Risk Ratio Percentage||
|miscellaneous|miscellaneous|specialNationalAccountIndicator|Special National Account Indicator||
|isoServices|Iso Services|isoIdVi|Iso Id Vi||
|settlementConfig|Settlement Config|surchargeExceptionCode|Determine If A Billback Surcharge Should Be Applied||
|signatureCapture|Signature Capture|signatureCaptureIndicator|Signature Capture Indicator||
|settlementConfig|Settlement Config|settlementMethod|The settlement method assigned to for the merchant||
|miscellaneous|miscellaneous|online|Online Indicator for Omnipay Merchant||
|creditSettings|Credit Settings|creditLimitAmount|Credit Limit Amount||
|statementConfig|Statement Config|cardAlternateCity|Card Alternate City||
|miscellaneous|miscellaneous|aggregatorMerchantIndicator|Aggregator Merchant Indicator||
|transactionControl|Transaction Control|mastercardIramIndicator|Mastercard Incremental Reversal Auth Match indicator||
|settlementConfig|Settlement Config|processingTypeCode|Processing Type Code||
|earlyTerminationFee|Early Termination Fee|earlyTermFeeAmount|Early termination fee amount||
|contract|Contract|salesLead|Secondary Tax ID||
|southHdcLateCutC|South Platform Hdc Late Batch Cut C|status|Program Status|ACTIVE,CANCEL|
|compassOnNorth|Compass Podb Functionality On North|forcedDeposit|Eligible For Force Deposits|FORCE_DEPOSITS,NO_FORCE_DEPOSITS|
|internalItUse|Internal It Use - Trigger Feeds And Save Data|spomiTrigger|Sponsored Merchant Feed To Amex|NO,REPROCESS,YES|
|miscellaneous|miscellaneous|caseManagementIndicator|Case Management Indicator||
|billingConfig|Billing cofiguration|delayedBillingEffectiveDate|Delayed billing effective date||
|reversalConfig|Reversal Config|reversalTimeZoneCode|Reversal TimeZone Code||
|merchantFrontEnds|Merchant Front Ends|authNetworkSecurityCode2|Code which is being used to determine the front end network ||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdVi|Payment Facilitator Id-Marketplace Id Vi||
|fundingConfig|Funding Configuration|fundingCurrencyCode|Funding Currency Code||
|merchantFrontEnds|Merchant Front Ends|authNetworkCode1|Name Of The Network||
|electronicTicketCapture|Electronic Ticket Capture|etcCutoffTimeCode|Code indicating what time electronic ticket capture processing is terminated for the day||
|financialBuAssignmentValues|Financial Bu Assignment Values|financeAlliance|Finance Alliance||
|statementConfig|Statement Config|email|Statement email address||
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|serviceType|Service Type for Omnipay||
|msipDetails|MSIP Details|msipMailToChainIndicator|MSIP Mail To Chain Indicator||
|msipDetails|MSIP Details|msipPlasticFormatCode|MSIP Plastic Format Code||
|fundingConfig|Funding Configuration|financialAdjustmentsFundingDivertCode|Funding Divert Code||
|financialBuAssignmentValues|Financial Bu Assignment Values|globalClientDescription|Global Client Description||
|fundingConfig|Funding Configuration|fundingExcludeCode|Merchant funding exclusion code||
|settlementConfig|Settlement Config|billbackCode|Billback Code||
|settlementConfig|Settlement Config|billbackSurchargeCode|Billback Surcharge Code||
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingCategoryCode|Funding Category Code||
|fundingConfig|Funding Configuration|depositsFundingCategoryCode|Funding Category Code||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramPointofsaleCapabilityCode|Visa Technology Migration Program terminal capability code ||
|compassSpecialFeatures|Compass Front End Generated Refund Auths|amexOnlineRefund|Amex Online Refund|NO,YES|
|msipDetails|MSIP Details|msipHotCardIndicator|MSIP Hot Card Indicator||
|miscellaneous|miscellaneous|nrptAmount|Anticipated Mc/VisaÂ® net revenue percentage||
|fundingConfig|Funding Configuration|depositsFundingDivertCode|Funding Divert Code||
|irsSupplementalInformation|Irs Supplemental Information|userProvidedEconsentEmail|User Provided Econsent Email||
|transactionControl|Transaction Control|visaIramIndicator|Visa Incremental Reversal Auth Match indicator ||
|authSettings|Auth Settings|transactionCurrency|Transaction Currency ||
|omahaDebitSuspenseItemsRelease|Omaha Dd-623 Debit  Suspense Items Release - Channel Level|status|Program Status|ACTIVE,CANCEL|
|selectiveDivert|Negative Bankwire Selective Divert|status|Program Status|ACTIVE,CANCEL|
|cashAdvanceProgram|Cash Advance Gl Funding Program|status|Program Status|ACTIVE,CANCEL|
|bamsDissolutionHoldingsStatus|Bams Dissolution Holdings Status|status|Program Status|ALLOCATED,DORMANT_CANCELLED,RESERVED_ATTACHED|
|referencedDeposit|Referenced Deposit|referenceNumberType|Reference Number Type|ALPHANUMERIC,NUMERIC|
|isoServices|Iso Services|serviceProvider|Service Provider|APERIA,FD_DIRECT,MARKETPLACE,WELLS|
|fraudAndAccountTakeoverRisk|Fraud And Account Takeover Risk|status|Program Status|CAUTION_PREVIOUS_FRAUD,URGENT_MERCH_AT_RISK|
|fundingConfig|Funding Configuration|feesFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|avsControl|AVS Control|avsNoIndicator|Address verification service no indicator||
|chargebackConfig|chargeback Configuration|excessiveChargebackIndicator|Excessive Chargeback Indicator||
|fundingConfig|Funding Configuration|funding30DayOverrideIndicator|Funding 30 day override indicator||
|financialBuAssignmentValues|Financial Bu Assignment Values|profitCenterDescription|Profit Center Description||
|fundingConfig|Funding Configuration|chargebacksFundingCategoryCode|Funding Category Code||
|fundingConfig|Funding Configuration|reversalsFundingCategoryCode|Funding Category Code||
|creditSettings|Credit Settings|cumulativeSalesLimitAmount|Cumulative Sales Limit Amount||
|msipDetails|MSIP Details|msipChainRollupIndicator|MSIP Chain Rollup Indicator||
|msipDetails|MSIP Details|msipVisaFloorAmount|MSIP Visa Floor Amount||
|fundingConfig|Funding Configuration|fundingRunCode|Merchant Funding Run||
|statementConfig|Statement Config|icplusStatementFormatCode|Code determining the interchange fee information the System prints on the merchant statement||
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsFundingDivertCode|Funding Divert Code||
|promotion|Promotion Tracking|promotionName2|Promotion Name Two||
|transactionControl|Transaction Control|visaRelationshipIndicator|Visa relationship particpant indicator||
|indemnification|Indemnification|indemnificationIndicator|Indemnification Indicator||
|merchantMunicipality|Merchant Municipality|municipalityTaxInd|Municipality Tax Indicator||
|fundingConfig|Funding Configuration|fundingAchDelayDays|Retention period for deposits and daily discount before releasing them for ACH processing||
|fundingConfig|Funding Configuration|chargebacksFundingDivertCode|Funding Divert Code||
|contract|Contract|postingMethod|The posting method assigned to the merchant||
|transactionControl|Transaction Control|globalGatewayE4EffectiveDate|Payeezy gateway effective date||
|sameDaySettlement|Same Day Settlement|status|Program Status|ACTIVE,CANCEL|
|panMasking|Pan Masking|offeringType|Offering Type|APPLY_PAN_MASKING|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|offeringType|Offering Type|GLOBAL,LEGACY,MARKETPLACE_CLIENT|
|rateLock|Rate Lock|rateLockLength|Number Of Years The Rate Lock Is In Place|ONE_YEAR,THREE_YEARS,TWO_YEARS|
|modelAfterMerchant|Model After Merchant For Boarding Usage|offeringType|Offering Type|STANDARD_OFFERING|
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteCreditLimitAmount|Merchant Lite Credit Limit Amount||
|fundingConfig|Funding Configuration|financialAdjustmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|isoServices|Iso Services|isoIdDscv|Iso Id Discover||
|fundingConfig|Funding Configuration|achSuspenseReleaseIndicator|ACH suspense release indicator||
|miscellaneous|miscellaneous|cashManagementIndicator|Cash Management Indicator||
|inHouseAuthConfig|InHouse Auth Configuration|inHouseBankCode|InHouse Bank Code||
|earlyTerminationFee|Early Termination Fee|earlyTermFeeIndicator|Early termination fee indicator||
|financialBuAssignmentValues|Financial Bu Assignment Values|fmgMarkerBank|Fmg Marker Bank||
|onBoardingDetails|OnBoarding Details|boardingTypeCode|Boarding Type Code||
|miscellaneous|miscellaneous|oilTradeClassCode|Class of Trade code for specific client usage||
|miscellaneous|miscellaneous|faxIndicator|Fax Indicator||
|msipDetails|MSIP Details|msipMailToBusinessIndicator|MSIP Mail To Business Indicator||
|msipDetails|MSIP Details|msipCategoryLevelCode|MSIP Category Level Code||
|promotion|Promotion Tracking|promotionName5|Promotion Name Five||
|promotion|Promotion Tracking|promotionName1|Promotion Name One||
|transactionControl|Transaction Control|fraudFlexIndicator|Fraud Flex Detect Indicator||
|compassOnNorth|Compass Podb Functionality On North|status|Program Status|ACTIVE_COMPASS_ON_NORTH,CANCEL_COMPASS_ON_NORTH|
|merchantPortfolioType|Merchant Portfolio Type|byTransactionCount|Transaction Count Portfolio Size|MIDMARKET,NATIONAL,SMB|
|boardingAdditionalInfo|Merchant Boarding Additional Information|homeBasedBusiness|Defines if the merchants business location is the same as his home location|NO,YES|
|billingConfig|Billing cofiguration|membershipFeeDate|Date that membership fees will be charged ||
|crossBorderAcquiring|Cross Border Acquiring|viSingleMerchantId|Visa Single Merchant Id||
|fundingConfig|Funding Configuration|agentBankSplitIndicator|Indicates if Bank Client is considered an agent relationship to FDCS||
|fundingConfig|Funding Configuration|bankwireBnfText|Bankwire beneficiary BNF Text||
|boardingAdditionalInfo|Merchant Boarding Additional Information|descriptionOfGoods|Description of goods and services sold by the merchant||
|avsControl|AVS Control|avsWholeZipIndicator|Address verification service whole zip indicator||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|subMerchantId|Sub Merchant ID for Omnipay||
|msipDetails|MSIP Details|msipMailToOutletIndicator|MSIP Mail To Outlet Indicator||
|settlementConfig|Settlement Config|dcc|DCC Merchant for Omnipay||
|merchantLocation|Merchant Location Information|state|Merchant State||
|msipDetails|MSIP Details|msipMaestroFraudProneIndicator|MSIP Maestro Fraud Prone Indicator||
|fundingConfig|Funding Configuration|fundingRollupCode|Indicates how the funding transactions will be combined on DDA statement||
|fundingConfig|Funding Configuration|fundingDailyOverrideDate|Funding Daily Override Date||
|financialBuAssignmentValues|Financial Bu Assignment Values|profitCenterId|Profit Center Id||
|irsSupplementalInformation|Irs Supplemental Information|requestGuid|Request Guid||
|fundingConfig|Funding Configuration|chargebacksBankSequenceNumber|Funding Bank Sequence||
|fundingConfig|Funding Configuration|fundingRppPercent|Revolving payment plan percent||
|msipDetails|MSIP Details|msipPlasticRegenerateIndicator|MSIP Plastic Regenerate Indicator||
|miscellaneous|miscellaneous|bankingCategoryCode|Banking Category Code||
|pricingMthdDisclosures|Pricing Method Disclosures|offeringType|Offering Type|ALL_OTHER,FLAT_RATE_NO_BB,SIMPLIFIED,UNKNOWN|
|merchantPortfolioType|Merchant Portfolio Type|offeringType|Offering Type|MIDMARKET,NATIONAL,SMB|
|compassSpecialFeatures|Compass Front End Generated Refund Auths|compassFrontendGenreFauth|Compass frontend Gen Ref Auth|NO,YES|
|merchantPricingStructure|Merchant Pricing Structure|offeringType|Offering Type|STANDARD_OFFERING|
|miscellaneous|miscellaneous|rejectNotifyCode|Reject Notification Code||
|miscellaneous|miscellaneous|emailtypecode|Type of Email Address||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdAmex|Payment Facilitator Id Amex||
|avsControl|AVS Control|avsAddressIndicator|Address verification service address indicator||
|avsControl|AVS Control|avsExactIndicator|Address verification service exact indicator||
|miscReporting|MISC|enhancedReportingIndicator|Enhanced Reporting Indicator||
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|conversionInformation|Conversion  Account Source System Data|contractDate|Contract Date||
|fundingConfig|Funding Configuration|depositsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|pathwardBankwire|Pathward Bankwire|futureUse2|Future Use 2||
|statementConfig|Statement Config|statementFaxNumber|Statement fax number||
|miscellaneous|miscellaneous|leaseCompanyCode|Lease Company Code||
|statementConfig|Statement Config|cardAlternateName|Card Alternate Name||
|chargebackConfig|chargeback Configuration|holdChargebackIndicator|Hold Chargebacks Indicator ||
|fundingConfig|Funding Configuration|discountsFundingDivertCode|Funding Divert Code||
|transactionControl|Transaction Control|commercialCardInterchangeServiceCode|Indicates the level of participation in the mastercard or visa commercial card interchange service||
|miscellaneous|miscellaneous|imprintersCount|Imprinter Quantity Bill Number||
|fundingConfig|Funding Configuration|settleTimeframeCode|Settlement Timeframe Code||
|fundingConfig|Funding Configuration|bankwireBbkText|Bankwire beneficiary BBK Text||
|fundingConfig|Funding Configuration|feesBankSequenceNumber|Funding Bank Sequence||
|miscellaneous|miscellaneous|loyaltyProcessingCode|Loyalty Processing Code||
|pathwardEmergingMarkets|Pathward Emerging Markets|offeringType|Offering Type|AIRLINES,CBD_CAT_1,CBD_CAT_2,CRUISE_LINES,DCC,DFS,LEGAL_GAMBLING,MSB_CRYPTO_NFT,MULTIPLE,NON_FI_LENDER,ONLINE_FIREARMS,PAYPAL_EXCEPTION,SINGLE_MID_MRKTPLACE,SINGLE_MID_PFAC,STAGED_DIGITAL_WALLET,TBD|
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pspIndicator|Payment Service Provider Indicator|FUND_PF,FUND_SUB,HYBRID_SERVICE,SELF_SERVICE|
|pricingMthdDisclosures|Pricing Method Disclosures|pricingSchedule|Pricing Schedule|SCHEDULE_010,SCHEDULE_028,SCHEDULE_101,SCHEDULE_102,SCHEDULE_103,SCHEDULE_104,SCHEDULE_105,SCHEDULE_108,SCHEDULE_111,SCHEDULE_112,SCHEDULE_113,SCHEDULE_120,SCHEDULE_123,SCHEDULE_124,SCHEDULE_125,SCHEDULE_127,SCHEDULE_133,SCHEDULE_135,SCHEDULE_136,SCHEDULE_138,SCHEDULE_150,SCHEDULE_2T,SCHEDULE_3T,SCHEDULE_IC,UNKNOWN|
|merchantFrontEnds|Merchant Front Ends|authNetworkCode2|Name Of The Secondary Network||
|miscellaneous|miscellaneous|descriptorEntitledIndicator|Descriptor Entitled Indicator||
|avsControl|AVS Control|avsRetryIndicator|Address verification service retry indicator||
|statementConfig|Statement Config|statementFaxIndicator|Statement Fax Indicator||
|fundingConfig|Funding Configuration|discountsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|pathwardBankwire|Pathward Bankwire|beneficiaryZipCode|Beneficiary Zip Code||
|msipDetails|MSIP Details|msipTerminalCount|MSIP Terminal Count||
|msipDetails|MSIP Details|msipRecourseCode|MSIP Recourse Code||
|fundingConfig|Funding Configuration|nonBankcardAdjustmentsBankSequenceNumber|Funding Bank Sequence||
|financialBuAssignmentValues|Financial Bu Assignment Values|companyCode|Company Code||
|financialBuAssignmentValues|Financial Bu Assignment Values|globalClientId|Global Client Id||
|msipDetails|MSIP Details|msipContactName|MSIP Contact Name||
|msipDetails|MSIP Details|msipMailToCorporationIndicator|MSIP Mail To Corporation Indicator||
|chargebackConfig|chargeback Configuration|mediaFaxNumber|Media Fax Number||
|statementConfig|Statement Config|statementDeliveryCode|Statement delivery method||
|transactionControl|Transaction Control|visaMerchantVerificationValue|Visa merchant verification value||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramRequestCode|Visa Technology Migration Program request code||
|pathwardBankwire|Pathward Bankwire|beneficiaryStateCode|Beneficiary State Code||
|firstHawaiianBank|First Hawaiian Bank|fhbNaicsNumber|Fhb Naics Number N||
|transactionControl|Transaction Control|visaTechnologyMigrationProgramEntryMode|Visa Technology Migration Program terminal entry mode code||
|cashAdvanceProgram|Cash Advance Gl Funding Program|offeringType|Offering Type|STANDARD_OFFERING|
|merchantLiteConfig|Merchant Lite Configuration|merchantLiteSalesLimitAmount|Merchant Lite Sales Limit Amount||
|miscellaneous|miscellaneous|revenueBookedDate|Revenue Booked Date||
|billingConfig|Billing cofiguration|managementFeeDate|Date that management fee will be charged||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|pfIdUpi|Payment Facilitator Id Upi||
|miscellaneous|miscellaneous|cmsServiceCodes|CMS Service Codes||
|fundingConfig|Funding Configuration|fundingNotifyPhoneNumber|Funding notification phone number||
|signatureCapture|Signature Capture|signatureCaptureRejectsIndicator|Signature Capture Rejects Indicator||
|fundingConfig|Funding Configuration|reversalsFundingRollupCode|Indicates how the transactions will be combined on DDA statement||
|msipDetails|MSIP Details|msipInternationalDialNumber|MSIP International Dial Number||
|creditSettings|Credit Settings|cumulativeCreditLimitAmount|Cumulative Credit Limit Amount||
|additionalTaxInfo|Additional Tax Information|vatTaxCode|VAT Tax Code||
|additionalTaxInfo|Additional Tax Information|secondaryTaxId|Secondary Tax ID||
|statementConfig|Statement Config|cardAlternateStateCode|Card Alternate State Code||
|transactionControl|Transaction Control|mastercardTieredMerchantId|Mastercard tiered merchant ID||
|miscellaneous|miscellaneous|arpCode|ARP Code||
|onBoardingDetails|OnBoarding Details|linkForwardMerchantId|Link Forward Merchant Id||
|avsControl|AVS Control|avsServiceIndicator|Address verification service indicator||
|prop51Conversion|Prop 51 Conversion|propMerchantId|Original Prop Merchant Id||
|freeProcessing|Free Processing|status|Program Status|ACTIVE,CANCEL,COMPLETED|
|bamsDissolutionHoldingsStatus|Bams Dissolution Holdings Status|offeringType|Offering Type|BANK_OF_AMERICA,FISERV,OTHER_ASSIGNED|
|channelLevelDiscoverPromotionalPvi|Discover Promotional Program Verification Identifier - Channel Level|offeringType|Offering Type|CLIENT_DISCOVER_PRO,FD_DISCOVER_PROMO|
|highRiskMonitoring|High Risk Monitoring|status|Program Status|COMPLETE_REGISTER,DEREGISTERED,NOT_REQUIRED,OTHER,PENDING_REGISTER|
|acknowledgementFilePreference|Acknowledgement File Preference|ackFilePreference|Acknowledgement File Preference|DISABLE,MASK,NORMAL|
|crossBorderAcquiring|Cross Border Acquiring|viSmiActivationInd|Visa Smi Activation Indicator|NO,YES|
|pathwardBankwire|Pathward Bankwire|beneficiaryStreetAddress|Beneficiary Street Address(No Po Box)||
|reversalConfig|Reversal Config|reversalDaylightSavingsIndicator|Reversal Daylight Savings Indicator||
|miscellaneous|miscellaneous|volumeTierIndicator|Volume Tier Indicator||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|parentId|Parent ID||
|isoServices|Iso Services|isoIdAmex|Iso Id Amex||
|contract|Contract|serviceContractIndex|Service contract defines the processing rules for a merchant||
|keyReferenceNumber|Key Reference Number|tbd|Tbd||
|chargebackConfig|chargeback Configuration|disputeDispositionCode|Indicates the disposition option for chargeback disputes||
|financialBuAssignmentValues|Financial Bu Assignment Values|financeParent|Finance Parent||
|pathwardBankwire|Pathward Bankwire|futureUse1|Future Use 1||
|highRiskMonitoring|High Risk Monitoring|contractDate|Contract Date||
|contractExpirationDate|Contract Expiration Date Notifications/Flag|gcid|Global Client Id||
|msipDetails|MSIP Details|msipMailToAgentIndicator|MSIP Mail To Agent Indicator||
|miscellaneous|miscellaneous|branchDepositorIndicator|Branch Depositor Indicator||
|msipDetails|MSIP Details|msipChainRollupDate|MSIP Chain Rollup Date||
|chargebackConfig|chargeback Configuration|mediaRetrievalCode|Code determining how the bank retrieval and chargeback retrieval advice or requests are processed||
|billingConfig|Billing cofiguration|zeroInterchangeIndicator|Zero interchange indicator reserved for international banks only||
|trustKeeper|Trust Keeper|trustkeeperIndicator|Trustkeeper Indicator||
|retrievalConfig|Retrievals Config|email|email address||
|msipDetails|MSIP Details|msipMaestroCashbackIndicator|MSIP Maestro Cashback Indicator||
|chargebackConfig|chargeback Configuration|chargebackAddressCode|Indicates where the chargeback advice is directed||
|fundingConfig|Funding Configuration|fundingNotifyContactName|Funding notification contact name||
|paymentFacilitator|Payment Service Provider/Payment Facilitator|participantType|Participant Type|A_PARTICIPANT,B_PARTICIPANT,C_PARTICIPANT|
|compassOnNorth|Compass Podb Functionality On North|reauthorizations|Eligible For Re-Authorizations|EXTENDED_AUTH_NO_REAUT,NO_REAUTHORIZATIONS,REAUTHORIZATIONS|
|fdggMigration|First Data Global Gateway Migration|status|Program Status|MIGRATED,NOT_MIGRATED|
|fdggMigration|First Data Global Gateway Migration|offeringType|Offering Type|STANDARD_OFFERING|
|indemnification|Indemnification|riskOwnerCode|Risk Owner Code||
|settlementConfig|Settlement Config|billbackRoundingIndicator|Bill Back Rounding Indicator||
|inHouseAuthConfig|InHouse Auth Configuration|inHouseNonMerchantCode|InHouse NonMerchant Code||
|electronicTicketCapture|Electronic Ticket Capture|etcBypassEditsIndicator|TellS the edit programs if the Merchant wishes to let all his ETC transactions process||
|fundingConfig|Funding Configuration|bankwireObiText|Bankwire beneficiary OBI Text||
|trustKeeper|Trust Keeper|trustkeeperDate|Trustkeeper Date||
|fundingConfig|Funding Configuration|interchangeAssessmentsFundingCategoryCode|Funding Category Code||
|fundingConfig|Funding Configuration|depositAdjustmentsBankSequenceNumber|Funding Bank Sequence||
|miscellaneous|miscellaneous|branchLongNumber|Branch Long Number||
|merchantLocation|Merchant Location Information|country|Merchant Country||
|msipDetails|MSIP Details|msipMaestroFloorAmount|MSIP Maestro Floor Amount||
|miscellaneous|miscellaneous|volumeTierInterchangeFeeIndicator|Volume Tier Interchange Fee Indicator||
|fundingConfig|Funding Configuration|fundingRppChangeDate|Merchant funding revolving payment plan change date||
|fundingConfig|Funding Configuration|ptsLimitsIndicator|PTS Limits Indicator||
|chargebackConfig|chargeback Configuration|chargebackPrenoteIndicator|Indicates if the merchants recieves pre-notification before receiving a charge back||
|fundingConfig|Funding Configuration|financialAdjustmentsBankSequenceNumber|Funding Bank Sequence||
|billingConfig|Billing cofiguration|billSuppliesIndicator|Bill Supplies Indicator||
|recurringPayment|Recurring Payment|recurringPaymentsIndicator|Hosted Recurring Payments Indicator||
|miscellaneous|miscellaneous|SECURITY_EMAIL|Security contact email||
|promotion|Promotion Tracking|promotionName3|Promotion Name Three||
|fundingConfig|Funding Configuration|fundingRppDelayDays|Revolving payment plan delay days||



<!-- type: tab-end -->  

