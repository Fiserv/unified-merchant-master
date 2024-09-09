# Product Attributes - VAS

## List of Domains

### cashAdvance

---

tags: [cashAdvance]

* List of Attributes: Applicable for UMM, North and UMA

<!-- type: tab 
titles: UMM
-->

|   Product Code   | Attribute         | Description               | Values        | Value Description                  | Inquiry  | Create   | Update   |  Delete  |
|:---------------------|:---------------------|:--------------------------|:--------------|:----------------------------------|:--------:|:--------:|:--------:|:--------:|
| VASCASHADV| activeDate   |   Cash Advance Activation Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | advanceAmount   |   Cash Advance Amount   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | bookingDate   |   Cash advance Booking Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | branchCode   |   Cash Advance Branch Code   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | businessSegment   |   Cash Advance Business Segment   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | cashAdvanceBankSequenceNumber   |   Cash Advance Bank Sequence Number added to Merchant Bank Account   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | contractTerm   |   Cash Advance Contract Term   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | dailyWithholdPercentage   |   Cash Advance Daily Withhold Percentage   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | estPaybackPeriod   |   Cash Advance EST Payback Period   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | finalPaymentDate   |   Cash Advance Final Payment Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | firstPaymentDate   |   Cash Advance First Payment Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | fundingDate   |   Cash Advance Funding Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | grossIncome   |   Cash Advance Gross Income   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | invDueDate   |   Cash Advance Invoice Due Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | lastPaymentDate   |   Cash Advance Last Payment Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | legalStatus   |   Lease Legal Status   |    013   |   PIF_MERCH_KEEP_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    017   |   RECOURSE_PIF   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    011   |   WRITEOFF_REVERSAL   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    016   |   END_OF_LEASE_W_RTN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    008   |   WRITEOFF_DEAD   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    015   |   PIF_MERCH_RETURN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    005   |   WRITEOFF   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    007   |   CANCELLED   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    014   |   SIF_MERCH_KEEP_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    004   |   BUYBACK   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    020   |   EQUIP_RETURNED_TO_TASQ   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    001   |   ATTORNEY_NEGOTIATION   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    019   |   SIF_MERCH_RETURN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|           |           |                    |    012   |   UPGRADE_BUYOUT   |         Available      |      Optional      |      Allowed       |         NA         |
|           | netIncome   |   Cash Advance Net Income   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | payBackAmount   |   Cash Advance Pay Back Amount   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | priorCashAdvanceId   |   Prior Cash Advance ID   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | receivedAmount   |   Cash Advance Received Amount   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | relationshipCode   |   Cash Advance Relationship Code   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | remainingAmount   |   Cash Advance Remaining Amount   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|           | terminationDate   |   Cash Advance Termination Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |


<!-- type: tab-end -->


### lease

---

tags: [lease]

* List of Attributes: Applicable for UMM, North and UMA

<!-- type: tab 
titles: UMM
-->

|   Product Code   | Attribute         | Description               | Values        | Value Description                  | Inquiry  | Create   | Update   |  Delete  |
|:---------------------|:---------------------|:--------------------------|:--------------|:----------------------------------|:--------:|:--------:|:--------:|:--------:|
| VASLEASE| leaseActivationDate   |   The activation date of the contract. Entering this date activates the contract. InfoLease uses this date along with the Contract Term and the Payments in Arrears Code to determine the termination date of the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
| VASLEASE| leaseAdditionalMid   |   This will be the Mainframe MID for ISOs that have a 15 digit MID that contains a zero added to the infolease record for cash advance   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseAmortizableResidualAmount   |   The calculation for amortizable residual is as follows.~ ~ Gross Residual~ - Residual Writedown ~ - Discount Residual~ - Present Value Amount~ = Amount of Residual Amortized~ ~ This field usually projects a conservative amount for residual. The Managers Residual field generally projects a more optimistic figure.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseApproverSignatoryName   |   The name of the person who signs the contract. This field defaults to the name entered in the Contact Name field.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBankSequenceNumber   |   Lease Bank Sequence Number added to Merchant Bank Account   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBillingCycle   |   Billing Cycle of a lease   |    S   |   SEMI_ANNUAL   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    Q   |   QUARTERLY   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    M   |   MONTHLY   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    N   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    Y   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    A   |   ANNUAL   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBranchCode   |   This 5-character code indicates the branch associated with the contract. You can use the branch as a sort sequence when requesting reports.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBusinessSegment   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBusinessSegmentCode   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseBuyoutQuoteCode   |   This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.   |    NO   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    YES   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCollateralCode   |   This code identifies additional collateral (other than the actual equipment) assigned to a contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCompanyName   |   UATB.LEASING.COMPANY   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractBalanceAmount   |   Contract balance remaining after all payments received are applied to the gross contract. This amount is system-calculated.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractStatus   |   The status of the contract.    |    YES   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    NO   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractStatusDate   |   The date the status was assigned to the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractStatusDesc   |   Contract Status Description   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractTerm   |   The term of the contract in months. If a commencement date was entered, this field is mandatory.The maximum term is 400 months.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseContractTotalReceivedAmount   |   The total contract payment amount received from the beginning of the contract. This is a system-calculated amount.~ ~ Note: If a partial disposition has taken place, this represents the payments on the active portion of the contract only.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerAccountReceivableName   |   The accounts receivable name. This name prints on the customers invoice.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressAttentionName   |   Information entered in this field prints on the invoice, i.e., the name of the person to whom you are mailing the invoice.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressCityName   |   The city for the accounts receivable address.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressCountryCode   |   The country code for the accounts receivable address.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressLine1   |   The first line of the accounts receivable address. This address prints on the customers invoice.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressLine2   |   The second line of the accounts receivable address. This address prints on the customers invoice.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressLine3   |   The third line of the accounts receivable address. This address prints on the customers invoice.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressPostalCode   |   The zip code of the city for the accounts receivable address.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerArAddressStateName   |   The state for accounts receivable address.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerCreditScore   |   A user-defined score given by the leasing company extending credit to the lessee. A credit score is based on certain factors, such as age, marital status, length of employment, etc. Each of these factors is assigned a certain point value with the total being the credit score. Based on this score, the lessee is approved for the credit.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerDoingBusinessName   |   The Customerdoing business name   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerFedSsnId   |   The appropriate identification number.  The ability to modify this field depends on your security settings.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerName   |   The customer name. Use the customer name to create alphabetical listings and locate a name when using Soundex.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseCustomerShortName   |   The Short Name is another name to use when referring to the customer. The Short Name cannot be the same as the Customer Name. This field defaults to the Short Name previously entered for the customer.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseDelinquentStatusCode   |   The delinquent status of the contract. This is a system-calculated field.    |    151   |   PAST_DUE_151_180_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    91   |   PAST_DUE_91_120_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    61   |   PAST_DUE_61_90_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    31   |   PAST_DUE_31_60_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    01   |   PAST_DUE_01_30_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    00   |   NOT_DELINQUENT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    121   |   PAST_DUE_121_150_DAYS   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    181   |   PAST_DUE_181_DAYS_AND_MORE   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseDispositionDate   |   The last date any disposition or inventory occurred on the contract. InfoLease updates this field at the time of a disposition.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseEarlyBuyoutAmount   |   You can enter buyout amounts for the contract in this field. You must first fill in the Date field. The information in this field does not default to the Buyout Quotes module.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseEarlyBuyoutDate   |   You can enter the buyout date for the contract in this field. Entering information here does not default to the Buyout Quotes module.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFacilityScore   |   This score represents the credit score of the deal, not the credit score of the customer.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFdmsDecisionDate   |   UATB.DATE.FDMS.DECISION   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFdmsDecisionInd   |   UATB.FDMS.DECISION   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFinalPaymentDate   |   This field identifies the date the last contract payment is due. This is a system-calculated field using the contract term, the number of advance payments, the number of payments in arrears, the commencement date, and the billing cycle.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFirstPaymentAmount   |   If the first payment is different from the regular scheduled payments, enter the amount here; otherwise, InfoLease defaults the regular contract payment. If no payment is due in the first month, enter zero.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFirstPaymentDate   |   The first payment date. This is a required field. InfoLease calculates the default date based on the commencement date, billing cycle, variable payment schedule, and the payments in arrears code.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFloatingRateIndicator   |   This yes/no field indicates whether this is a floating rate contract.   |    N   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    Y   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseFollowUpDays   |   The number of days after the payment due date that you need to contact the customer. InfoLease uses the number of follow-up days to generate follow-up lists for payment collections. This field is used with the Customer Service Module.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseGeneralLedgerBookingDate   |   Lease General Booking Date   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseGrossAssetAmount   |   The total equipment cost for all assets (not including disposed assets) on the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseGrossFinanceAmount   |   The total amount of finance or interest income (difference between the gross contract amount and the equipment cost). If a commencement date was entered, this field is mandatory.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseGrossPaymentAmount   |   The total amount of payments due on the contract. If a commencement date was entered, this field is mandatory.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseIncomeStartDate   |   The date the income on the contract begins to amortize. This date affects how InfoLease calculates the IRR. This date defaults to the commencement date of the contract; however, in cases where interest free periods exist, you can modify this date.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseInterimRentAmount   |   The amount of interest payments received prior to the commencement of the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseInvoiceCode   |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.   |    N   |   NO_MORE_INVOICING   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    M   |   MANUAL_INVOICING   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    S   |   INVOICE_SUPRESSED   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    D   |   SEPARATED_BY_NOTE_DATE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    C   |   INVOICE_BY_CONTRACT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    A   |   INVOICE_BY_CUSTOMER   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    R   |   RENTALS_SEPARATED   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    B   |   CONTRACT_SEPARATED_INDIVIDUAL_INVOICES   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseInvoiceDueDate   |   The day of the month the payment is due. If you do not enter the invoicing due day, the field defaults to the due day on the Customer Default Data Screen.    |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseLastPaymentDate   |   The date you received the last payment.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseLegalStatus   |   Lease Legal Status   |    015   |   PIF_MERCH_RETURN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    005   |   WRITEOFF   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    007   |   CANCELLED   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    014   |   SIF_MERCH_KEEP_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    004   |   BUYBACK   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    020   |   EQUIP_RETURNED_TO_TASQ   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    013   |   PIF_MERCH_KEEP_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    001   |   ATTORNEY_NEGOTIATION   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    017   |   RECOURSE_PIF   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    012   |   UPGRADE_BUYOUT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    011   |   WRITEOFF_REVERSAL   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    019   |   SIF_MERCH_RETURN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    008   |   WRITEOFF_DEAD   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    016   |   END_OF_LEASE_W_RTN_EQUIP   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseManagerResidualAmount   |   An alternate residual amount that you can select when calculating a buyout quote. Managers residual does not accrue income.This field usually projects an optimistic figure for residual. The Amortizable Residual field usually projects a more conservative figure.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseMerchantId   |   Lease Merchant ID   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseMonthlyPaymentAmount   |   The amount of the contract payment. If this is a variable payment contract, do not enter a contract payment here.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseNetFinanceAmount   |   Net finance is the difference between the gross finance income and the setup income. If Prov Loss Fr Fin = (Y)es, InfoLease also subtracts Provision for Loss from net finance. This amount is system-calculated and you cannot modify it.    |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseNetInvestmentAmount   |   The net investment of the contract. The net investment is the loss the lessor would incur if the lessee stopped payment today.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseNextAgingDate   |   The next date InfoLease will age the contract. You cannot modify this field.    |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseNextChargeDate   |   The next date InfoLease will assess the appropriate late charges during the aging process. You cannot modify this field. InfoLease updates this field whenever you run aging.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseNumberOfAsset   |   The number of active assets associated with the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePaymentInvoicedCount   |   The number of payments billed to the customer.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePaymentOptionCode   |   This field depicts different options of Lease Payment.   |    T   |   TAPE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    N   |   NORMAL_PAY   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    A   |   ASSUMED_PAY   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    P   |   POST_DATED_CHEQUE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    C   |   COUPON   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    U   |   UNDISCOUNTED_PAYMENT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    D   |   DISCOUNTED_PAYMENT   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePaymentPaidToDate   |   Contract payments are paid up to, but not including, this date. This field is based on the due dates of unpaid open items or the next due date (invoicing date plus lead invoicing days) if there are no unpaid open items.    |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePaymentUpfrontAmount   |   The number of beginning payments paid in advance by the customer at contract commencement. Without the Customer Service Module, this field is informational only.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePendingCode   |   This field identifies outstanding information, e.g., paperwork, correspondence, you expect to receive for the contract.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePlatformCode   |   PLATFORM   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePreviousContractNumber   |   Lease Previous Contract Number   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leasePreviousDelinquentStatusCode   |   The previous delinquent status of the contract. If the Delinquent Status Code changes, the previous status is moved to the Previous Delinquent Status field.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseProgramTypeCode   |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.   |    0012   |   VAPP   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0004   |   CROSS_SALES_LARGE_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0019   |   MCA_FDIS_ISO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0099   |   IMS_PORTFOLIO_PURCHASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0016   |   CASH_ADVANCE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0007   |   ATLANTA_TELESALES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0015   |   RSA_RECOURSE_PROJECT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0003   |   CROSS_SALES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0006   |   DBG_RECOURSE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0021   |   MCA_REGIONAL_SALES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0011   |   SAMS_NY_TELESALES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0005   |   PAPERLESS_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0020   |   MCA_FDIS_AGENT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0009   |   RSA_SEVEN_DAY_NO_PPWK   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0022   |   CLOVER   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0018   |   MCA_TELESALES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0008   |   RSA_SEVEN_DAY   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    0001   |   LARGE_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseProvisionForLossAmount   |   The amount set aside to record in the first month for bad debt expense. Enter an amount or default to the system-calculated amount. Gross Contract x Provision for Loss Percentage (lessor file) = Provision for Loss Enter the provision for loss percentage in the Prov for Loss field accessed via the Lessor Parameter Maintenance Screen and the Lessor Default Fields Screen.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseRelationCode   |   Lease Relationship code   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseRenewalStatusCode   |   Lease Renewal status code   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseResidualAmount   |   This field displays once information is entered in residual amount at the asset level. This field cannot be entered or maintained at the contract level. However, a residual change at the asset level affects the gross residual.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseSaleLeasebackInd   |   Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.   |    N   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    Y   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseSecurityDepositAmount   |   This window displays the Security Deposit and the Down Payment fields.The Security Deposit field represents the amount received from the lessee. The Down Payment field represents the amount received from the lessee.    |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseTaxExemptIndicator   |   This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.   |    N   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         |                           |                     |    Y   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseTermDate   |   The date the contract expires.This date is system-generated and you cannot enter or maintain it at the contract level. However, a new date is generated if the Commencement Date, Contract Term, or the Payments In Arrears code is changed.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseTotalRentalPaymentNumber   |   Total number of rental payments made to date.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseTypeCode   |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.   |    RL   |   RENTAL_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    RA   |   REVOLVING_ACCOUNT   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    TL   |   TRUE_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    LL   |   LEVERAGED_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    LP   |   LEASE_PURCHASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    LN   |   TERM_LOAN   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    OL   |   OPERATING_LEASE   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    CS   |   CONDITIONAL_SALE   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseVariablePaymentAmount   |   Variable Payment Amount of the lease   |       |      |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseVariablePaymentIndicator   |   This yes/no field indicates whether this contract has a variable payment schedule.    |    Y   |   YES   |         Available      |      Optional      |      Allowed       |         NA         |
|         |           |                    |    N   |   NO   |         Available      |      Optional      |      Allowed       |         NA         |
|         | leaseWriteOffAmount   |   The income used to offset the initial expense associated with a new lease. The amount is calculated by multiplying the setup income percentage on the Lessor Parameter File by the gross finance income.   |       |      |         Available      |      Optional      |      Allowed       |         NA         |

<!-- type: tab-end -->
