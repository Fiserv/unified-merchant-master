# Product Attributes - VAS

## List of Domains

### cashAdvance

---

tags: [cashAdvance]

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |
---
 

|   Product Code   | Attribute         | Description               | Values        | Value Description                  |
|:---------------------|:---------------------|:--------------------------|:--------------|:----------------------------------|
| VASCASHADV| activeDate   |   Cash Advance Activation Date   |       |      |
|           | advanceAmount   |   Cash Advance Amount   |       |      |
|           | bookingDate   |   Cash advance Booking Date   |       |      |
|           | branchCode   |   Cash Advance Branch Code   |       |      |
|           | businessSegment   |   Cash Advance Business Segment   |       |      |
|           | cashAdvanceBankSequenceNumber   |   Cash Advance Bank Sequence Number added to Merchant Bank Account   |       |      |
|           | contractTerm   |   Cash Advance Contract Term   |       |      |
|           | dailyWithholdPercentage   |   Cash Advance Daily Withhold Percentage   |       |      |
|           | estPaybackPeriod   |   Cash Advance EST Payback Period   |       |      |
|           | finalPaymentDate   |   Cash Advance Final Payment Date   |       |      |
|           | firstPaymentDate   |   Cash Advance First Payment Date   |       |      |
|           | fundingDate   |   Cash Advance Funding Date   |       |      |
|           | grossIncome   |   Cash Advance Gross Income   |       |      |
|           | invDueDate   |   Cash Advance Invoice Due Date   |       |      |
|           | lastPaymentDate   |   Cash Advance Last Payment Date   |       |      |
|           | legalStatus   |   Lease Legal Status   |    013   |   PIF_MERCH_KEEP_EQUIP   |
|           |           |                    |    017   |   RECOURSE_PIF   |
|           |           |                    |    011   |   WRITEOFF_REVERSAL   |
|           |           |                    |    016   |   END_OF_LEASE_W_RTN_EQUIP   |
|           |           |                    |    008   |   WRITEOFF_DEAD   |
|           |           |                    |    015   |   PIF_MERCH_RETURN_EQUIP   |
|           |           |                    |    005   |   WRITEOFF   |
|           |           |                    |    007   |   CANCELLED   |
|           |           |                    |    014   |   SIF_MERCH_KEEP_EQUIP   |
|           |           |                    |    004   |   BUYBACK   |
|           |           |                    |    020   |   EQUIP_RETURNED_TO_TASQ   |
|           |           |                    |    001   |   ATTORNEY_NEGOTIATION   |
|           |           |                    |    019   |   SIF_MERCH_RETURN_EQUIP   |
|           |           |                    |    012   |   UPGRADE_BUYOUT   |
|           | netIncome   |   Cash Advance Net Income   |       |      |
|           | payBackAmount   |   Cash Advance Pay Back Amount   |       |      |
|           | priorCashAdvanceId   |   Prior Cash Advance ID   |       |      |
|           | receivedAmount   |   Cash Advance Received Amount   |       |      |
|           | relationshipCode   |   Cash Advance Relationship Code   |       |      |
|           | remainingAmount   |   Cash Advance Remaining Amount   |       |      |
|           | terminationDate   |   Cash Advance Termination Date   |       |      |


<!-- type: tab-end -->


### lease

---

tags: [lease]

* **List of Attributes**: Applicable for UMM, North and GMA
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |
---


|   Product Code   | Attribute         | Description               | Values        | Value Description                  |
|:---------------------|:---------------------|:--------------------------|:--------------|:----------------------------------|
| VASLEASE| leaseActivationDate   |   The activation date of the contract. Entering this date activates the contract. InfoLease uses this date along with the Contract Term and the Payments in Arrears Code to determine the termination date of the contract.   |       |      |
| VASLEASE| leaseAdditionalMid   |   This will be the Mainframe MID for ISOs that have a 15 digit MID that contains a zero added to the infolease record for cash advance   |       |      |
|         | leaseAmortizableResidualAmount   |   The calculation for amortizable residual is as follows.~ ~ Gross Residual~ - Residual Writedown ~ - Discount Residual~ - Present Value Amount~ = Amount of Residual Amortized~ ~ This field usually projects a conservative amount for residual. The Managers Residual field generally projects a more optimistic figure.   |       |      |
|         | leaseApproverSignatoryName   |   The name of the person who signs the contract. This field defaults to the name entered in the Contact Name field.   |       |      |
|         | leaseBankSequenceNumber   |   Lease Bank Sequence Number added to Merchant Bank Account   |       |      |
|         | leaseBillingCycle   |   Billing Cycle of a lease   |    S   |   SEMI_ANNUAL   |
|         |           |                    |    Q   |   QUARTERLY   |
|         |           |                    |    M   |   MONTHLY   |
|         |           |                    |    N   |   NO   |
|         |           |                    |    Y   |   YES   |
|         |           |                    |    A   |   ANNUAL   |
|         | leaseBranchCode   |   This 5-character code indicates the branch associated with the contract. You can use the branch as a sort sequence when requesting reports.   |       |      |
|         | leaseBusinessSegment   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.   |       |      |
|         | leaseBusinessSegmentCode   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.   |       |      |
|         | leaseBuyoutQuoteCode   |   This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.   |    NO   |   NO   |
|         |           |                    |    YES   |   YES   |
|         | leaseCollateralCode   |   This code identifies additional collateral (other than the actual equipment) assigned to a contract.   |       |      |
|         | leaseCompanyName   |   UATB.LEASING.COMPANY   |       |      |
|         | leaseContractBalanceAmount   |   Contract balance remaining after all payments received are applied to the gross contract. This amount is system-calculated.   |       |      |
|         | leaseContractStatus   |   The status of the contract.    |    YES   |   YES   |
|         |           |                    |    NO   |   NO   |
|         | leaseContractStatusDate   |   The date the status was assigned to the contract.   |       |      |
|         | leaseContractStatusDesc   |   Contract Status Description   |       |      |
|         | leaseContractTerm   |   The term of the contract in months. If a commencement date was entered, this field is mandatory.The maximum term is 400 months.   |       |      |
|         | leaseContractTotalReceivedAmount   |   The total contract payment amount received from the beginning of the contract. This is a system-calculated amount.~ ~ Note: If a partial disposition has taken place, this represents the payments on the active portion of the contract only.   |       |      |
|         | leaseCustomerAccountReceivableName   |   The accounts receivable name. This name prints on the customers invoice.   |       |      |
|         | leaseCustomerArAddressAttentionName   |   Information entered in this field prints on the invoice, i.e., the name of the person to whom you are mailing the invoice.   |       |      |
|         | leaseCustomerArAddressCityName   |   The city for the accounts receivable address.   |       |      |
|         | leaseCustomerArAddressCountryCode   |   The country code for the accounts receivable address.   |       |      |
|         | leaseCustomerArAddressLine1   |   The first line of the accounts receivable address. This address prints on the customers invoice.   |       |      |
|         | leaseCustomerArAddressLine2   |   The second line of the accounts receivable address. This address prints on the customers invoice.   |       |      |
|         | leaseCustomerArAddressLine3   |   The third line of the accounts receivable address. This address prints on the customers invoice.   |       |      |
|         | leaseCustomerArAddressPostalCode   |   The zip code of the city for the accounts receivable address.   |       |      |
|         | leaseCustomerArAddressStateName   |   The state for accounts receivable address.   |       |      |
|         | leaseCustomerCreditScore   |   A user-defined score given by the leasing company extending credit to the lessee. A credit score is based on certain factors, such as age, marital status, length of employment, etc. Each of these factors is assigned a certain point value with the total being the credit score. Based on this score, the lessee is approved for the credit.   |       |      |
|         | leaseCustomerDoingBusinessName   |   The Customerdoing business name   |       |      |
|         | leaseCustomerFedSsnId   |   The appropriate identification number.  The ability to modify this field depends on your security settings.   |       |      |
|         | leaseCustomerName   |   The customer name. Use the customer name to create alphabetical listings and locate a name when using Soundex.   |       |      |
|         | leaseCustomerShortName   |   The Short Name is another name to use when referring to the customer. The Short Name cannot be the same as the Customer Name. This field defaults to the Short Name previously entered for the customer.   |       |      |
|         | leaseDelinquentStatusCode   |   The delinquent status of the contract. This is a system-calculated field.    |    151   |   PAST_DUE_151_180_DAYS   |
|         |           |                    |    91   |   PAST_DUE_91_120_DAYS   |
|         |           |                    |    61   |   PAST_DUE_61_90_DAYS   |
|         |           |                    |    31   |   PAST_DUE_31_60_DAYS   |
|         |           |                    |    01   |   PAST_DUE_01_30_DAYS   |
|         |           |                    |    00   |   NOT_DELINQUENT   |
|         |           |                    |    121   |   PAST_DUE_121_150_DAYS   |
|         |           |                    |    181   |   PAST_DUE_181_DAYS_AND_MORE   |
|         | leaseDispositionDate   |   The last date any disposition or inventory occurred on the contract. InfoLease updates this field at the time of a disposition.   |       |      |
|         | leaseEarlyBuyoutAmount   |   You can enter buyout amounts for the contract in this field. You must first fill in the Date field. The information in this field does not default to the Buyout Quotes module.   |       |      |
|         | leaseEarlyBuyoutDate   |   You can enter the buyout date for the contract in this field. Entering information here does not default to the Buyout Quotes module.   |       |      |
|         | leaseFacilityScore   |   This score represents the credit score of the deal, not the credit score of the customer.   |       |      |
|         | leaseFdmsDecisionDate   |   UATB.DATE.FDMS.DECISION   |       |      |
|         | leaseFdmsDecisionInd   |   UATB.FDMS.DECISION   |       |      |
|         | leaseFinalPaymentDate   |   This field identifies the date the last contract payment is due. This is a system-calculated field using the contract term, the number of advance payments, the number of payments in arrears, the commencement date, and the billing cycle.   |       |      |
|         | leaseFirstPaymentAmount   |   If the first payment is different from the regular scheduled payments, enter the amount here; otherwise, InfoLease defaults the regular contract payment. If no payment is due in the first month, enter zero.   |       |      |
|         | leaseFirstPaymentDate   |   The first payment date. This is a required field. InfoLease calculates the default date based on the commencement date, billing cycle, variable payment schedule, and the payments in arrears code.   |       |      |
|         | leaseFloatingRateIndicator   |   This yes/no field indicates whether this is a floating rate contract.   |    N   |   NO   |
|         |           |                    |    Y   |   YES   |
|         | leaseFollowUpDays   |   The number of days after the payment due date that you need to contact the customer. InfoLease uses the number of follow-up days to generate follow-up lists for payment collections. This field is used with the Customer Service Module.   |       |      |
|         | leaseGeneralLedgerBookingDate   |   Lease General Booking Date   |       |      |
|         | leaseGrossAssetAmount   |   The total equipment cost for all assets (not including disposed assets) on the contract.   |       |      |
|         | leaseGrossFinanceAmount   |   The total amount of finance or interest income (difference between the gross contract amount and the equipment cost). If a commencement date was entered, this field is mandatory.   |       |      |
|         | leaseGrossPaymentAmount   |   The total amount of payments due on the contract. If a commencement date was entered, this field is mandatory.   |       |      |
|         | leaseIncomeStartDate   |   The date the income on the contract begins to amortize. This date affects how InfoLease calculates the IRR. This date defaults to the commencement date of the contract; however, in cases where interest free periods exist, you can modify this date.   |       |      |
|         | leaseInterimRentAmount   |   The amount of interest payments received prior to the commencement of the contract.   |       |      |
|         | leaseInvoiceCode   |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.   |    N   |   NO_MORE_INVOICING   |
|         |           |                    |    M   |   MANUAL_INVOICING   |
|         |           |                    |    S   |   INVOICE_SUPRESSED   |
|         |           |                    |    D   |   SEPARATED_BY_NOTE_DATE   |
|         |           |                    |    C   |   INVOICE_BY_CONTRACT   |
|         |           |                    |    A   |   INVOICE_BY_CUSTOMER   |
|         |           |                    |    R   |   RENTALS_SEPARATED   |
|         |           |                    |    B   |   CONTRACT_SEPARATED_INDIVIDUAL_INVOICES   |
|         | leaseInvoiceDueDate   |   The day of the month the payment is due. If you do not enter the invoicing due day, the field defaults to the due day on the Customer Default Data Screen.    |       |      |
|         | leaseLastPaymentDate   |   The date you received the last payment.   |       |      |
|         | leaseLegalStatus   |   Lease Legal Status   |    015   |   PIF_MERCH_RETURN_EQUIP   |
|         |           |                    |    005   |   WRITEOFF   |
|         |           |                    |    007   |   CANCELLED   |
|         |           |                    |    014   |   SIF_MERCH_KEEP_EQUIP   |
|         |           |                    |    004   |   BUYBACK   |
|         |           |                    |    020   |   EQUIP_RETURNED_TO_TASQ   |
|         |           |                    |    013   |   PIF_MERCH_KEEP_EQUIP   |
|         |           |                    |    001   |   ATTORNEY_NEGOTIATION   |
|         |           |                    |    017   |   RECOURSE_PIF   |
|         |           |                    |    012   |   UPGRADE_BUYOUT   |
|         |           |                    |    011   |   WRITEOFF_REVERSAL   |
|         |           |                    |    019   |   SIF_MERCH_RETURN_EQUIP   |
|         |           |                    |    008   |   WRITEOFF_DEAD   |
|         |           |                    |    016   |   END_OF_LEASE_W_RTN_EQUIP   |
|         | leaseManagerResidualAmount   |   An alternate residual amount that you can select when calculating a buyout quote. Managers residual does not accrue income.This field usually projects an optimistic figure for residual. The Amortizable Residual field usually projects a more conservative figure.   |       |      |
|         | leaseMerchantId   |   Lease Merchant ID   |       |      |
|         | leaseMonthlyPaymentAmount   |   The amount of the contract payment. If this is a variable payment contract, do not enter a contract payment here.   |       |      |
|         | leaseNetFinanceAmount   |   Net finance is the difference between the gross finance income and the setup income. If Prov Loss Fr Fin = (Y)es, InfoLease also subtracts Provision for Loss from net finance. This amount is system-calculated and you cannot modify it.    |       |      |
|         | leaseNetInvestmentAmount   |   The net investment of the contract. The net investment is the loss the lessor would incur if the lessee stopped payment today.   |       |      |
|         | leaseNextAgingDate   |   The next date InfoLease will age the contract. You cannot modify this field.    |       |      |
|         | leaseNextChargeDate   |   The next date InfoLease will assess the appropriate late charges during the aging process. You cannot modify this field. InfoLease updates this field whenever you run aging.   |       |      |
|         | leaseNumberOfAsset   |   The number of active assets associated with the contract.   |       |      |
|         | leasePaymentInvoicedCount   |   The number of payments billed to the customer.   |       |      |
|         | leasePaymentOptionCode   |   This field depicts different options of Lease Payment.   |    T   |   TAPE   |
|         |           |                    |    N   |   NORMAL_PAY   |
|         |           |                    |    A   |   ASSUMED_PAY   |
|         |           |                    |    P   |   POST_DATED_CHEQUE   |
|         |           |                    |    C   |   COUPON   |
|         |           |                    |    U   |   UNDISCOUNTED_PAYMENT   |
|         |           |                    |    D   |   DISCOUNTED_PAYMENT   |
|         | leasePaymentPaidToDate   |   Contract payments are paid up to, but not including, this date. This field is based on the due dates of unpaid open items or the next due date (invoicing date plus lead invoicing days) if there are no unpaid open items.    |       |      |
|         | leasePaymentUpfrontAmount   |   The number of beginning payments paid in advance by the customer at contract commencement. Without the Customer Service Module, this field is informational only.   |       |      |
|         | leasePendingCode   |   This field identifies outstanding information, e.g., paperwork, correspondence, you expect to receive for the contract.   |       |      |
|         | leasePlatformCode   |   PLATFORM   |       |      |
|         | leasePreviousContractNumber   |   Lease Previous Contract Number   |       |      |
|         | leasePreviousDelinquentStatusCode   |   The previous delinquent status of the contract. If the Delinquent Status Code changes, the previous status is moved to the Previous Delinquent Status field.   |       |      |
|         | leaseProgramTypeCode   |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.   |    0012   |   VAPP   |
|         |           |                    |    0004   |   CROSS_SALES_LARGE_LEASE   |
|         |           |                    |    0019   |   MCA_FDIS_ISO   |
|         |           |                    |    0099   |   IMS_PORTFOLIO_PURCHASE   |
|         |           |                    |    0016   |   CASH_ADVANCE   |
|         |           |                    |    0007   |   ATLANTA_TELESALES   |
|         |           |                    |    0015   |   RSA_RECOURSE_PROJECT   |
|         |           |                    |    0003   |   CROSS_SALES   |
|         |           |                    |    0006   |   DBG_RECOURSE   |
|         |           |                    |    0021   |   MCA_REGIONAL_SALES   |
|         |           |                    |    0011   |   SAMS_NY_TELESALES   |
|         |           |                    |    0005   |   PAPERLESS_LEASE   |
|         |           |                    |    0020   |   MCA_FDIS_AGENT   |
|         |           |                    |    0009   |   RSA_SEVEN_DAY_NO_PPWK   |
|         |           |                    |    0022   |   CLOVER   |
|         |           |                    |    0018   |   MCA_TELESALES   |
|         |           |                    |    0008   |   RSA_SEVEN_DAY   |
|         |           |                    |    0001   |   LARGE_LEASE   |
|         | leaseProvisionForLossAmount   |   The amount set aside to record in the first month for bad debt expense. Enter an amount or default to the system-calculated amount. Gross Contract x Provision for Loss Percentage (lessor file) = Provision for Loss Enter the provision for loss percentage in the Prov for Loss field accessed via the Lessor Parameter Maintenance Screen and the Lessor Default Fields Screen.   |       |      |
|         | leaseRelationCode   |   Lease Relationship code   |       |      |
|         | leaseRenewalStatusCode   |   Lease Renewal status code   |       |      |
|         | leaseResidualAmount   |   This field displays once information is entered in residual amount at the asset level. This field cannot be entered or maintained at the contract level. However, a residual change at the asset level affects the gross residual.   |       |      |
|         | leaseSaleLeasebackInd   |   Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.   |    N   |   NO   |
|         |           |                    |    Y   |   YES   |
|         | leaseSecurityDepositAmount   |   This window displays the Security Deposit and the Down Payment fields.The Security Deposit field represents the amount received from the lessee. The Down Payment field represents the amount received from the lessee.    |       |      |
|         | leaseTaxExemptIndicator   |   This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.   |    N   |   NO   |
|         |                           |                     |    Y   |   YES   |
|         | leaseTermDate   |   The date the contract expires.This date is system-generated and you cannot enter or maintain it at the contract level. However, a new date is generated if the Commencement Date, Contract Term, or the Payments In Arrears code is changed.   |       |      |
|         | leaseTotalRentalPaymentNumber   |   Total number of rental payments made to date.   |       |      |
|         | leaseTypeCode   |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.   |    RL   |   RENTAL_LEASE   |
|         |           |                    |    RA   |   REVOLVING_ACCOUNT   |
|         |           |                    |    TL   |   TRUE_LEASE   |
|         |           |                    |    LL   |   LEVERAGED_LEASE   |
|         |           |                    |    LP   |   LEASE_PURCHASE   |
|         |           |                    |    LN   |   TERM_LOAN   |
|         |           |                    |    OL   |   OPERATING_LEASE   |
|         |           |                    |    CS   |   CONDITIONAL_SALE   |
|         | leaseVariablePaymentAmount   |   Variable Payment Amount of the lease   |       |      |
|         | leaseVariablePaymentIndicator   |   This yes/no field indicates whether this contract has a variable payment schedule.    |    Y   |   YES   |
|         |           |                    |    N   |   NO   |
|         | leaseWriteOffAmount   |   The income used to offset the initial expense associated with a new lease. The amount is calculated by multiplying the setup income percentage on the Lessor Parameter File by the gross finance income.   |       |      |

<!-- type: tab-end -->
