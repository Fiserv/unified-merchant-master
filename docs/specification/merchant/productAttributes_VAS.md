# Product Attributes - VAS

## List of Domains

### cashAdvance

---

tags: [cashAdvance]Cash Advance Activation Date

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |

---

|   Product Code   | Attribute         | Description                   | UMM Value                  |
|:---------------------|:---------------------|:--------------------------|:----------------------------------|
| VASCASHADV   | activeDate   |   Cash Advance Activation Date   |      |   
|       | advanceAmount   |   Cash Advance Amount   |      |   
|       | bookingDate   |   Cash advance Booking Date   |      |   
|       | branchCode   |   Cash Advance Branch Code   |      |   
|       | businessSegment   |   Cash Advance Business Segment   |      |   
|       | cashAdvanceBankSequenceNumber   |   Cash Advance Bank Sequence Number added to Merchant Bank Account   |      |   
|       | contractTerm   |   Cash Advance Contract Term   |      |   
|       | dailyWithholdPercentage   |   Cash Advance Daily Withhold Percentage   |      |   
|       | estPaybackPeriod   |   Cash Advance EST Payback Period   |      |   
|       | finalPaymentDate   |   Cash Advance Final Payment Date   |      |   
|       | firstPaymentDate   |   Cash Advance First Payment Date   |      |   
|       | fundingDate   |   Cash Advance Funding Date   |      |   
|       | grossIncome   |   Cash Advance Gross Income   |      |   
|       | invDueDate   |   Cash Advance Invoice Due Date   |      |   
|       | lastPaymentDate   |   Cash Advance Last Payment Date   |      |   
|       | legalStatus   |   Lease Legal Status   |   PIF_MERCH_KEEP_EQUIP   |   
|                       |                  |                       |   RECOURSE_PIF   |   
|                       |                  |                       |   WRITEOFF_REVERSAL   |   
|                       |                  |                       |   END_OF_LEASE_W_RTN_EQUIP   |   
|                       |                  |                       |   WRITEOFF_DEAD   |   
|                       |                  |                       |   PIF_MERCH_RETURN_EQUIP   |   
|                       |                  |                       |   WRITEOFF   |   
|                       |                  |                       |   CANCELLED   |   
|                       |                  |                       |   SIF_MERCH_KEEP_EQUIP   |   
|                       |                  |                       |   BUYBACK   |   
|                       |                  |                       |   EQUIP_RETURNED_TO_TASQ   |   
|                       |                  |                       |   ATTORNEY_NEGOTIATION   |   
|                       |                  |                       |   SIF_MERCH_RETURN_EQUIP   |   
|                       |                  |                       |   UPGRADE_BUYOUT   |   
|       | payBackAmount   |   Cash Advance Pay Back Amount   |      |   
|       | priorCashAdvanceId   |   Prior Cash Advance ID   |      |   
|       | receivedAmount   |   Cash Advance Received Amount   |      |   
|       | relationshipCode   |   Cash Advance Relationship Code   |      |   
|       | remainingAmount   |   Cash Advance Remaining Amount   |      |   
|       | terminationDate   |   Cash Advance Termination Date   |      |   

<!-- type: tab-end -->


### lease

---

tags: [lease]

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |

---

|   Product Code   | Attribute         | Description                   | UMM Value                  |
|:---------------------|:---------------------|:--------------------------|:----------------------------------|
| VASLEASE   | leaseActivationDate   |   The activation date of the contract. Entering this date activates the contract. InfoLease uses this date along with the Contract Term and the Payments in Arrears Code to determine the termination date of the contract.   |      |   
|       | leaseAdditionalMid   |   This will be the Mainframe MID for ISOs that have a 15 digit MID that contains a zero added to the infolease record for cash advance   |      |   
|       | leaseAmortizableResidualAmount   |   The calculation for amortizable residual is as follows.~ ~ Gross Residual~ - Residual Writedown ~ - Discount Residual~ - Present Value Amount~ = Amount of Residual Amortized~ ~ This field usually projects a conservative amount for residual. The Managers Residual field generally projects a more optimistic figure.   |      |   
|       | leaseApproverSignatoryName   |   The name of the person who signs the contract. This field defaults to the name entered in the Contact Name field.   |      |   
|       | leaseBankSequenceNumber   |   Lease Bank Sequence Number added to Merchant Bank Account   |      |   
|       | leaseBillingCycle   |   Billing Cycle of a lease   |   SEMI_ANNUAL   |   
|                       |                  |                       |   QUARTERLY   |   
|                       |                  |                       |   MONTHLY   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   ANNUAL   |   
|       | leaseBranchCode   |   This 5-character code indicates the branch associated with the contract. You can use the branch as a sort sequence when requesting reports.   |      |   
|       | leaseBusinessSegment   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.   |      |   
|       | leaseBusinessSegmentCode   |      |      |   
|       | leaseBuyoutQuoteCode   |   This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.   |   NO   |   
|                       |                  |                       |   YES   |   
|       | leaseCollateralCode   |   This code identifies additional collateral (other than the actual equipment) assigned to a contract.   |      |   
|       | leaseCompanyName   |   UATB.LEASING.COMPANY   |      |   
|       | leaseContractBalanceAmount   |   Contract balance remaining after all payments received are applied to the gross contract. This amount is system-calculated.   |      |   
|       | leaseContractStatus   |   The status of the contract.    |   YES   |   
|                       |                  |                       |   NO   |   
|       | leaseContractStatusDate   |   The date the status was assigned to the contract.   |      |   
|       | leaseContractStatusDesc   |   Contract Status Description   |      |   
|       | leaseContractTerm   |   The term of the contract in months. If a commencement date was entered, this field is mandatory.The maximum term is 400 months.   |      |   
|       | leaseContractTotalReceivedAmount   |   The total contract payment amount received from the beginning of the contract. This is a system-calculated amount.~ ~ Note: If a partial disposition has taken place, this represents the payments on the active portion of the contract only.   |      |   
|       | leaseCustomerAccountReceivableName   |   The accounts receivable name. This name prints on the customers invoice.   |      |   
|       | leaseCustomerArAddressAttentionName   |   Information entered in this field prints on the invoice, i.e., the name of the person to whom you are mailing the invoice.   |      |   
|       | leaseCustomerArAddressCityName   |   The city for the accounts receivable address.   |      |   
|       | leaseCustomerArAddressCountryCode   |   The country code for the accounts receivable address.   |      |   
|       | leaseCustomerArAddressLine1   |   The first line of the accounts receivable address. This address prints on the customers invoice.   |      |   
|       | leaseCustomerArAddressLine2   |   The second line of the accounts receivable address. This address prints on the customers invoice.   |      |   
|       | leaseCustomerArAddressLine3   |   The third line of the accounts receivable address. This address prints on the customers invoice.   |      |   
|       | leaseCustomerArAddressPostalCode   |   The zip code of the city for the accounts receivable address.   |      |   
|       | leaseCustomerArAddressStateName   |   The state for accounts receivable address.   |      |   
|       | leaseCustomerCreditScore   |   A user-defined score given by the leasing company extending credit to the lessee. A credit score is based on certain factors, such as age, marital status, length of employment, etc. Each of these factors is assigned a certain point value with the total being the credit score. Based on this score, the lessee is approved for the credit.   |      |   
|       | leaseCustomerDoingBusinessName   |   The Customerdoing business name   |      |   
|       | leaseCustomerFedSsnId   |   The appropriate identification number.  The ability to modify this field depends on your security settings.   |      |   
|       | leaseCustomerName   |   The customer name. Use the customer name to create alphabetical listings and locate a name when using Soundex.   |      |   
|       | leaseCustomerShortName   |   The Short Name is another name to use when referring to the customer. The Short Name cannot be the same as the Customer Name. This field defaults to the Short Name previously entered for the customer.   |      |   
|       | leaseDelinquentStatusCode   |   The delinquent status of the contract. This is a system-calculated field.    |   PAST_DUE_151_180_DAYS   |   
|                       |                  |                       |   PAST_DUE_91_120_DAYS   |   
|                       |                  |                       |   PAST_DUE_61_90_DAYS   |   
|                       |                  |                       |   PAST_DUE_31_60_DAYS   |   
|                       |                  |                       |   PAST_DUE_01_30_DAYS   |   
|                       |                  |                       |   NOT_DELINQUENT   |   
|                       |                  |                       |   PAST_DUE_121_150_DAYS   |   
|                       |                  |                       |   PAST_DUE_181_DAYS_AND_MORE   |   
|       | leaseDispositionDate   |   The last date any disposition or inventory occurred on the contract. InfoLease updates this field at the time of a disposition.   |      |   
|       | leaseEarlyBuyoutAmount   |   You can enter buyout amounts for the contract in this field. You must first fill in the Date field. The information in this field does not default to the Buyout Quotes module.   |      |   
|       | leaseEarlyBuyoutDate   |   You can enter the buyout date for the contract in this field. Entering information here does not default to the Buyout Quotes module.   |      |   
|       | leaseFacilityScore   |   This score represents the credit score of the deal, not the credit score of the customer.   |      |   
|       | leaseFdmsDecisionDate   |   UATB.DATE.FDMS.DECISION   |      |   
|       | leaseFdmsDecisionInd   |   UATB.FDMS.DECISION   |      |   
|       | leaseFinalPaymentDate   |   This field identifies the date the last contract payment is due. This is a system-calculated field using the contract term, the number of advance payments, the number of payments in arrears, the commencement date, and the billing cycle.   |      |   
|       | leaseFirstPaymentAmount   |   If the first payment is different from the regular scheduled payments, enter the amount here; otherwise, InfoLease defaults the regular contract payment. If no payment is due in the first month, enter zero.   |      |   
|       | leaseFirstPaymentDate   |   The first payment date. This is a required field. InfoLease calculates the default date based on the commencement date, billing cycle, variable payment schedule, and the payments in arrears code.   |      |   
|       | leaseFloatingRateIndicator   |   This yes/no field indicates whether this is a floating rate contract.   |   NO   |   
|                       |                  |                       |   YES   |   
|       | leaseFollowUpDays   |   The number of days after the payment due date that you need to contact the customer. InfoLease uses the number of follow-up days to generate follow-up lists for payment collections. This field is used with the Customer Service Module.   |      |   
|       | leaseGeneralLedgerBookingDate   |   Lease General Booking Date   |      |   
|       | leaseGrossAssetAmount   |   The total equipment cost for all assets (not including disposed assets) on the contract.   |      |   
|       | leaseGrossFinanceAmount   |   The total amount of finance or interest income (difference between the gross contract amount and the equipment cost). If a commencement date was entered, this field is mandatory.   |      |   
|       | leaseGrossPaymentAmount   |   The total amount of payments due on the contract. If a commencement date was entered, this field is mandatory.   |      |   
|       | leaseIncomeStartDate   |   The date the income on the contract begins to amortize. This date affects how InfoLease calculates the IRR. This date defaults to the commencement date of the contract; however, in cases where interest free periods exist, you can modify this date.   |      |   
|       | leaseInterimRentAmount   |   The amount of interest payments received prior to the commencement of the contract.   |      |   
|       | leaseInvoiceCode   |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.   |   NO_MORE_INVOICING   |   
|                       |                  |                       |   MANUAL_INVOICING   |   
|                       |                  |                       |   INVOICE_SUPRESSED   |   
|                       |                  |                       |   SEPARATED_BY_NOTE_DATE   |   
|                       |                  |                       |   INVOICE_BY_CONTRACT   |   
|                       |                  |                       |   INVOICE_BY_CUSTOMER   |   
|                       |                  |                       |   RENTALS_SEPARATED   |   
|                       |                  |                       |   CONTRACT_SEPARATED_INDIVIDUAL_INVOICES   |   
|       | leaseInvoiceDueDate   |   The day of the month the payment is due. If you do not enter the invoicing due day, the field defaults to the due day on the Customer Default Data Screen.    |      |   
|       | leaseLastPaymentDate   |   The date you received the last payment.   |      |   
|       | leaseLegalStatus   |   Lease Legal Status   |   PIF_MERCH_RETURN_EQUIP   |   
|                       |                  |                       |   WRITEOFF   |   
|                       |                  |                       |   CANCELLED   |   
|                       |                  |                       |   SIF_MERCH_KEEP_EQUIP   |   
|                       |                  |                       |   BUYBACK   |   
|                       |                  |                       |   EQUIP_RETURNED_TO_TASQ   |   
|                       |                  |                       |   PIF_MERCH_KEEP_EQUIP   |   
|                       |                  |                       |   ATTORNEY_NEGOTIATION   |   
|                       |                  |                       |   RECOURSE_PIF   |   
|                       |                  |                       |   UPGRADE_BUYOUT   |   
|                       |                  |                       |   WRITEOFF_REVERSAL   |   
|                       |                  |                       |   SIF_MERCH_RETURN_EQUIP   |   
|                       |                  |                       |   WRITEOFF_DEAD   |   
|                       |                  |                       |   END_OF_LEASE_W_RTN_EQUIP   |   
|       | leaseManagerResidualAmount   |   An alternate residual amount that you can select when calculating a buyout quote. Managers residual does not accrue income.This field usually projects an optimistic figure for residual. The Amortizable Residual field usually projects a more conservative figure.   |      |   
|       | leaseMerchantId   |   Lease Merchant ID   |      |   
|       | leaseMonthlyPaymentAmount   |   The amount of the contract payment. If this is a variable payment contract, do not enter a contract payment here.   |      |   
|       | leaseNetFinanceAmount   |   Net finance is the difference between the gross finance income and the setup income. If Prov Loss Fr Fin = (Y)es, InfoLease also subtracts Provision for Loss from net finance. This amount is system-calculated and you cannot modify it.    |      |   
|       | leaseNetInvestmentAmount   |   The net investment of the contract. The net investment is the loss the lessor would incur if the lessee stopped payment today.   |      |   
|       | leaseNextAgingDate   |   The next date InfoLease will age the contract. You cannot modify this field.    |      |   
|       | leaseNextChargeDate   |   The next date InfoLease will assess the appropriate late charges during the aging process. You cannot modify this field. InfoLease updates this field whenever you run aging.   |      |   
|       | leaseNumberOfAsset   |   The number of active assets associated with the contract.   |      |   
|       | leasePaymentInvoicedCount   |   The number of payments billed to the customer.   |      |   
|       | leasePaymentOptionCode   |   This field depicts different options of Lease Payment.   |   TAPE   |   
|                       |                  |                       |   NORMAL_PAY   |   
|                       |                  |                       |   ASSUMED_PAY   |   
|                       |                  |                       |   POST_DATED_CHEQUE   |   
|                       |                  |                       |   COUPON   |   
|                       |                  |                       |   UNDISCOUNTED_PAYMENT   |   
|                       |                  |                       |   DISCOUNTED_PAYMENT   |   
|       | leasePaymentPaidToDate   |   Contract payments are paid up to, but not including, this date. This field is based on the due dates of unpaid open items or the next due date (invoicing date plus lead invoicing days) if there are no unpaid open items.    |      |   
|       | leasePaymentUpfrontAmount   |   The number of beginning payments paid in advance by the customer at contract commencement. Without the Customer Service Module, this field is informational only.   |      |   
|       | leasePendingCode   |   This field identifies outstanding information, e.g., paperwork, correspondence, you expect to receive for the contract.   |      |   
|       | leasePlatformCode   |   PLATFORM   |      |   
|       | leasePreviousContractNumber   |   Lease Previous Contract Number   |      |   
|       | leasePreviousDelinquentStatusCode   |   The previous delinquent status of the contract. If the Delinquent Status Code changes, the previous status is moved to the Previous Delinquent Status field.   |      |   
|       | leaseProgramTypeCode   |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.   |   VAPP   |   
|                       |                  |                       |   CROSS_SALES_LARGE_LEASE   |   
|                       |                  |                       |   MCA_FDIS_ISO   |   
|                       |                  |                       |   IMS_PORTFOLIO_PURCHASE   |   
|                       |                  |                       |   CASH_ADVANCE   |   
|                       |                  |                       |   ATLANTA_TELESALES   |   
|                       |                  |                       |   RSA_RECOURSE_PROJECT   |   
|                       |                  |                       |   CROSS_SALES   |   
|                       |                  |                       |   DBG_RECOURSE   |   
|                       |                  |                       |   MCA_REGIONAL_SALES   |   
|                       |                  |                       |   SAMS_NY_TELESALES   |   
|                       |                  |                       |   PAPERLESS_LEASE   |   
|                       |                  |                       |   MCA_FDIS_AGENT   |   
|                       |                  |                       |   RSA_SEVEN_DAY_NO_PPWK   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   MCA_TELESALES   |   
|                       |                  |                       |   RSA_SEVEN_DAY   |   
|                       |                  |                       |   LARGE_LEASE   |   
|       | leaseProvisionForLossAmount   |   The amount set aside to record in the first month for bad debt expense. Enter an amount or default to the system-calculated amount. Gross Contract x Provision for Loss Percentage (lessor file) = Provision for Loss Enter the provision for loss percentage in the Prov for Loss field accessed via the Lessor Parameter Maintenance Screen and the Lessor Default Fields Screen.   |      |   
|       | leaseRelationCode   |   Lease Relationship code   |      |   
|       | leaseRenewalStatusCode   |   Lease Renewal status code   |      |   
|       | leaseResidualAmount   |   This field displays once information is entered in residual amount at the asset level. This field cannot be entered or maintained at the contract level. However, a residual change at the asset level affects the gross residual.   |      |   
|       | leaseSaleLeasebackInd   |   Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.   |   NO   |   
|                       |                  |                       |   YES   |   
|       | leaseSecurityDepositAmount   |   This window displays the Security Deposit and the Down Payment fields.The Security Deposit field represents the amount received from the lessee. The Down Payment field represents the amount received from the lessee.    |      |   
|       | leaseTaxExemptIndicator   |   This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.   |   NO   |   
|                       |                  |                       |   YES   |   
|       | leaseTermDate   |   The date the contract expires.This date is system-generated and you cannot enter or maintain it at the contract level. However, a new date is generated if the Commencement Date, Contract Term, or the Payments In Arrears code is changed.   |      |   
|       | leaseTotalRentalPaymentNumber   |   Total number of rental payments made to date.   |      |   
|       | leaseTypeCode   |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.   |   RENTAL_LEASE   |   
|                       |                  |                       |   REVOLVING_ACCOUNT   |   
|                       |                  |                       |   TRUE_LEASE   |   
|                       |                  |                       |   LEVERAGED_LEASE   |   
|                       |                  |                       |   LEASE_PURCHASE   |   
|                       |                  |                       |   TERM_LOAN   |   
|                       |                  |                       |   OPERATING_LEASE   |   
|                       |                  |                       |   CONDITIONAL_SALE   |   
|       | leaseVariablePaymentAmount   |   Variable Payment Amount of the lease   |      |   
|       | leaseVariablePaymentIndicator   |   This yes/no field indicates whether this contract has a variable payment schedule.    |   YES   |   
|                       |                  |                       |   NO   |   
|       | leaseWriteOffAmount   |   The income used to offset the initial expense associated with a new lease. The amount is calculated by multiplying the setup income percentage on the Lessor Parameter File by the gross finance income.   |      |   


<!-- type: tab-end -->


### serviceAttr

---

tags: [serviceAttr]

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |

---

|   Product Code   | Attribute         | Description                   | UMM Value                  |
|:---------------------|:---------------------|:--------------------------|:----------------------------------|
| VASTRNSARM   | encryptExceptionKeyId   |   Encryption exception key ID   |      |   
|       | encryptServiceLevelCode   |   Encryption security level code   |   NONE   |   
|                       |                  |                       |   ENCRP_ONLY   |   
|                       |                  |                       |   TOKEN_ONLY   |   
|                       |                  |                       |   BOTH   |   
|       | encryptTokenCode   |   Encryption token type code   |      |   
|       | encryptTokenHierarchyCode   |   Encryption multipay token hierarchy level code   |   AGENT   |   
|                       |                  |                       |   CORP   |   
|                       |                  |                       |   BUSINESS   |   
|                       |                  |                       |   OUTLET   |   
|                       |                  |                       |   CHAIN   |   
|                       |                  |                       |   NONE   |   
|                       |                  |                       |   BANK   |   
|       | encryptTokenOverrideIndicator   |   Encryption multipay token override indicator   |   NO   |   
|                       |                  |                       |   YES   |   
|       | encryptTypeCode   |   Encryption type code   |   INGENICO_ONGUARD   |   
|                       |                  |                       |   RSA_PKI   |   
|                       |                  |                       |   3DES   |   
|                       |                  |                       |   AES_DUKPT   |   
|                       |                  |                       |   VERIFONE_PROTECT_WITH_SP   |   
|                       |                  |                       |   NONE   |   
|                       |                  |                       |   VERIFONE_PROTECT   |   
|       | vspBrand   |   VSP brand indicates the TransArmor VeriFone VSP Brand   |      |   
|       | vspDomain   |   VSP domain Indicates the Corporate Identifier for TransArmor VeriFone Edition   |      |   
| VASTAP2PE   | 3des   |   3DES for Transarmor   |   NOT_CHECKED   |   
|                       |                  |                       |   CHECKED   |    
| VASADVINS   | advInsightBillingEffectiveDate   |   Billing Effective Date for Advertising Insights   |      |   
|       | advInsightOfferingType   |   Offering Type for Advertising Insights   |   STANDARD_OFFERING   |   
|       | advInsightStatus   |   Program Status for Advertising Insights   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASTAP2PE   | aesDukpt   |   AES DUKPT for Transarmor   |   CHECKED   |   
|                       |                  |                       |   NOT_CHECKED   |   
| VASNTWKTKN   | americanExpress   |   American Express Network Tokens   |   NO   |   
|                       |                  |                       |   YES   |   
| VASMSTTIST   | analyticsProductType   |   Product Offering That A Merchant Is Enrolled To Use.   |   MSI_APP   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   MSI_EXPRESS   |   
| VASWELLSP   | bobPreference   |   Wells Bob Preference Field   |   PRINT_ONLY   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
| VASBPMOB   | bpMobiletermType   |   Mobile Terminal Type for BP Mobile   |      |   
 VASWELLSP   | ceoLPreference   |   Wells Ceo Preference Field   |   PRINT_ONLY   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
| VASGBSPOSINS   | channel   |   Channel for GBS POS Installments   |   CBS   |
|                       |                  |                       |   CMM   |
|                       |                  |                       |   AGENT_ISV   |
| VASBPMOB   | chargebackInd   |   OEMV Chargeback Writeoff Indicator for BP Mobile   |   NO   |
|                       |                  |                       |   YES   |   
| VASMSTTIST   | cloverInsightsEmail   |   User Provided Clover Insights Email   |      |   
| VASSAMSPLS   | clubNum   |   SAMS Club - Club Number   |      |
| VASWELLSP   | companyId   |   Wells Company Id Field   |      |   
| VASPERKA   | contractSignDateTime   |   Date Time Contract Signed   |      |   
| VASBPMOB   | convenienceFeeInd   |   Convenience Fee Indicator for BP Mobile   |   NO   |   
|                       |                  |                       |   YES   |   
| VASMSTTIST   | dataRightsOptOutCode   |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.   |   OPTED_OUT   |   
|                       |                  |                       |   IAS_PRODUCT_EXCEPTION   |   
| VASDBTTERMID   | dbtTermIdStatus   |   Program Status for Debit Term Id   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASPAYEEZY   | developerEmailId   |   Developer Email ID   |      |   
|       | developerId   |   Developer ID   |      |   
| VASDISCDBTACP   | discDbtAcpOfferingType   |   Offering Type for Discover Debit Acceptance   |      |   
|       | discDbtAcpStatus   |   Program Status for Discover Debit Acceptance   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASDISCINCAUTH   | discIncAuthOfferingType   |   Offering Type for Discover Inc Auth   |      |   
|       | discIncAuthStatus   |   Program Status for Discover Inc Auth   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASDISCPROMPRG   | discPrmPrgEffectiveDate   |   Effective Date for Discover Prm Prg   |      |   
|       | discPrmPrgExpiryDate   |   Expiry Date for Discover Prm Prg   |      |   
|       | discPrmPrgOfferingType   |   offering Type for Discover Prm Prg   |      |   
|       | discPrmPrgPVI   |   PVI for Discover Prm Prg   |      |   
|       | discPrmPrgStatus   |   Program Status for Discover Prm Prg   |   APPROVED   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   DENIED   |   
| VASNTWKTKN   | discover   |   Discover Token   |   YES   |   
|                       |                  |                       |   NO   |   
| VASBPMOB   | ebtFnsNum   |   EBT FNS Number for BP Mobile   |      |   
| VASGBSPOSINS   | ecommercePlatform   |   Ecommerce Platform for GBS POS Installments   |   MIVA   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   OTHER   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
| VASEMVCMP   | emvBillingEffectiveDate   |   EMV Billing Effective Date   |      |   
|       | emvBillingExpirationDate   |   EMV Billing Expiration Date   |      |   
| VASEMVENB   | emvEnablementStatus   |   Program Status for EMV Enablement   |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
| VASEMVCMP   | emvOfferingType   |   EMV Offering Type   |   EMV_CAMPAIGN   |   
|       | emvProgramStatus   |   EMV Program Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASWSLENT   | enrollmentStatus   |   Enrollment Status for Wisely Entitlement   |      |   
| VASENTINSB   | entInsightBenchBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Bench   |      |   
|       | entInsightBenchStatus   |   Program Status for Enterprise Insights Bench   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
|       | entInsightBenchofferingType   |   Offering Type for Enterprise Insights Bench   |   WALLET_TRANSFER   |   
| VASENTINS   | entInsightBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights   |      |   
| VASENTINSD   | entInsightDemographicOfferingType   |   Offering Type for Enterprise Insights Demographic   |   STANDARD_OFFERING   |   
|       | entInsightDemographicStatus   |   Program Status for Enterprise Insights Demographic   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
|       | entInsightDemographicbillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Demographic   |      |   
| VASENTINSL   | entInsightLobbyBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Lobby   |      |   
|       | entInsightLobbyOfferingType   |   Offering Type for Enterprise Insights Lobby   |   STANDARD_OFFERING   |   
|       | entInsightLobbyStatus   |   Program Status for Enterprise Insights Lobby   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASENTINS   | entInsightOfferingType   |   Offering Type for Enterprise Insights   |   STANDARD_OFFERING   |   
|       | entInsightStatus   |   Program Status for Enterprise Insights   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASNTWKTKN   | fiservTokenRequesterId   |   Fiserv Token Requester ID for Network Tokens   |      |   
| VASFRDDTCT   | fraudDetectBillingEffectiveDate   |   Billing Effective Date for Fraud Detect   |      |   
|       | fraudDetectofferingType   |   Offering Type for Fraud Detect   |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|       | fraudDetectstatus   |   Program Status for Fraud Detect   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASFRDFLX   | fraudFlexBillingEffectiveDate   |   Billing Effective Date for Fraud Flex   |      |   
|       | fraudFlexOfferingType   |   Offering Type for Fraud Flex   |   STANDARD_OFFERING   |   
|       | fraudFlexStatus   |   Program Status for Fraud Flex   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASFRDDTCT   | gatewayApi   |   Fraud Detect Entry Point   |   FIRST_API   |   
|                       |                  |                       |   PAYEEZY   |   
|                       |                  |                       |   IPG   |   
|                       |                  |                       |   UCOMM   |   
|                       |                  |                       |   NONE   |   
| VASGBSPOSINS   | gbsPosInsStatus   |   Program Status for GBS POS Installment   |   APPROVED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|       | gbsPosInsofferingType   |   Offering Type for GBS POS Installment   |      |   
| VASTAP2PE   | ingenicoOnguard   |   Ingenico On-Guard for Transarmor   |   NOT_CHECKED   |   
|                       |                  |                       |   CHECKED   |   
| VASLCRDBT   | lcrDebitStatus   |   Program Status for LCR Debit Flags (Optional)   |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
| VASLCRFB   | lcrStatus   |   Program Status of LCR Fallback   |   APPLY_FALL_BACK   |   
|                       |                  |                       | DO_NOT_APPLY_FALLBACK   |   
| VASMSTTIST   | mainStreetProgramstatus   |   Program Status   |   CANCELLED_BY_FD   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   NO_RESPONSE   |   
|       | mainStreetbillingEffectiveDate   |   Billing Effective Date    |      |   
| VASNTWKTKN   | masterCard   |   Master Card Network Tokens   |   YES   |   
|                       |                  |                       |   NO   |     
| VASMSTPWLT   | masterpassofferingType   |   Masterpass Offering Type   |   STANDARD_OFFERING   |   
|       | masterpassstatus   |   Masterpass Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASMCMONEYSEND   | mcMoneySendOfferingType   |   Offering Type for MC Moneysend   |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   GAMING_PAYMENTS   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   RAPID_DEPOSIT   |      
|       | mcMoneySendStatus   |   Program Status for MC Moneysend   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASSAMSPLS   | memberShipId   |   SAMS Club Membership ID   |      |   
| VASMERSRCH   | merchSurchargeProgEffectiveDate   |   Surcharge Effective Date for Merchant Surcharge Program   |      |   
|       | merchSurchargeProgOfferingType   |   Offering Type for Merchant Surcharge Program   |   STANDARD_OFFERING   |   
|       | merchSurchargeProgSolutionType   |   Solution Type for Merchant Surcharge Program   |   FDMS_POS   |   
|                       |                  |                       |   NON_FDMS_POS   |   
|                       |                  |                       |   BLANK   |   
|       | merchSurchargeProgStatus   |   Program Status for Merchant Surcharge Program   |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|       | merchSurchargeProgSurchargeRate   |   Surcharge Rate for Merchant Surcharge Program   |      |   
| VASWSLENT   | merchantIdentifier   |   Merchant Identifier for Wisely Entitlement   |      |
| VASBPMOB   | mobInd   |   Mobile Indicator for BP Mobile   |   YES   |   
|                       |                  |                       |   NO   |   
| VASNTWKTKN   | networkTokenBillingEffectiveDate   |   Billing Effective Date for Network Tokens   |      |   
|       | networkTokenOfferingType   |   Offering Type for Network Tokens   |   NT_HYBRID   |   
|                       |                  |                       |   NT_STANDARD   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|       | networkTokenStatus   |   Program Status for Network Tokens   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASSAMSPLS   | newUpgRnwlInd   |   SAMS Club New/Upgrade/Renewal Indicator   |   NEW   |   
|                       |                  |                       |   UPGRADE   |   
|                       |                  |                       |   RENEWAL   |   
|                       |                  |                       |   NONE   |   
|       | nxtRnwlDt   |   SAMS Club Next Renewal Date   |      |   
| VASGBSPOSINS   | partner   |   Partner for GBS POS Installments   |   BREAD   |   
| VASPAYEEZY   | payezeeyBillingEffectiveDate   |   Billing Effective Date   |      |   
|       | payezeeyOfferingType   |   Payeezy Offering Type   |   STANDARD_OFFERING   |      
|       | payezeeyProgramStatus   |   Payeezy Program Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASPERKA   | perkaAccountNum   |   Perka Account Number   |      |   
|       | perkaAccountStatus   |   Account Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   PENDING   |    
|       | perkaBillingEffectiveDate   |   Billing Effective Date for Perka   |      |   
|       | perkaProductType   |   Perka Product Type   |   STANDARD_OFFERING   |   
|       | perkaTrainInd   |   Perka Training Indicator   |   TRAINING_REQUESTED   |   
|                       |                  |                       |   TRAINING_NOT_REQUESTED   |   
|       | perkaUniqueId   |   Perka Unique Identifier   |      |   
| VASPDATAPRT   | personalDataProtectionBillingEffectiveDate   |   Billing Effective Date for Personal Data Protection   |      |   
|       | personalDataProtectionOfferingType   |   Offering Type for Personal Data Protection   |   STANDARD_OFFERING   |     
|       | personalDataProtectionStatus   |   Program Status for Personal Data Protection   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASPINLESSECOM   | pinlessEcomStatus   |   Program Status for Pinless Ecomm   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASMSTTIST   | primaryEmailInd   |   Primary Email Indicator   |   USE_PRIMARY_EMAIL   |   
|                       |                  |                       |   USE_USER_PROVIDED   |   
| VASEMVCMP   | rebateAmount   |   EMV Rebate Amount   |      |    
| VASPERKA   | reccuringCharge   |   Recurring Charge   |      |   
| VASPAYEEZY   | referralCode   |   Referral Code   |      |   
| VASVRUSRV   | requestNewVruIdCd   |   Request New VRU Id For Compromised One   |   NEW_VRU_ID_REQUESTED   |   
|                       |                  |                       |   NEW_VRU_ID_COMPLETED   |   
|                       |                  |                       |   NO_REQUEST_OF_NEW_VRU   |   
| VASSAMSPLS   | rnwlAmtPaid   |   SAMS Club Renewal Amount Paid   |   FDMS_POS   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   PENDING   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   NON_FDMS_POS   |   
|                       |                  |                       |   BLANK   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   NO   |   
| VASTAP2PE   | rsavpki   |   rsavpki for Transarmor   |   NEW_VRU_ID_COMPLETED   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   FIRST_API   |   
|                       |                  |                       |   SPRINKLES   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   OPTED_OUT   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   NO_REQUEST_OF_NEW_VRU   |   
|                       |                  |                       |   NONE   |   
|                       |                  |                       |   SONNYS_BBQ   |   
|                       |                  |                       |   PAYEEZY   |   
|                       |                  |                       |   IPG   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   ABUELOS   |   
|                       |                  |                       |   NEW_VRU_ID_REQUESTED   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   PF_CHANGS   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   FIREBIRDS   |   
|                       |                  |                       |   BO_JANGLES   |   
|                       |                  |                       |   UNCLE_JULIO   |   
|                       |                  |                       |   UNION_SQ_HOSPITAL   |   
|                       |                  |                       |   IAS_PRODUCT_EXCEPTION   |   
|                       |                  |                       |   UCOMM   |   
|                       |                  |                       |   BREAD   |   
|                       |                  |                       |   PRINT_ONLY   |   
| VASTCKCP   | tckCpPrcsInd   |   Process Indicator Telecheck CP   |   USE_USER_PROVIDED   |   
|                       |                  |                       |   AGENT_ISV   |   
|                       |                  |                       |   CBS   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   USE_PRIMARY_EMAIL   |   
|                       |                  |                       |   CMM   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   NO   |   
|       | tckCpPrdct   |   Product for Telecheck CP   |   SPRINKLES   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   PAYEEZY   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   PF_CHANGS   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   UNCLE_JULIO   |   
|                       |                  |                       |   UNION_SQ_HOSPITAL   |   
|                       |                  |                       |   FIREBIRDS   |   
|                       |                  |                       |   NEW_VRU_ID_COMPLETED   |   
|                       |                  |                       |   UCOMM   |   
|                       |                  |                       |   NEW_VRU_ID_REQUESTED   |   
|                       |                  |                       |   IPG   |   
|                       |                  |                       |   FIRST_API   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   OPTED_OUT   |   
|                       |                  |                       |   BREAD   |   
|                       |                  |                       |   BO_JANGLES   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   IAS_PRODUCT_EXCEPTION   |   
|                       |                  |                       |   SONNYS_BBQ   |   
|                       |                  |                       |   ABUELOS   |   
|                       |                  |                       |   NO_REQUEST_OF_NEW_VRU   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   NONE   |   
|       | tckCpServEntl   |   Service Entitlement for Telecheck CP   |   CLOVER_ONLINE_STORE   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   MSI_EXPRESS   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   DELETE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   OTHER   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   YES   |   
|       | tckCpSettlInd   |   Settlement Indicator for Telecheck CP   |   NOT_CHECKED   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   FDMS_POS   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   BLANK   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   PENDING   |   
|                       |                  |                       |   NON_FDMS_POS   |   
|                       |                  |                       |   CANCEL   |   
|       | tckCpStatus   |   Program Status for Telecheck CP   |   DECLINED   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
| VASTEMPUS   | tempusProgramStatus   |   Tempus Program Status   |   DISCOVER_REVIEW   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
| VASPERKA   | term   |   Term   |   MONTHLY   |   
|                       |                  |                       |   OPTED_OUT   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   PROVISIONED   |   
|                       |                  |                       |   ANNUAL   |   
|                       |                  |                       |   PENDING   |   
|                       |                  |                       |   INITIATED   |   
|                       |                  |                       |   FAILED   |   
| VASBPMOB   | terminalType01   |   Terminal Type 01 for BP Mobile   |   FAILED   |   
|                       |                  |                       |   PROVISIONED   |   
|                       |                  |                       |   UPGRADE   |   
|                       |                  |                       |   INITIATED   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   RENEWAL   |   
|                       |                  |                       |   NONE   |   
|                       |                  |                       |   NEW   |   
|       | terminalType03   |   Terminal Type 03 for BP Mobile   |   PENDING   |   
|                       |                  |                       |   OPTED_OUT   |   
|                       |                  |                       |   ANNUAL   |   
|                       |                  |                       |   MONTHLY   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   FAILED   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   INITIATED   |   
|                       |                  |                       |   PROVISIONED   |   
| VASMERSRCH   | thirdParty   |   Third Party for Merchant Surcharge Program   |   OTHER   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   DELETE   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   MSI_EXPRESS   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   CLOVER_ONLINE_STORE   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   CLOVER   |   
| VASTXNINS   | transactionInsightBillingEffectiveDate   |   Billing Effective Date for Transaction Insights   |      |   
|       | transactionInsightOfferingType   |   Offering Type for Transaction Insights   |   PERSON_TO_PERSON   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   NOT_ELIGIBLE_ACQ_ON   |   
|                       |                  |                       |   EMV_CAMPAIGN   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   ELIGIBLE   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   AUTHORIZATION_DATA   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   GAMING_PAYMENTS   |   
|                       |                  |                       |   SETTLEMENT_DATA   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   CUP_ELIGIBLE   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   BLACK_LISTED   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   ALIPAY_ELIGIBLE   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   NT_HYBRID   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   NT_STANDARD   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   WHITE_LISTED   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   FD_DSCV_PROMO   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|       | transactionInsightStatus   |   Program Status for Transaction Insights   |   NO_RESPONSE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   FREE_TRIAL   |   
| VASTAP2PE   | transarmorP2peStatus   |   Transrmor P2PE Pragram Status   |   UNSUBSCRIBED   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
| VASTRNSARM   | transarmorProgramstatus   |   Transarmor Program Status   |   APPLY_FALL_BACK   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|       | transarmorofferingType   |   Transarmor Offering Type   |   NT_STANDARD   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   ALIPAY_ELIGIBLE   |   
|                       |                  |                       |   AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|                       |                  |                       |   GAMING_PAYMENTS   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   SETTLEMENT_DATA   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   WHITE_LISTED   |   
|                       |                  |                       |   ELIGIBLE   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   NOT_ELIGIBLE_ACQ_ON   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   EMV_CAMPAIGN   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   CUP_ELIGIBLE   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   FD_DSCV_PROMO   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   BLACK_LISTED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   NT_HYBRID   |   
|                       |                  |                       |   AUTHORIZATION_DATA   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
| VASTAP2PE   | verifoneProtect   |   Verifone Protect for Transarmor   |   MSI_EXPRESS   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   CLOVER_ONLINE_STORE   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   DELETE   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   OTHER   |   
|       | verifoneProtectWsp   |   Verifone Protect W/SP for  Transarmor   |   AGENT_ISV   |   
|                       |                  |                       |   USE_PRIMARY_EMAIL   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   CMM   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   USE_USER_PROVIDED   |   
|                       |                  |                       |   CBS   |   
| VASVETPRG   | veteransProgramType   |   Veterans Program Offering Type   |   ABUELOS   |   
|                       |                  |                       |   UNCLE_JULIO   |   
|                       |                  |                       |   BO_JANGLES   |   
|                       |                  |                       |   NO_REQUEST_OF_NEW_VRU   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   PF_CHANGS   |   
|                       |                  |                       |   NEW_VRU_ID_REQUESTED   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   FIRST_API   |   
|                       |                  |                       |   IAS_PRODUCT_EXCEPTION   |   
|                       |                  |                       |   SPRINKLES   |   
|                       |                  |                       |   PAYEEZY   |   
|                       |                  |                       |   NEW_VRU_ID_COMPLETED   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   NONE   |   
|                       |                  |                       |   OPTED_OUT   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   SONNYS_BBQ   |   
|                       |                  |                       |   UCOMM   |   
|                       |                  |                       |   IPG   |   
|                       |                  |                       |   UNION_SQ_HOSPITAL   |   
|                       |                  |                       |   FIREBIRDS   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   BREAD   |   
|       | veteransProgramstatus   |   Veterans Program Account Status   |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   OTHER   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   CLOVER_ONLINE_STORE   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   MSI_EXPRESS   |   
|                       |                  |                       |   DELETE   |   
| VASNTWKTKN   | visa   |   Visa Network Tokens   |   CENPOS   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   PRINT_ONLY   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   DELETE   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   MSI_EXPRESS   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   OTHER   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   CLOVER_ONLINE_STORE   |   
| VASVISAACTUPD   | visaAcctUpdStatus   |   Program Status for VISA Account Update   |   APPLY_FALL_BACK   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   CANCEL   |   
| VASVISAACTFNDTRX   | visaActFndOfferingType   |   Offering Type for Visa Account Funding   |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|                       |                  |                       |   NOT_ELIGIBLE_ACQ_ON   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   FD_DSCV_PROMO   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   BLACK_LISTED   |   
|                       |                  |                       |   NT_HYBRID   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
|                       |                  |                       |   EMV_CAMPAIGN   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   ALIPAY_ELIGIBLE   |   
|                       |                  |                       |   AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   WHITE_LISTED   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   SETTLEMENT_DATA   |   
|                       |                  |                       |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   CUP_ELIGIBLE   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   GAMING_PAYMENTS   |   
|                       |                  |                       |   NT_STANDARD   |   
|                       |                  |                       |   ELIGIBLE   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   AUTHORIZATION_DATA   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|       | visaActFndStatus   |   Program Status for Visa Account Funding   |   SUBSCRIBED   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   ACTIVE   |   
| VASVISACHKOUT   | visaChkOutStatus   |   Program Sttatus for Visa Check Out   |   PENDING_UPGRADE   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   DISCOVER_REVIEW   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
| VASVISAOCT   | visaOctOfferingType   |   Offering Type for Visa Oct   |   ELIGIBLE   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   AUTHORIZATION_DATA   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   NOT_ELIGIBLE_ACQ_ON   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   FD_DSCV_PROMO   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   BLACK_LISTED   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   EMV_CAMPAIGN   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   GAMING_PAYMENTS   |   
|                       |                  |                       |   NT_HYBRID   |   
|                       |                  |                       |   ALIPAY_ELIGIBLE   |   
|                       |                  |                       |   CUP_ELIGIBLE   |   
|                       |                  |                       |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   WHITE_LISTED   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   SETTLEMENT_DATA   |   
|                       |                  |                       |   NT_STANDARD   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|       | visaOctStatus   |   Program Status for Visa Oct   |   DISCOVER_REVIEW   |   
|                       |                  |                       |   SUBSCRIBED   |   
|                       |                  |                       |   NEW_APPLICATION   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   PENDING_UNCONTACTED   |   
|                       |                  |                       |   ACTIVE_SURCHARGING   |   
|                       |                  |                       |   MERCH_EQ_EMV_CAPABLE   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   CANCEL_SURCHARGING   |   
|                       |                  |                       |   MIX_EMV_AND_NON_EMV   |   
|                       |                  |                       |   IN_PROGRESS   |   
|                       |                  |                       |   CANCELLED_BY_MERCHANT   |   
|                       |                  |                       |   CANCELLED_BY_FD   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   NO_RESPONSE   |   
|                       |                  |                       |   UNSUBSCRIBED   |   
|                       |                  |                       |   PENDING_CONTACTED   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   DONT_APPLY_DEBIT_FLAGS   |   
|                       |                  |                       |   LIVE   |   
|                       |                  |                       |   DECLINED   |   
|                       |                  |                       |   APPLY_FALL_BACK   |   
|                       |                  |                       |   FREE_TRIAL   |   
|                       |                  |                       |   APPROVED   |   
|                       |                  |                       |   DENIED   |   
|                       |                  |                       |   DO_NOT_APPLY_FALLBACK   |   
|                       |                  |                       |   ALLOW_DEBIT_FLAGS   |   
|                       |                  |                       |   PENDING_UPGRADE   |   
| VASVRUSRV   | vruServiceofferingType   |   VRU Services Offering Type   |   GAMING_PAYMENTS   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
|                       |                  |                       |   AUTHORIZATION_DATA   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   FRAUD_DETECT_SMB_TRIAL   |   
|                       |                  |                       |   STANDARD_OFFERING   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   CASH_2_ATM   |   
|                       |                  |                       |   TR_OWN_DB_OR_PP_CARD   |   
|                       |                  |                       |   FRAUD_DETECT_SMB   |   
|                       |                  |                       |   SETTLEMENT_DATA   |   
|                       |                  |                       |   ESSENTIALS   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   PYMNT_OF_OWN_CC_BILL   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|                       |                  |                       |   ELIGIBLE   |   
|                       |                  |                       |   NT_HYBRID   |   
|                       |                  |                       |   STANDARD   |   
|                       |                  |                       |   CUP_ELIGIBLE   |   
|                       |                  |                       |   P2P_TRANSFER_TO_CARD   |   
|                       |                  |                       |   BUS_DISBURS_TO_CARD   |   
|                       |                  |                       |   NT_ON_THE_GO   |   
|                       |                  |                       |   ALIPAY_ELIGIBLE   |   
|                       |                  |                       |   WHITE_LISTED   |   
|                       |                  |                       |   PREMIUM   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   BLACK_LISTED   |   
|                       |                  |                       |   FD_DSCV_PROMO   |   
|                       |                  |                       |   CASH_2_CARD   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   NT_STANDARD   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   STAGED_WALLET_LOAD   |   
|                       |                  |                       |   NOT_ELIGIBLE_ACQ_ON   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   P2P_TRANSFER   |   
|                       |                  |                       |   GOV-NPROF_DISBRMTS   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   AGENT_CASH_OUT   |   
|                       |                  |                       |   ADVANCED   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PMT   |   
|                       |                  |                       |   BUS_TO_BUS_TRANSFER   |   
|                       |                  |                       |   AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |   GEN_B2B_TRAN_TO_CARD   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   EMV_CAMPAIGN   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
| VASPAYEEZY   | webStore   |   Web Store   |   PRINT_ONLY   |   
|                       |                  |                       |   CHECKED   |   
|                       |                  |                       |   MIVA   |   
|                       |                  |                       |   SHOPIFY   |   
|                       |                  |                       |   3DCART   |   
|                       |                  |                       |   ONLINE_AND_PRINT   |   
|                       |                  |                       |   OTHER   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   MAGENTO2   |   
|                       |                  |                       |   MSI_EXPRESS   |   
|                       |                  |                       |   KIBO   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   ONLINE_ONLY   |   
|                       |                  |                       |   DELETE   |   
|                       |                  |                       |   SALESFORCE_COMMERCE   |   
|                       |                  |                       |   BIGCOMMERCE   |   
|                       |                  |                       |   NOT_APPLICABLE   |   
|                       |                  |                       |   MAIN_STREET_INSIGHTS   |   
|                       |                  |                       |   NO   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   NOT_CHECKED   |   
|                       |                  |                       |   YES   |   
|                       |                  |                       |   ACTIVE   |   
|                       |                  |                       |   MSI_APP   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   CLOVER_ONLINE_STORE   |   
|                       |                  |                       |   ADD   |   
|                       |                  |                       |   VALUELINK   |   
|                       |                  |                       |   CLOVER   |   
|                       |                  |                       |   CANCEL   |   
|                       |                  |                       |   ORACLE_NET_SUITE   |   
|                       |                  |                       |   WOOCOMMERCE   |   
|                       |                  |                       |   NON_SURCHARGE_SNAPPAY_CARDX   |   

<!-- type: tab-end -->
