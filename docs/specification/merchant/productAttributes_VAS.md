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
| VASSAMSPLS   | rnwlAmtPaid   |   SAMS Club Renewal Amount Paid   |      |   
| VASTAP2PE   | rsavpki   |   rsavpki for Transarmor   |   CHECKED   |   
|                       |                  |                       |   NOT_CHECKED   |   
| VASTCKCP   | tckCpPrcsInd   |   Process Indicator Telecheck CP   |      |   
|       | tckCpPrdct   |   Product for Telecheck CP   |      |   
|       | tckCpServEntl   |   Service Entitlement for Telecheck CP   |      |   
|       | tckCpSettlInd   |   Settlement Indicator for Telecheck CP   |      |   
|       | tckCpStatus   |   Program Status for Telecheck CP   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASTEMPUS   | tempusProgramStatus   |   Tempus Program Status   |   ACTIVE   |   
|                       |                  |                       |  CANCEL   |   
| VASPERKA   | term   |   Term   |   ANNUAL   |   
|                       |                  |                       |   MONTHLY   |   
| VASBPMOB   | terminalType01   |   Terminal Type 01 for BP Mobile   |      |   
|       | terminalType03   |   Terminal Type 03 for BP Mobile   |      |   
| VASMERSRCH   | thirdParty   |   Third Party for Merchant Surcharge Program   |   NON_SURCHARGE_SNAPPAY_CARDX   |   
|                       |                  |                       |   SNAPPAY_CARDX   |   
|                       |                  |                       |   CARDX   |   
|                       |                  |                       |   TEMPUS   |   
|                       |                  |                       |   CENPOS   |   
|                       |                  |                       |   OTHER   |   
| VASTXNINS   | transactionInsightBillingEffectiveDate   |   Billing Effective Date for Transaction Insights   |      |   
|       | transactionInsightOfferingType   |   Offering Type for Transaction Insights   |   STANDARD_OFFERING   |     
|       | transactionInsightStatus   |   Program Status for Transaction Insights   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASTAP2PE   | transarmorP2peStatus   |   Transrmor P2PE Pragram Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASTRNSARM   | transarmorProgramstatus   |   Transarmor Program Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
|       | transarmorofferingType   |   Transarmor Offering Type   |   SETTLEMENT_DATA   |   
|                       |                  |                       |  AUTH_AND_SETTLEMENT   |   
|                       |                  |                       |  AUTHORIZATION_DATA   |     
| VASTAP2PE   | verifoneProtect   |   Verifone Protect for Transarmor   |   CHECKED   |   
|                       |                  |                       |   NOT_CHECKED   |   
|       | verifoneProtectWsp   |   Verifone Protect W/SP for  Transarmor   |   CHECKED   |   
|                       |                  |                       |   NOT_CHECKED   |   
| VASVETPRG   | veteransProgramType   |   Veterans Program Offering Type   |   STANDARD_OFFERING   |   
|       | veteransProgramstatus   |   Veterans Program Account Status   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   |   
| VASNTWKTKN   | visa   |   Visa Network Tokens   |   YES   |   
|                       |                  |                       |   NO   |   
| VASVISAACTUPD   | visaAcctUpdStatus   |   Program Status for VISA Account Update   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASVISAACTFNDTRX   | visaActFndOfferingType   |   Offering Type for Visa Account Funding   |   PERSON_TO_PERSON   |   
|                       |                  |                       |   FUNDS_TRANSFER   |   
|                       |                  |                       |   PREPAID_LOADS   |   
|                       |                  |                       |   NON-CARD_BILL_PAY   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   BANK_INITIATED_TRANS   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   CREDIT_CARD_BILL_PAY   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|       | visaActFndStatus   |   Program Status for Visa Account Funding   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASVISACHKOUT   | visaChkOutStatus   |   Program Sttatus for Visa Check Out   |   CANCEL   |   
|                       |                  |                       |   ACTIVE   | 
| VASVISAOCT   | visaOctOfferingType   |   Offering Type for Visa Oct   |   FUNDS_TRANSFER   |   
|                       |                  |                       |   WALLET_TRANSFER   |   
|                       |                  |                       |   GAMBLING_PAYOUT   |   
|                       |                  |                       |   BUSINESS_TO_BUSINESS   |   
|                       |                  |                       |   PAYRL_PNSN_DISBRSMNT   |   
|                       |                  |                       |   BANK_INITIATED_P2P   |   
|                       |                  |                       |   RAPID_DEPOSIT   |   
|                       |                  |                       |   CASH_DEPOSIT   |   
|                       |                  |                       |   PERSON_TO_PERSON   |   
|                       |                  |                       |   ACCOUNT_TO_ACCOUNT   |   
|                       |                  |                       |   MNY_TRFR_MERCH_INIT   |   
|                       |                  |                       |   LOYALTY_N_OFFERS   |   
|                       |                  |                       |   FUNDS_DISBURSEMENTS   |   
|                       |                  |                       |   MERCH_DISBURSEMENTS   |   
|                       |                  |                       |   GOVT_DISBURSEMENTS   |   
|                       |                  |                       |   ONLINE_GAMBLING   |   
|       | visaOctStatus   |   Program Status for Visa Oct   |   ACTIVE   |   
|                       |                  |                       |   CANCEL   |   
| VASVRUSRV   | vruServiceofferingType   |   VRU Services Offering Type   |   BLACK_LISTED   |   
|                       |                  |                       |   WHITE_LISTED   |    
| VASPAYEEZY   | webStore   |   Web Store   |   CLOVER_ONLINE_STORE   |   

<!-- type: tab-end -->
