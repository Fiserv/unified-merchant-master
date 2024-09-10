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

|   Product Code   | Attribute         | Description               | Values        | Value Descriptio                  |
|:---------------------|:---------------------|:--------------------------|:--------------|:----------------------------------|
| VASCASHADV   | activeDate   |   Cash Advance Activation Date   |       |      |   
|                       | advanceAmount   |   Cash Advance Amount    |               |                                   | 
|                       | bookingDate   |   Cash advance Booking Date    |               |                                   | 
|                       | branchCode   |   Cash Advance Branch Code    |               |                                   | 
|                       | businessSegment   |   Cash Advance Business Segment    |               |                                   | 
|                       | cashAdvanceBankSequenceNumber   |   Cash Advance Bank Sequence Number added to Merchant Bank Account    |               |                                   | 
|                       | contractTerm   |   Cash Advance Contract Term    |               |                                   | 
|                       | dailyWithholdPercentage   |   Cash Advance Daily Withhold Percentage    |               |                                   | 
|                       | estPaybackPeriod   |   Cash Advance EST Payback Period    |               |                                   | 
|                       | finalPaymentDate   |   Cash Advance Final Payment Date    |               |                                   | 
|                       | firstPaymentDate   |   Cash Advance First Payment Date    |               |                                   | 
|                       | fundingDate   |   Cash Advance Funding Date    |               |                                   | 
|                       | grossIncome   |   Cash Advance Gross Income    |               |                                   | 
|                       | invDueDate   |   Cash Advance Invoice Due Date    |               |                                   | 
|                       | lastPaymentDate   |   Cash Advance Last Payment Date    |               |                                   | 
|                       | legalStatus   |   Lease Legal Status    |       013        |                 PIF_MERCH_KEEP_EQUIP                  | 
|                       |    |   Lease Legal Status    |       017        |                 RECOURSE_PIF                  | 
|                       |    |   Lease Legal Status    |       011        |                 WRITEOFF_REVERSAL                  | 
|                       |    |   Lease Legal Status    |       016        |                 END_OF_LEASE_W_RTN_EQUIP                  | 
|                       |    |   Lease Legal Status    |       008        |                 WRITEOFF_DEAD                  | 
|                       |    |   Lease Legal Status    |       015        |                 PIF_MERCH_RETURN_EQUIP                  | 
|                       |    |   Lease Legal Status    |       005        |                 WRITEOFF                  | 
|                       |    |   Lease Legal Status    |       007        |                 CANCELLED                  | 
|                       |    |   Lease Legal Status    |       014        |                 SIF_MERCH_KEEP_EQUIP                  | 
|                       |    |   Lease Legal Status    |       004        |                 BUYBACK                  | 
|                       |    |   Lease Legal Status    |       020        |                 EQUIP_RETURNED_TO_TASQ                  | 
|                       |    |   Lease Legal Status    |       001        |                 ATTORNEY_NEGOTIATION                  | 
|                       |    |   Lease Legal Status    |       019        |                 SIF_MERCH_RETURN_EQUIP                  | 
|                       |    |   Lease Legal Status    |       012        |                 UPGRADE_BUYOUT                  | 
|                       | netIncome   |   Cash Advance Net Income    |               |                                   | 
|                       | payBackAmount   |   Cash Advance Pay Back Amount    |               |                                   | 
|                       | priorCashAdvanceId   |   Prior Cash Advance ID    |               |                                   | 
|                       | receivedAmount   |   Cash Advance Received Amount    |               |                                   | 
|                       | relationshipCode   |   Cash Advance Relationship Code    |               |                                   | 
|                       | remainingAmount   |   Cash Advance Remaining Amount    |               |                                   | 
|                       | terminationDate   |   Cash Advance Termination Date    |               |                                   | 


<!-- type: tab -->


### lease

---

tags: [lease]

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |

---

|   Product Code       | Attribute            | Description                    | Values        | Value Descriptio                  |
|:---------------------|:---------------------|:-------------------------------|:--------------|:----------------------------------|
| VASLEASE| leaseActivationDate   |   The activation date of the contract. Entering this date activates the contract. InfoLease uses this date along with the Contract Term and the Payments in Arrears Code to determine the termination date of the contract.    |               |                                   | 
|                       | leaseAdditionalMid   |   This will be the Mainframe MID for ISOs that have a 15 digit MID that contains a zero added to the infolease record for cash advance    |               |                                   | 
|                       | leaseAmortizableResidualAmount   |   The calculation for amortizable residual is as follows.~ ~ Gross Residual~ - Residual Writedown ~ - Discount Residual~ - Present Value Amount~ = Amount of Residual Amortized~ ~ This field usually projects a conservative amount for residual. The Managers Residual field generally projects a more optimistic figure.    |               |                                   | 
|                       | leaseApproverSignatoryName   |   The name of the person who signs the contract. This field defaults to the name entered in the Contact Name field.    |               |                                   | 
|                       | leaseBankSequenceNumber   |   Lease Bank Sequence Number added to Merchant Bank Account    |               |                                   | 
|                       | leaseBillingCycle   |   Billing Cycle of a lease    |       S        |                 SEMI_ANNUAL                  | 
|                       |    |   Billing Cycle of a lease    |       Q        |                 QUARTERLY                  | 
|                       |    |   Billing Cycle of a lease    |       M        |                 MONTHLY                  | 
|                       |    |   Billing Cycle of a lease    |       N        |                 NO                  | 
|                       |    |   Billing Cycle of a lease    |       Y        |                 YES                  | 
|                       |    |   Billing Cycle of a lease    |       A        |                 ANNUAL                  | 
|                       | leaseBranchCode   |   This 5-character code indicates the branch associated with the contract. You can use the branch as a sort sequence when requesting reports.    |               |                                   | 
|                       | leaseBusinessSegment   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.    |               |                                   | 
|                       | leaseBusinessSegmentCode   |   This 6-digit table code indicates the relationships business segment. If you modify the default, InfoLease verifies the code entered is valid for the relationship.    |               |                                   | 
|                       | leaseBuyoutQuoteCode   |   This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.    |       NO        |                 NO                  | 
|                       |    |   This yes/no field indicates whether the lessor has access to the Buyout Quotes Screen for this contract. Refer to the Buyout Quotes Module documentation.    |       YES        |                 YES                  | 
|                       | leaseCollateralCode   |   This code identifies additional collateral (other than the actual equipment) assigned to a contract.    |               |                                   | 
|                       | leaseCompanyName   |   UATB.LEASING.COMPANY    |               |                                   | 
|                       | leaseContractBalanceAmount   |   Contract balance remaining after all payments received are applied to the gross contract. This amount is system-calculated.    |               |                                   | 
|                       | leaseContractStatus   |   The status of the contract.     |       YES        |                 YES                  | 
|                       |    |   The status of the contract.     |       NO        |                 NO                  | 
|                       | leaseContractStatusDate   |   The date the status was assigned to the contract.    |               |                                   | 
|                       | leaseContractStatusDesc   |   Contract Status Description    |               |                                   | 
|                       | leaseContractTerm   |   The term of the contract in months. If a commencement date was entered, this field is mandatory.The maximum term is 400 months.    |               |                                   | 
|                       | leaseContractTotalReceivedAmount   |   The total contract payment amount received from the beginning of the contract. This is a system-calculated amount.~ ~ Note: If a partial disposition has taken place, this represents the payments on the active portion of the contract only.    |               |                                   | 
|                       | leaseCustomerAccountReceivableName   |   The accounts receivable name. This name prints on the customers invoice.    |               |                                   | 
|                       | leaseCustomerArAddressAttentionName   |   Information entered in this field prints on the invoice, i.e., the name of the person to whom you are mailing the invoice.    |               |                                   | 
|                       | leaseCustomerArAddressCityName   |   The city for the accounts receivable address.    |               |                                   | 
|                       | leaseCustomerArAddressCountryCode   |   The country code for the accounts receivable address.    |               |                                   | 
|                       | leaseCustomerArAddressLine1   |   The first line of the accounts receivable address. This address prints on the customers invoice.    |               |                                   | 
|                       | leaseCustomerArAddressLine2   |   The second line of the accounts receivable address. This address prints on the customers invoice.    |               |                                   | 
|                       | leaseCustomerArAddressLine3   |   The third line of the accounts receivable address. This address prints on the customers invoice.    |               |                                   | 
|                       | leaseCustomerArAddressPostalCode   |   The zip code of the city for the accounts receivable address.    |               |                                   | 
|                       | leaseCustomerArAddressStateName   |   The state for accounts receivable address.    |               |                                   | 
|                       | leaseCustomerCreditScore   |   A user-defined score given by the leasing company extending credit to the lessee. A credit score is based on certain factors, such as age, marital status, length of employment, etc. Each of these factors is assigned a certain point value with the total being the credit score. Based on this score, the lessee is approved for the credit.    |               |                                   | 
|                       | leaseCustomerDoingBusinessName   |   The Customerdoing business name    |               |                                   | 
|                       | leaseCustomerFedSsnId   |   The appropriate identification number.  The ability to modify this field depends on your security settings.    |               |                                   | 
|                       | leaseCustomerName   |   The customer name. Use the customer name to create alphabetical listings and locate a name when using Soundex.    |               |                                   | 
|                       | leaseCustomerShortName   |   The Short Name is another name to use when referring to the customer. The Short Name cannot be the same as the Customer Name. This field defaults to the Short Name previously entered for the customer.    |               |                                   | 
|                       | leaseDelinquentStatusCode   |   The delinquent status of the contract. This is a system-calculated field.     |       151        |                 PAST_DUE_151_180_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       91        |                 PAST_DUE_91_120_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       61        |                 PAST_DUE_61_90_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       31        |                 PAST_DUE_31_60_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       01        |                 PAST_DUE_01_30_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       00        |                 NOT_DELINQUENT                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       121        |                 PAST_DUE_121_150_DAYS                  | 
|                       |    |   The delinquent status of the contract. This is a system-calculated field.     |       181        |                 PAST_DUE_181_DAYS_AND_MORE                  | 
|                       | leaseDispositionDate   |   The last date any disposition or inventory occurred on the contract. InfoLease updates this field at the time of a disposition.    |               |                                   | 
|                       | leaseEarlyBuyoutAmount   |   You can enter buyout amounts for the contract in this field. You must first fill in the Date field. The information in this field does not default to the Buyout Quotes module.    |               |                                   | 
|                       | leaseEarlyBuyoutDate   |   You can enter the buyout date for the contract in this field. Entering information here does not default to the Buyout Quotes module.    |               |                                   | 
|                       | leaseFacilityScore   |   This score represents the credit score of the deal, not the credit score of the customer.    |               |                                   | 
|                       | leaseFdmsDecisionDate   |   UATB.DATE.FDMS.DECISION    |               |                                   | 
|                       | leaseFdmsDecisionInd   |   UATB.FDMS.DECISION    |               |                                   | 
|                       | leaseFinalPaymentDate   |   This field identifies the date the last contract payment is due. This is a system-calculated field using the contract term, the number of advance payments, the number of payments in arrears, the commencement date, and the billing cycle.    |               |                                   | 
|                       | leaseFirstPaymentAmount   |   If the first payment is different from the regular scheduled payments, enter the amount here; otherwise, InfoLease defaults the regular contract payment. If no payment is due in the first month, enter zero.    |               |                                   | 
|                       | leaseFirstPaymentDate   |   The first payment date. This is a required field. InfoLease calculates the default date based on the commencement date, billing cycle, variable payment schedule, and the payments in arrears code.    |               |                                   | 
|                       | leaseFloatingRateIndicator   |   This yes/no field indicates whether this is a floating rate contract.    |       N        |                 NO                  | 
|                       |    |   This yes/no field indicates whether this is a floating rate contract.    |       Y        |                 YES                  | 
|                       | leaseFollowUpDays   |   The number of days after the payment due date that you need to contact the customer. InfoLease uses the number of follow-up days to generate follow-up lists for payment collections. This field is used with the Customer Service Module.    |               |                                   | 
|                       | leaseGeneralLedgerBookingDate   |   Lease General Booking Date    |               |                                   | 
|                       | leaseGrossAssetAmount   |   The total equipment cost for all assets (not including disposed assets) on the contract.    |               |                                   | 
|                       | leaseGrossFinanceAmount   |   The total amount of finance or interest income (difference between the gross contract amount and the equipment cost). If a commencement date was entered, this field is mandatory.    |               |                                   | 
|                       | leaseGrossPaymentAmount   |   The total amount of payments due on the contract. If a commencement date was entered, this field is mandatory.    |               |                                   | 
|                       | leaseIncomeStartDate   |   The date the income on the contract begins to amortize. This date affects how InfoLease calculates the IRR. This date defaults to the commencement date of the contract; however, in cases where interest free periods exist, you can modify this date.    |               |                                   | 
|                       | leaseInterimRentAmount   |   The amount of interest payments received prior to the commencement of the contract.    |               |                                   | 
|                       | leaseInvoiceCode   |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       N        |                 NO_MORE_INVOICING                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       M        |                 MANUAL_INVOICING                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       S        |                 INVOICE_SUPRESSED                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       D        |                 SEPARATED_BY_NOTE_DATE                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       C        |                 INVOICE_BY_CONTRACT                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       A        |                 INVOICE_BY_CUSTOMER                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       R        |                 RENTALS_SEPARATED                  | 
|                       |    |   The method InfoLease uses to create invoices. A value defaults to this field from the Invoice Code field on the Lessor Default Fields Screen.  Use this invoice code when selling a stream of contract payments.    |       B        |                 CONTRACT_SEPARATED_INDIVIDUAL_INVOICES                  | 
|                       | leaseInvoiceDueDate   |   The day of the month the payment is due. If you do not enter the invoicing due day, the field defaults to the due day on the Customer Default Data Screen.     |               |                                   | 
|                       | leaseLastPaymentDate   |   The date you received the last payment.    |               |                                   | 
|                       | leaseLegalStatus   |   Lease Legal Status    |       015        |                 PIF_MERCH_RETURN_EQUIP                  | 
|                       |    |   Lease Legal Status    |       005        |                 WRITEOFF                  | 
|                       |    |   Lease Legal Status    |       007        |                 CANCELLED                  | 
|                       |    |   Lease Legal Status    |       014        |                 SIF_MERCH_KEEP_EQUIP                  | 
|                       |    |   Lease Legal Status    |       004        |                 BUYBACK                  | 
|                       |    |   Lease Legal Status    |       020        |                 EQUIP_RETURNED_TO_TASQ                  | 
|                       |    |   Lease Legal Status    |       013        |                 PIF_MERCH_KEEP_EQUIP                  | 
|                       |    |   Lease Legal Status    |       001        |                 ATTORNEY_NEGOTIATION                  | 
|                       |    |   Lease Legal Status    |       017        |                 RECOURSE_PIF                  | 
|                       |    |   Lease Legal Status    |       012        |                 UPGRADE_BUYOUT                  | 
|                       |    |   Lease Legal Status    |       011        |                 WRITEOFF_REVERSAL                  | 
|                       |    |   Lease Legal Status    |       019        |                 SIF_MERCH_RETURN_EQUIP                  | 
|                       |    |   Lease Legal Status    |       008        |                 WRITEOFF_DEAD                  | 
|                       |    |   Lease Legal Status    |       016        |                 END_OF_LEASE_W_RTN_EQUIP                  | 
|                       | leaseManagerResidualAmount   |   An alternate residual amount that you can select when calculating a buyout quote. Managers residual does not accrue income.This field usually projects an optimistic figure for residual. The Amortizable Residual field usually projects a more conservative figure.    |               |                                   | 
|                       | leaseMerchantId   |   Lease Merchant ID    |               |                                   | 
|                       | leaseMonthlyPaymentAmount   |   The amount of the contract payment. If this is a variable payment contract, do not enter a contract payment here.    |               |                                   | 
|                       | leaseNetFinanceAmount   |   Net finance is the difference between the gross finance income and the setup income. If Prov Loss Fr Fin = (Y)es, InfoLease also subtracts Provision for Loss from net finance. This amount is system-calculated and you cannot modify it.     |               |                                   | 
|                       | leaseNetInvestmentAmount   |   The net investment of the contract. The net investment is the loss the lessor would incur if the lessee stopped payment today.    |               |                                   | 
|                       | leaseNextAgingDate   |   The next date InfoLease will age the contract. You cannot modify this field.     |               |                                   | 
|                       | leaseNextChargeDate   |   The next date InfoLease will assess the appropriate late charges during the aging process. You cannot modify this field. InfoLease updates this field whenever you run aging.    |               |                                   | 
|                       | leaseNumberOfAsset   |   The number of active assets associated with the contract.    |               |                                   | 
|                       | leasePaymentInvoicedCount   |   The number of payments billed to the customer.    |               |                                   | 
|                       | leasePaymentOptionCode   |   This field depicts different options of Lease Payment.    |       T        |                 TAPE                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       N        |                 NORMAL_PAY                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       A        |                 ASSUMED_PAY                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       P        |                 POST_DATED_CHEQUE                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       C        |                 COUPON                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       U        |                 UNDISCOUNTED_PAYMENT                  | 
|                       |    |   This field depicts different options of Lease Payment.    |       D        |                 DISCOUNTED_PAYMENT                  | 
|                       | leasePaymentPaidToDate   |   Contract payments are paid up to, but not including, this date. This field is based on the due dates of unpaid open items or the next due date (invoicing date plus lead invoicing days) if there are no unpaid open items.     |               |                                   | 
|                       | leasePaymentUpfrontAmount   |   The number of beginning payments paid in advance by the customer at contract commencement. Without the Customer Service Module, this field is informational only.    |               |                                   | 
|                       | leasePendingCode   |   This field identifies outstanding information, e.g., paperwork, correspondence, you expect to receive for the contract.    |               |                                   | 
|                       | leasePlatformCode   |   PLATFORM    |               |                                   | 
|                       | leasePreviousContractNumber   |   Lease Previous Contract Number    |               |                                   | 
|                       | leasePreviousDelinquentStatusCode   |   The previous delinquent status of the contract. If the Delinquent Status Code changes, the previous status is moved to the Previous Delinquent Status field.    |               |                                   | 
|                       | leaseProgramTypeCode   |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0012        |                 VAPP                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0004        |                 CROSS_SALES_LARGE_LEASE                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0019        |                 MCA_FDIS_ISO                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0099        |                 IMS_PORTFOLIO_PURCHASE                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0016        |                 CASH_ADVANCE                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0007        |                 ATLANTA_TELESALES                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0015        |                 RSA_RECOURSE_PROJECT                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0003        |                 CROSS_SALES                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0006        |                 DBG_RECOURSE                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0021        |                 MCA_REGIONAL_SALES                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0011        |                 SAMS_NY_TELESALES                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0005        |                 PAPERLESS_LEASE                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0020        |                 MCA_FDIS_AGENT                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0009        |                 RSA_SEVEN_DAY_NO_PPWK                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0022        |                 CLOVER                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0018        |                 MCA_TELESALES                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0008        |                 RSA_SEVEN_DAY                  | 
|                       |    |   A 2-digit program type distinguishing the different types of credit applications taken by your company. The program type also determines the Document Checklist to assign to the credit application.    |       0001        |                 LARGE_LEASE                  | 
|                       | leaseProvisionForLossAmount   |   The amount set aside to record in the first month for bad debt expense. Enter an amount or default to the system-calculated amount. Gross Contract x Provision for Loss Percentage (lessor file) = Provision for Loss Enter the provision for loss percentage in the Prov for Loss field accessed via the Lessor Parameter Maintenance Screen and the Lessor Default Fields Screen.    |               |                                   | 
|                       | leaseRelationCode   |   Lease Relationship code    |               |                                   | 
|                       | leaseRenewalStatusCode   |   Lease Renewal status code    |               |                                   | 
|                       | leaseResidualAmount   |   This field displays once information is entered in residual amount at the asset level. This field cannot be entered or maintained at the contract level. However, a residual change at the asset level affects the gross residual.    |               |                                   | 
|                       | leaseSaleLeasebackInd   |   Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.    |       N        |                 NO                  | 
|                       |    |   Enter yes if the contract is a sale/leaseback. A sale/leaseback agreement involves two separate transactions: the sale of the asset to the prospective lessor and the subsequent lease of the asset to the original owner. This field is informational only.    |       Y        |                 YES                  | 
|                       | leaseSecurityDepositAmount   |   This window displays the Security Deposit and the Down Payment fields.The Security Deposit field represents the amount received from the lessee. The Down Payment field represents the amount received from the lessee.     |               |                                   | 
|                       | leaseTaxExemptIndicator   |   This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.    |       N        |                 NO                  | 
|                       |    |   This field indicates whether the contract has interest income that is exempt from federal income tax. The default is (N)o.    |       Y        |                 YES                  | 
|                       | leaseTermDate   |   The date the contract expires.This date is system-generated and you cannot enter or maintain it at the contract level. However, a new date is generated if the Commencement Date, Contract Term, or the Payments In Arrears code is changed.    |               |                                   | 
|                       | leaseTotalRentalPaymentNumber   |   Total number of rental payments made to date.    |               |                                   | 
|                       | leaseTypeCode   |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       RL        |                 RENTAL_LEASE                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       RA        |                 REVOLVING_ACCOUNT                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       TL        |                 TRUE_LEASE                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       LL        |                 LEVERAGED_LEASE                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       LP        |                 LEASE_PURCHASE                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       LN        |                 TERM_LOAN                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       OL        |                 OPERATING_LEASE                  | 
|                       |    |   A 2-digit contract type. Once you enter this code, you cannot change it without deleting and re-entering the contract.    |       CS        |                 CONDITIONAL_SALE                  | 
|                       | leaseVariablePaymentAmount   |   Variable Payment Amount of the lease    |               |                                   | 
|                       | leaseVariablePaymentIndicator   |   This yes/no field indicates whether this contract has a variable payment schedule.     |       Y        |                 YES                  | 
|                       |    |   This yes/no field indicates whether this contract has a variable payment schedule.     |       N        |                 NO                  | 
|                       | leaseWriteOffAmount   |   The income used to offset the initial expense associated with a new lease. The amount is calculated by multiplying the setup income percentage on the Lessor Parameter File by the gross finance income.    |               |                                   | 


<!-- type: tab -->


### serviceAttr

---

tags: [serviceAttr]

* **List of Attributes**: Applicable for UMM, North and GMA
  
  | Inquiry         |   Create      |    Update  |  Delete  |
  |:---------------:|:-------------:|:----------:|:--------:|
  |    Available    |   Optional    |  Allowed   |  NA      |

---

|   Product Code       | Attribute            | Description                    | Values        | Value Descriptio                  |
|:---------------------|:---------------------|:-------------------------------|:--------------|:----------------------------------|
| VASTRNSARM| encryptExceptionKeyId   |   Encryption exception key ID    |               |                                   | 
|                       | encryptServiceLevelCode   |   Encryption security level code    |       00        |                 NONE                  | 
|                       |    |   Encryption security level code    |       02        |                 ENCRP_ONLY                  | 
|                       |    |   Encryption security level code    |       03        |                 TOKEN_ONLY                  | 
|                       |    |   Encryption security level code    |       01        |                 BOTH                  | 
|                       | encryptTokenCode   |   Encryption token type code    |               |                                   | 
|                       | encryptTokenHierarchyCode   |   Encryption multipay token hierarchy level code    |       04        |                 AGENT                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       03        |                 CORP                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       06        |                 BUSINESS                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       01        |                 OUTLET                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       02        |                 CHAIN                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       00        |                 NONE                  | 
|                       |    |   Encryption multipay token hierarchy level code    |       05        |                 BANK                  | 
|                       | encryptTokenOverrideIndicator   |   Encryption multipay token override indicator    |       N        |                 NO                  | 
|                       |    |   Encryption multipay token override indicator    |       Y        |                 YES                  | 
|                       | encryptTypeCode   |   Encryption type code    |       05        |                 INGENICO_ONGUARD                  | 
|                       |    |   Encryption type code    |       01        |                 RSA_PKI                  | 
|                       |    |   Encryption type code    |       04        |                 3DES                  | 
|                       |    |   Encryption type code    |       06        |                 AES_DUKPT                  | 
|                       |    |   Encryption type code    |       03        |                 VERIFONE_PROTECT_WITH_SP                  | 
|                       |    |   Encryption type code    |       00        |                 NONE                  | 
|                       |    |   Encryption type code    |       02        |                 VERIFONE_PROTECT                  | 
|                       | vspBrand   |   VSP brand indicates the TransArmor VeriFone VSP Brand    |               |                                   | 
|                       | vspDomain   |   VSP domain Indicates the Corporate Identifier for TransArmor VeriFone Edition    |               |                                   | 
| VASTAP2PE| 3des   |   3DES for Transarmor    |       P        |                 PENDING                  | 
|                       |    |   3DES for Transarmor    |       Y        |                 YES                  | 
|                       |    |   3DES for Transarmor    |       03        |                 BLANK                  | 
|                       |    |   3DES for Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   3DES for Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   3DES for Transarmor    |       A        |                 ACTIVE                  | 
|                       |    |   3DES for Transarmor    |       01        |                 FDMS_POS                  | 
|                       |    |   3DES for Transarmor    |       N        |                 NO                  | 
|                       |    |   3DES for Transarmor    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   3DES for Transarmor    |       C        |                 CANCEL                  | 

| VASADVINS| advInsightBillingEffectiveDate   |   Billing Effective Date for Advertising Insights    |               |                                   | 
|                       | advInsightOfferingType   |   Offering Type for Advertising Insights    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Advertising Insights    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Advertising Insights    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Advertising Insights    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Advertising Insights    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Advertising Insights    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Advertising Insights    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Advertising Insights    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Advertising Insights    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Advertising Insights    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Advertising Insights    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Advertising Insights    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Advertising Insights    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Advertising Insights    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Advertising Insights    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Advertising Insights    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Advertising Insights    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Advertising Insights    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Advertising Insights    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Advertising Insights    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Advertising Insights    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Advertising Insights    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Advertising Insights    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Advertising Insights    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Advertising Insights    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Advertising Insights    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Advertising Insights    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Advertising Insights    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Advertising Insights    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Advertising Insights    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Advertising Insights    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Advertising Insights    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Advertising Insights    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Advertising Insights    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Advertising Insights    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Advertising Insights    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Advertising Insights    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Advertising Insights    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Advertising Insights    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Advertising Insights    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Advertising Insights    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Advertising Insights    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Advertising Insights    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Advertising Insights    |       C58        |                 CASH_2_ATM                  | 
|                       | advInsightStatus   |   Program Status for Advertising Insights    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Advertising Insights    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Advertising Insights    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Advertising Insights    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Advertising Insights    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Advertising Insights    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Advertising Insights    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Advertising Insights    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Advertising Insights    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Advertising Insights    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Advertising Insights    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Advertising Insights    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Advertising Insights    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Advertising Insights    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Advertising Insights    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Advertising Insights    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Advertising Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Advertising Insights    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Advertising Insights    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Advertising Insights    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Advertising Insights    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Advertising Insights    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Advertising Insights    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Advertising Insights    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Advertising Insights    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Advertising Insights    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Advertising Insights    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Advertising Insights    |       N        |                 NEW_APPLICATION                  | 

| VASTAP2PE| aesDukpt   |   AES DUKPT for Transarmor    |       A        |                 ANNUAL                  | 
|                       |    |   AES DUKPT for Transarmor    |       I        |                 INITIATED                  | 
|                       |    |   AES DUKPT for Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   AES DUKPT for Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   AES DUKPT for Transarmor    |       F        |                 FAILED                  | 
|                       |    |   AES DUKPT for Transarmor    |       O        |                 OPTED_OUT                  | 
|                       |    |   AES DUKPT for Transarmor    |       P        |                 PENDING                  | 
|                       |    |   AES DUKPT for Transarmor    |       M        |                 MONTHLY                  | 
|                       |    |   AES DUKPT for Transarmor    |       A        |                 PROVISIONED                  | 

| VASNTWKTKN| americanExpress   |   American Express Network Tokens    |       N        |                 NOT_CHECKED                  | 
|                       |    |   American Express Network Tokens    |       Y        |                 YES                  | 
|                       |    |   American Express Network Tokens    |       N        |                 NO                  | 
|                       |    |   American Express Network Tokens    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   American Express Network Tokens    |       03        |                 BLANK                  | 
|                       |    |   American Express Network Tokens    |       Y        |                 CHECKED                  | 
|                       |    |   American Express Network Tokens    |       C        |                 CANCEL                  | 
|                       |    |   American Express Network Tokens    |       01        |                 FDMS_POS                  | 
|                       |    |   American Express Network Tokens    |       A        |                 ACTIVE                  | 
|                       |    |   American Express Network Tokens    |       P        |                 PENDING                  | 

| VASMSTTIST| analyticsProductType   |   Product Offering That A Merchant Is Enrolled To Use.    |       03        |                 MSI_APP                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       Y        |                 YES                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       X        |                 CARDX                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       K        |                 KIBO                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       T        |                 TEMPUS                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       V        |                 VALUELINK                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       D        |                 DELETE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       C        |                 CENPOS                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       C        |                 CLOVER                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       S        |                 SHOPIFY                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       N        |                 NO                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       A        |                 ADD                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       O        |                 OTHER                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       M        |                 MAGENTO2                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       V        |                 MIVA                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       3        |                 3DCART                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       C        |                 CANCEL                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       A        |                 ACTIVE                  | 
|                       |    |   Product Offering That A Merchant Is Enrolled To Use.    |       Y        |                 CHECKED                  | 

| VASWELLSP| bobPreference   |   Wells Bob Preference Field    |       C        |                 CLOVER                  | 
|                       |    |   Wells Bob Preference Field    |       C        |                 CANCEL                  | 
|                       |    |   Wells Bob Preference Field    |       Y        |                 CHECKED                  | 
|                       |    |   Wells Bob Preference Field    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Wells Bob Preference Field    |       V        |                 MIVA                  | 
|                       |    |   Wells Bob Preference Field    |       T        |                 TEMPUS                  | 
|                       |    |   Wells Bob Preference Field    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Wells Bob Preference Field    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Wells Bob Preference Field    |       A        |                 ACTIVE                  | 
|                       |    |   Wells Bob Preference Field    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Wells Bob Preference Field    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Wells Bob Preference Field    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Wells Bob Preference Field    |       3        |                 3DCART                  | 
|                       |    |   Wells Bob Preference Field    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Wells Bob Preference Field    |       D        |                 DELETE                  | 
|                       |    |   Wells Bob Preference Field    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Wells Bob Preference Field    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Wells Bob Preference Field    |       N        |                 NO                  | 
|                       |    |   Wells Bob Preference Field    |       V        |                 VALUELINK                  | 
|                       |    |   Wells Bob Preference Field    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Wells Bob Preference Field    |       S        |                 SHOPIFY                  | 
|                       |    |   Wells Bob Preference Field    |       Y        |                 YES                  | 
|                       |    |   Wells Bob Preference Field    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Wells Bob Preference Field    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Wells Bob Preference Field    |       K        |                 KIBO                  | 
|                       |    |   Wells Bob Preference Field    |       X        |                 CARDX                  | 
|                       |    |   Wells Bob Preference Field    |       O        |                 OTHER                  | 
|                       |    |   Wells Bob Preference Field    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Wells Bob Preference Field    |       M        |                 MAGENTO2                  | 
|                       |    |   Wells Bob Preference Field    |       03        |                 MSI_APP                  | 
|                       |    |   Wells Bob Preference Field    |       C        |                 CENPOS                  | 
|                       |    |   Wells Bob Preference Field    |       A        |                 ADD                  | 
|                       |    |   Wells Bob Preference Field    |       S        |                 SNAPPAY_CARDX                  | 

| VASBPMOB| bpMobiletermType   |   Mobile Terminal Type for BP Mobile    |       D        |                 DELETE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       C        |                 CENPOS                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       03        |                 MSI_APP                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       K        |                 KIBO                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       N        |                 NO                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       S        |                 SHOPIFY                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       T        |                 TEMPUS                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       3        |                 3DCART                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       V        |                 MIVA                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       X        |                 CARDX                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       O        |                 OTHER                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       A        |                 ACTIVE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       M        |                 MAGENTO2                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       Y        |                 YES                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       A        |                 ADD                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       C        |                 CANCEL                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       V        |                 VALUELINK                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       C        |                 CLOVER                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Mobile Terminal Type for BP Mobile    |       B        |                 BIGCOMMERCE                  | 

| VASWELLSP| ceoLPreference   |   Wells Ceo Preference Field    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Wells Ceo Preference Field    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Wells Ceo Preference Field    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Wells Ceo Preference Field    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Wells Ceo Preference Field    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Wells Ceo Preference Field    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Wells Ceo Preference Field    |       03        |                 PAYEEZY                  | 
|                       |    |   Wells Ceo Preference Field    |       00        |                 NONE                  | 
|                       |    |   Wells Ceo Preference Field    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Wells Ceo Preference Field    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Wells Ceo Preference Field    |       1        |                 OPTED_OUT                  | 
|                       |    |   Wells Ceo Preference Field    |       Y        |                 CHECKED                  | 
|                       |    |   Wells Ceo Preference Field    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Wells Ceo Preference Field    |       02        |                 IPG                  | 
|                       |    |   Wells Ceo Preference Field    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Wells Ceo Preference Field    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Wells Ceo Preference Field    |       01        |                 FIRST_API                  | 
|                       |    |   Wells Ceo Preference Field    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Wells Ceo Preference Field    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Wells Ceo Preference Field    |       04        |                 UCOMM                  | 
|                       |    |   Wells Ceo Preference Field    |       N        |                 NO                  | 
|                       |    |   Wells Ceo Preference Field    |       Y        |                 YES                  | 
|                       |    |   Wells Ceo Preference Field    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Wells Ceo Preference Field    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Wells Ceo Preference Field    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Wells Ceo Preference Field    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Wells Ceo Preference Field    |       B        |                 BREAD                  | 

| VASGBSPOSINS| channel   |   Channel for GBS POS Installments    |       C        |                 CBS                  | 
|                       |    |   Channel for GBS POS Installments    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Channel for GBS POS Installments    |       A        |                 AGENT_ISV                  | 
|                       |    |   Channel for GBS POS Installments    |       Y        |                 YES                  | 
|                       |    |   Channel for GBS POS Installments    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Channel for GBS POS Installments    |       Y        |                 CHECKED                  | 
|                       |    |   Channel for GBS POS Installments    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Channel for GBS POS Installments    |       N        |                 NO                  | 
|                       |    |   Channel for GBS POS Installments    |       CM        |                 CMM                  | 

| VASBPMOB| chargebackInd   |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       A        |                 ACTIVE                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       Y        |                 YES                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       C        |                 CANCEL                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       01        |                 FDMS_POS                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       03        |                 BLANK                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       N        |                 NO                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       P        |                 PENDING                  | 
|                       |    |   OEMV Chargeback Writeoff Indicator for BP Mobile    |       N        |                 NOT_CHECKED                  | 

| VASMSTTIST| cloverInsightsEmail   |   User Provided Clover Insights Email    |       Y        |                 YES                  | 
|                       |    |   User Provided Clover Insights Email    |       01        |                 FDMS_POS                  | 
|                       |    |   User Provided Clover Insights Email    |       N        |                 NO                  | 
|                       |    |   User Provided Clover Insights Email    |       N        |                 NOT_CHECKED                  | 
|                       |    |   User Provided Clover Insights Email    |       Y        |                 CHECKED                  | 
|                       |    |   User Provided Clover Insights Email    |       A        |                 ACTIVE                  | 
|                       |    |   User Provided Clover Insights Email    |       03        |                 BLANK                  | 
|                       |    |   User Provided Clover Insights Email    |       C        |                 CANCEL                  | 
|                       |    |   User Provided Clover Insights Email    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   User Provided Clover Insights Email    |       P        |                 PENDING                  | 

| VASSAMSPLS| clubNum   |   SAMS Club - Club Number    |       O        |                 OTHER                  | 
|                       |    |   SAMS Club - Club Number    |       Y        |                 CHECKED                  | 
|                       |    |   SAMS Club - Club Number    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   SAMS Club - Club Number    |       K        |                 KIBO                  | 
|                       |    |   SAMS Club - Club Number    |       03        |                 MSI_APP                  | 
|                       |    |   SAMS Club - Club Number    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   SAMS Club - Club Number    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   SAMS Club - Club Number    |       C        |                 CENPOS                  | 
|                       |    |   SAMS Club - Club Number    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   SAMS Club - Club Number    |       M        |                 MAGENTO2                  | 
|                       |    |   SAMS Club - Club Number    |       N        |                 NO                  | 
|                       |    |   SAMS Club - Club Number    |       S        |                 SHOPIFY                  | 
|                       |    |   SAMS Club - Club Number    |       Y        |                 YES                  | 
|                       |    |   SAMS Club - Club Number    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   SAMS Club - Club Number    |       V        |                 VALUELINK                  | 
|                       |    |   SAMS Club - Club Number    |       D        |                 DELETE                  | 
|                       |    |   SAMS Club - Club Number    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   SAMS Club - Club Number    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   SAMS Club - Club Number    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   SAMS Club - Club Number    |       X        |                 CARDX                  | 
|                       |    |   SAMS Club - Club Number    |       3        |                 3DCART                  | 
|                       |    |   SAMS Club - Club Number    |       T        |                 TEMPUS                  | 
|                       |    |   SAMS Club - Club Number    |       C        |                 CANCEL                  | 
|                       |    |   SAMS Club - Club Number    |       N        |                 NOT_CHECKED                  | 
|                       |    |   SAMS Club - Club Number    |       V        |                 MIVA                  | 
|                       |    |   SAMS Club - Club Number    |       A        |                 ACTIVE                  | 
|                       |    |   SAMS Club - Club Number    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   SAMS Club - Club Number    |       C        |                 CLOVER                  | 
|                       |    |   SAMS Club - Club Number    |       P        |                 PRINT_ONLY                  | 
|                       |    |   SAMS Club - Club Number    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   SAMS Club - Club Number    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   SAMS Club - Club Number    |       A        |                 ADD                  | 
|                       |    |   SAMS Club - Club Number    |       NA        |                 NOT_APPLICABLE                  | 

| VASWELLSP| companyId   |   Wells Company Id Field    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Wells Company Id Field    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Wells Company Id Field    |       C        |                 CBS                  | 
|                       |    |   Wells Company Id Field    |       A        |                 AGENT_ISV                  | 
|                       |    |   Wells Company Id Field    |       CM        |                 CMM                  | 
|                       |    |   Wells Company Id Field    |       Y        |                 CHECKED                  | 
|                       |    |   Wells Company Id Field    |       N        |                 NO                  | 
|                       |    |   Wells Company Id Field    |       Y        |                 YES                  | 
|                       |    |   Wells Company Id Field    |       Y        |                 USE_PRIMARY_EMAIL                  | 

| VASPERKA| contractSignDateTime   |   Date Time Contract Signed    |       T        |                 TEMPUS                  | 
|                       |    |   Date Time Contract Signed    |       A        |                 ACTIVE                  | 
|                       |    |   Date Time Contract Signed    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Date Time Contract Signed    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Date Time Contract Signed    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Date Time Contract Signed    |       S        |                 SHOPIFY                  | 
|                       |    |   Date Time Contract Signed    |       Y        |                 CHECKED                  | 
|                       |    |   Date Time Contract Signed    |       3        |                 3DCART                  | 
|                       |    |   Date Time Contract Signed    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Date Time Contract Signed    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Date Time Contract Signed    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Date Time Contract Signed    |       03        |                 MSI_APP                  | 
|                       |    |   Date Time Contract Signed    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Date Time Contract Signed    |       C        |                 CLOVER                  | 
|                       |    |   Date Time Contract Signed    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Date Time Contract Signed    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Date Time Contract Signed    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Date Time Contract Signed    |       N        |                 NO                  | 
|                       |    |   Date Time Contract Signed    |       D        |                 DELETE                  | 
|                       |    |   Date Time Contract Signed    |       O        |                 OTHER                  | 
|                       |    |   Date Time Contract Signed    |       A        |                 ADD                  | 
|                       |    |   Date Time Contract Signed    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Date Time Contract Signed    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Date Time Contract Signed    |       Y        |                 YES                  | 
|                       |    |   Date Time Contract Signed    |       K        |                 KIBO                  | 
|                       |    |   Date Time Contract Signed    |       V        |                 MIVA                  | 
|                       |    |   Date Time Contract Signed    |       X        |                 CARDX                  | 
|                       |    |   Date Time Contract Signed    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Date Time Contract Signed    |       V        |                 VALUELINK                  | 
|                       |    |   Date Time Contract Signed    |       M        |                 MAGENTO2                  | 
|                       |    |   Date Time Contract Signed    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Date Time Contract Signed    |       C        |                 CANCEL                  | 
|                       |    |   Date Time Contract Signed    |       C        |                 CENPOS                  | 

| VASBPMOB| convenienceFeeInd   |   Convenience Fee Indicator for BP Mobile    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       CM        |                 CMM                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       C        |                 CBS                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       N        |                 NO                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       A        |                 AGENT_ISV                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Convenience Fee Indicator for BP Mobile    |       Y        |                 YES                  | 

| VASMSTTIST| dataRightsOptOutCode   |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       B        |                 BREAD                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       Y        |                 CHECKED                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       Y        |                 YES                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       03        |                 PAYEEZY                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       1        |                 OPTED_OUT                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       02        |                 IPG                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       04        |                 UCOMM                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       01        |                 FIRST_API                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       00        |                 NONE                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Type Of Merchant Data Rights Opt Out For Usage Of Their Internal Data.    |       N        |                 NO                  | 

| VASDBTTERMID| dbtTermIdStatus   |   Program Status for Debit Term Id    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Debit Term Id    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Debit Term Id    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Debit Term Id    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Debit Term Id    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Debit Term Id    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Debit Term Id    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Debit Term Id    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Debit Term Id    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Debit Term Id    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Debit Term Id    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Debit Term Id    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Debit Term Id    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Debit Term Id    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Debit Term Id    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Debit Term Id    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Debit Term Id    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Debit Term Id    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Debit Term Id    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Debit Term Id    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Debit Term Id    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Debit Term Id    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Debit Term Id    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Debit Term Id    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Debit Term Id    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Debit Term Id    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Debit Term Id    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Debit Term Id    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 

| VASPAYEEZY| developerEmailId   |   Developer Email ID    |       C        |                 CANCEL                  | 
|                       |    |   Developer Email ID    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   Developer Email ID    |       P        |                 PENDING                  | 
|                       |    |   Developer Email ID    |       Y        |                 YES                  | 
|                       |    |   Developer Email ID    |       03        |                 BLANK                  | 
|                       |    |   Developer Email ID    |       A        |                 ACTIVE                  | 
|                       |    |   Developer Email ID    |       Y        |                 CHECKED                  | 
|                       |    |   Developer Email ID    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Developer Email ID    |       N        |                 NO                  | 
|                       |    |   Developer Email ID    |       01        |                 FDMS_POS                  | 
|                       | developerId   |   Developer ID    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Developer ID    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Developer ID    |       CM        |                 CMM                  | 
|                       |    |   Developer ID    |       N        |                 NO                  | 
|                       |    |   Developer ID    |       Y        |                 YES                  | 
|                       |    |   Developer ID    |       C        |                 CBS                  | 
|                       |    |   Developer ID    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Developer ID    |       Y        |                 CHECKED                  | 
|                       |    |   Developer ID    |       A        |                 AGENT_ISV                  | 

| VASDISCDBTACP| discDbtAcpOfferingType   |   Offering Type for Discover Debit Acceptance    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Discover Debit Acceptance    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       | discDbtAcpStatus   |   Program Status for Discover Debit Acceptance    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Discover Debit Acceptance    |       A        |                 ACTIVE                  | 

| VASDISCINCAUTH| discIncAuthOfferingType   |   Offering Type for Discover Inc Auth    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Discover Inc Auth    |       01        |                 EMV_CAMPAIGN                  | 
|                       | discIncAuthStatus   |   Program Status for Discover Inc Auth    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Discover Inc Auth    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Discover Inc Auth    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Discover Inc Auth    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Discover Inc Auth    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Discover Inc Auth    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Discover Inc Auth    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Discover Inc Auth    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Inc Auth    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Discover Inc Auth    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Inc Auth    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Discover Inc Auth    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Discover Inc Auth    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Discover Inc Auth    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Discover Inc Auth    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Discover Inc Auth    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Discover Inc Auth    |       9        |                 CANCELLED_BY_MERCHANT                  | 

| VASDISCPROMPRG| discPrmPrgEffectiveDate   |   Effective Date for Discover Prm Prg    |       N        |                 NO                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       04        |                 UCOMM                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       03        |                 PAYEEZY                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       Y        |                 CHECKED                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       Y        |                 YES                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       02        |                 IPG                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       01        |                 FIRST_API                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       B        |                 BREAD                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       00        |                 NONE                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       1        |                 OPTED_OUT                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Effective Date for Discover Prm Prg    |       B        |                 ONLINE_AND_PRINT                  | 
|                       | discPrmPrgExpiryDate   |   Expiry Date for Discover Prm Prg    |       D        |                 DELETE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       A        |                 ACTIVE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       T        |                 TEMPUS                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       V        |                 MIVA                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       S        |                 SHOPIFY                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       Y        |                 YES                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       V        |                 VALUELINK                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       Y        |                 CHECKED                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       A        |                 ADD                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       C        |                 CANCEL                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       C        |                 CENPOS                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       K        |                 KIBO                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       O        |                 OTHER                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       M        |                 MAGENTO2                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       X        |                 CARDX                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       3        |                 3DCART                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       03        |                 MSI_APP                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       C        |                 CLOVER                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Expiry Date for Discover Prm Prg    |       N        |                 NO                  | 
|                       | discPrmPrgOfferingType   |   offering Type for Discover Prm Prg    |       03        |                 ESSENTIALS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 ELIGIBLE                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   offering Type for Discover Prm Prg    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   offering Type for Discover Prm Prg    |       02        |                 NT_STANDARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       04        |                 ADVANCED                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       W        |                 WHITE_LISTED                  | 
|                       |    |   offering Type for Discover Prm Prg    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   offering Type for Discover Prm Prg    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   offering Type for Discover Prm Prg    |       06        |                 STANDARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   offering Type for Discover Prm Prg    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       B        |                 BLACK_LISTED                  | 
|                       |    |   offering Type for Discover Prm Prg    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   offering Type for Discover Prm Prg    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   offering Type for Discover Prm Prg    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   offering Type for Discover Prm Prg    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   offering Type for Discover Prm Prg    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   offering Type for Discover Prm Prg    |       05        |                 PREMIUM                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   offering Type for Discover Prm Prg    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   offering Type for Discover Prm Prg    |       03        |                 NT_HYBRID                  | 
|                       |    |   offering Type for Discover Prm Prg    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   offering Type for Discover Prm Prg    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   offering Type for Discover Prm Prg    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   offering Type for Discover Prm Prg    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   offering Type for Discover Prm Prg    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   offering Type for Discover Prm Prg    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       | discPrmPrgPVI   |   PVI for Discover Prm Prg    |       A        |                 AGENT_ISV                  | 
|                       |    |   PVI for Discover Prm Prg    |       C        |                 CBS                  | 
|                       |    |   PVI for Discover Prm Prg    |       Y        |                 CHECKED                  | 
|                       |    |   PVI for Discover Prm Prg    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   PVI for Discover Prm Prg    |       N        |                 NOT_CHECKED                  | 
|                       |    |   PVI for Discover Prm Prg    |       N        |                 NO                  | 
|                       |    |   PVI for Discover Prm Prg    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   PVI for Discover Prm Prg    |       Y        |                 YES                  | 
|                       |    |   PVI for Discover Prm Prg    |       CM        |                 CMM                  | 
|                       | discPrmPrgStatus   |   Program Status for Discover Prm Prg    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Discover Prm Prg    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Discover Prm Prg    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Discover Prm Prg    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Prm Prg    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Discover Prm Prg    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Discover Prm Prg    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Discover Prm Prg    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Discover Prm Prg    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Discover Prm Prg    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Discover Prm Prg    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Discover Prm Prg    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Discover Prm Prg    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Discover Prm Prg    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Discover Prm Prg    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Discover Prm Prg    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Discover Prm Prg    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Discover Prm Prg    |       1        |                 SUBSCRIBED                  | 

| VASNTWKTKN| discover   |   Discover Token    |       I        |                 INITIATED                  | 
|                       |    |   Discover Token    |       A        |                 PROVISIONED                  | 
|                       |    |   Discover Token    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Discover Token    |       Y        |                 YES                  | 
|                       |    |   Discover Token    |       R        |                 RENEWAL                  | 
|                       |    |   Discover Token    |       N        |                 NEW                  | 
|                       |    |   Discover Token    |       N        |                 NO                  | 
|                       |    |   Discover Token    |       U        |                 UPGRADE                  | 
|                       |    |   Discover Token    |       F        |                 FAILED                  | 
|                       |    |   Discover Token    |               |                 NONE                  | 
|                       |    |   Discover Token    |       Y        |                 CHECKED                  | 

| VASBPMOB| ebtFnsNum   |   EBT FNS Number for BP Mobile    |               |                                   | 

| VASGBSPOSINS| ecommercePlatform   |   Ecommerce Platform for GBS POS Installments    |       M        |                 MAGENTO2                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       N        |                 NO                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       Y        |                 YES                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       S        |                 SHOPIFY                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       C        |                 CENPOS                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       T        |                 TEMPUS                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       A        |                 ACTIVE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       V        |                 VALUELINK                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       A        |                 ADD                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       K        |                 KIBO                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       D        |                 DELETE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       3        |                 3DCART                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       Y        |                 CHECKED                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       C        |                 CANCEL                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       V        |                 MIVA                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       C        |                 CLOVER                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       O        |                 OTHER                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       03        |                 MSI_APP                  | 
|                       |    |   Ecommerce Platform for GBS POS Installments    |       X        |                 CARDX                  | 

| VASEMVCMP| emvBillingEffectiveDate   |   EMV Billing Effective Date    |               |                                   | 
|                       | emvBillingExpirationDate   |   EMV Billing Expiration Date    |               |                                   | 

| VASEMVENB| emvEnablementStatus   |   Program Status for EMV Enablement    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for EMV Enablement    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for EMV Enablement    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for EMV Enablement    |       L        |                 LIVE                  | 
|                       |    |   Program Status for EMV Enablement    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for EMV Enablement    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for EMV Enablement    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for EMV Enablement    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for EMV Enablement    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for EMV Enablement    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for EMV Enablement    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for EMV Enablement    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for EMV Enablement    |       R        |                 DENIED                  | 
|                       |    |   Program Status for EMV Enablement    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for EMV Enablement    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for EMV Enablement    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for EMV Enablement    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for EMV Enablement    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for EMV Enablement    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for EMV Enablement    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for EMV Enablement    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for EMV Enablement    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for EMV Enablement    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for EMV Enablement    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for EMV Enablement    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for EMV Enablement    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for EMV Enablement    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for EMV Enablement    |       8        |                 ACTIVE                  | 

| VASEMVCMP| emvOfferingType   |   EMV Offering Type    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   EMV Offering Type    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   EMV Offering Type    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   EMV Offering Type    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   EMV Offering Type    |       06        |                 STANDARD                  | 
|                       |    |   EMV Offering Type    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   EMV Offering Type    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   EMV Offering Type    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   EMV Offering Type    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   EMV Offering Type    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   EMV Offering Type    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   EMV Offering Type    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   EMV Offering Type    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   EMV Offering Type    |       05        |                 PREMIUM                  | 
|                       |    |   EMV Offering Type    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   EMV Offering Type    |       04        |                 ADVANCED                  | 
|                       |    |   EMV Offering Type    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   EMV Offering Type    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   EMV Offering Type    |       W        |                 WHITE_LISTED                  | 
|                       |    |   EMV Offering Type    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   EMV Offering Type    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   EMV Offering Type    |       B        |                 BLACK_LISTED                  | 
|                       |    |   EMV Offering Type    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   EMV Offering Type    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   EMV Offering Type    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   EMV Offering Type    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   EMV Offering Type    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   EMV Offering Type    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   EMV Offering Type    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   EMV Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   EMV Offering Type    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   EMV Offering Type    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   EMV Offering Type    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   EMV Offering Type    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   EMV Offering Type    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   EMV Offering Type    |       01        |                 ELIGIBLE                  | 
|                       |    |   EMV Offering Type    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   EMV Offering Type    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   EMV Offering Type    |       03        |                 NT_HYBRID                  | 
|                       |    |   EMV Offering Type    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   EMV Offering Type    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   EMV Offering Type    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   EMV Offering Type    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   EMV Offering Type    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   EMV Offering Type    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   EMV Offering Type    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   EMV Offering Type    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   EMV Offering Type    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   EMV Offering Type    |       02        |                 NT_STANDARD                  | 
|                       |    |   EMV Offering Type    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   EMV Offering Type    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   EMV Offering Type    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   EMV Offering Type    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   EMV Offering Type    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   EMV Offering Type    |       03        |                 ESSENTIALS                  | 
|                       |    |   EMV Offering Type    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   EMV Offering Type    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   EMV Offering Type    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   EMV Offering Type    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   EMV Offering Type    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   EMV Offering Type    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   EMV Offering Type    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       | emvProgramStatus   |   EMV Program Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   EMV Program Status    |       A        |                 ACTIVE                  | 
|                       |    |   EMV Program Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   EMV Program Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   EMV Program Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   EMV Program Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   EMV Program Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   EMV Program Status    |       8        |                 ACTIVE                  | 
|                       |    |   EMV Program Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   EMV Program Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   EMV Program Status    |       A        |                 APPROVED                  | 
|                       |    |   EMV Program Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   EMV Program Status    |       R        |                 DENIED                  | 
|                       |    |   EMV Program Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   EMV Program Status    |       C        |                 CANCEL                  | 
|                       |    |   EMV Program Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   EMV Program Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   EMV Program Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   EMV Program Status    |       D        |                 DECLINED                  | 
|                       |    |   EMV Program Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   EMV Program Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   EMV Program Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   EMV Program Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   EMV Program Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   EMV Program Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   EMV Program Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   EMV Program Status    |       L        |                 LIVE                  | 
|                       |    |   EMV Program Status    |       C        |                 CANCELLED_BY_FD                  | 

| VASWSLENT| enrollmentStatus   |   Enrollment Status for Wisely Entitlement    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       03        |                 ESSENTIALS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       05        |                 PREMIUM                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       02        |                 NT_STANDARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       04        |                 ADVANCED                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       06        |                 STANDARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 ELIGIBLE                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       03        |                 NT_HYBRID                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Enrollment Status for Wisely Entitlement    |       BI        |                 BANK_INITIATED_TRANS                  | 

| VASENTINSB| entInsightBenchBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Bench    |               |                                   | 
|                       | entInsightBenchStatus   |   Program Status for Enterprise Insights Bench    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Enterprise Insights Bench    |       6        |                 NO_RESPONSE                  | 
|                       | entInsightBenchofferingType   |   Offering Type for Enterprise Insights Bench    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Enterprise Insights Bench    |       04        |                 ADVANCED                  | 

| VASENTINS| entInsightBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights    |               |                                   | 

| VASENTINSD| entInsightDemographicOfferingType   |   Offering Type for Enterprise Insights Demographic    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Demographic    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       | entInsightDemographicStatus   |   Program Status for Enterprise Insights Demographic    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Enterprise Insights Demographic    |       C        |                 CANCEL_SURCHARGING                  | 
|                       | entInsightDemographicbillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Demographic    |               |                                   | 

| VASENTINSL| entInsightLobbyBillingEffectiveDate   |   Billing Effective Date for Enterprise Insights Lobby    |               |                                   | 
|                       | entInsightLobbyOfferingType   |   Offering Type for Enterprise Insights Lobby    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights Lobby    |       05        |                 PREMIUM                  | 
|                       | entInsightLobbyStatus   |   Program Status for Enterprise Insights Lobby    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights Lobby    |       Y        |                 DISCOVER_REVIEW                  | 

| VASENTINS| entInsightOfferingType   |   Offering Type for Enterprise Insights    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Enterprise Insights    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Enterprise Insights    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Enterprise Insights    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Enterprise Insights    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Enterprise Insights    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Enterprise Insights    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Enterprise Insights    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Enterprise Insights    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Enterprise Insights    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Enterprise Insights    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Enterprise Insights    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Enterprise Insights    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Enterprise Insights    |       FT        |                 FUNDS_TRANSFER                  | 
|                       | entInsightStatus   |   Program Status for Enterprise Insights    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Enterprise Insights    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Enterprise Insights    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Enterprise Insights    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Enterprise Insights    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Enterprise Insights    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Enterprise Insights    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Enterprise Insights    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Enterprise Insights    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Enterprise Insights    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Enterprise Insights    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Enterprise Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Enterprise Insights    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Enterprise Insights    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Enterprise Insights    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Enterprise Insights    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Enterprise Insights    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Enterprise Insights    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Enterprise Insights    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Enterprise Insights    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Enterprise Insights    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Enterprise Insights    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Enterprise Insights    |       I        |                 IN_PROGRESS                  | 

| VASNTWKTKN| fiservTokenRequesterId   |   Fiserv Token Requester ID for Network Tokens    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       04        |                 UCOMM                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       02        |                 IPG                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       Y        |                 CHECKED                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       01        |                 FIRST_API                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       B        |                 BREAD                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       03        |                 PAYEEZY                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       Y        |                 YES                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       00        |                 NONE                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       N        |                 NO                  | 
|                       |    |   Fiserv Token Requester ID for Network Tokens    |       1        |                 OPTED_OUT                  | 

| VASFRDDTCT| fraudDetectBillingEffectiveDate   |   Billing Effective Date for Fraud Detect    |               |                                   | 
|                       | fraudDetectofferingType   |   Offering Type for Fraud Detect    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Fraud Detect    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Fraud Detect    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Fraud Detect    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Detect    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Fraud Detect    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Detect    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Fraud Detect    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Fraud Detect    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Fraud Detect    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Fraud Detect    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Fraud Detect    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Detect    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Fraud Detect    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Detect    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Detect    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Fraud Detect    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Fraud Detect    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Detect    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Detect    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Fraud Detect    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Detect    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Fraud Detect    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Fraud Detect    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Fraud Detect    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Fraud Detect    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Detect    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Fraud Detect    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Fraud Detect    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Fraud Detect    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Fraud Detect    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Fraud Detect    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Fraud Detect    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Detect    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Fraud Detect    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Fraud Detect    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Detect    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Fraud Detect    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Fraud Detect    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Fraud Detect    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Fraud Detect    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Detect    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Fraud Detect    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Fraud Detect    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Fraud Detect    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Fraud Detect    |       01        |                 NT_ON_THE_GO                  | 
|                       | fraudDetectstatus   |   Program Status for Fraud Detect    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Fraud Detect    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Fraud Detect    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Fraud Detect    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Fraud Detect    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Fraud Detect    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Fraud Detect    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Fraud Detect    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Fraud Detect    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Fraud Detect    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Fraud Detect    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Fraud Detect    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Fraud Detect    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Fraud Detect    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Fraud Detect    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Fraud Detect    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Fraud Detect    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Fraud Detect    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Fraud Detect    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Fraud Detect    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Fraud Detect    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Fraud Detect    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Fraud Detect    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Fraud Detect    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Fraud Detect    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Fraud Detect    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Fraud Detect    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Fraud Detect    |       Y        |                 DISCOVER_REVIEW                  | 

| VASFRDFLX| fraudFlexBillingEffectiveDate   |   Billing Effective Date for Fraud Flex    |               |                                   | 
|                       | fraudFlexOfferingType   |   Offering Type for Fraud Flex    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Fraud Flex    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Fraud Flex    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Fraud Flex    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Flex    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Fraud Flex    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Fraud Flex    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Fraud Flex    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Flex    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Flex    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Fraud Flex    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Flex    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Fraud Flex    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Fraud Flex    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Fraud Flex    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Fraud Flex    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Fraud Flex    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Fraud Flex    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Fraud Flex    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Fraud Flex    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Fraud Flex    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Fraud Flex    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Fraud Flex    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Flex    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Flex    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Fraud Flex    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Fraud Flex    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Fraud Flex    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Flex    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Fraud Flex    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Fraud Flex    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Fraud Flex    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Fraud Flex    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Fraud Flex    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Fraud Flex    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Fraud Flex    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Fraud Flex    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Fraud Flex    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Fraud Flex    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Fraud Flex    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Fraud Flex    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Fraud Flex    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Fraud Flex    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Fraud Flex    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Fraud Flex    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       | fraudFlexStatus   |   Program Status for Fraud Flex    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Fraud Flex    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Fraud Flex    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Fraud Flex    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Fraud Flex    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Fraud Flex    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Fraud Flex    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Fraud Flex    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Fraud Flex    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Fraud Flex    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Fraud Flex    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Fraud Flex    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Fraud Flex    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Fraud Flex    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Fraud Flex    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Fraud Flex    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Fraud Flex    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Fraud Flex    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Fraud Flex    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Fraud Flex    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Fraud Flex    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Fraud Flex    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Fraud Flex    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Fraud Flex    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Fraud Flex    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Fraud Flex    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Fraud Flex    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Fraud Flex    |       3        |                 PENDING_UNCONTACTED                  | 

| VASFRDDTCT| gatewayApi   |   Fraud Detect Entry Point    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Fraud Detect Entry Point    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Fraud Detect Entry Point    |       B        |                 BREAD                  | 
|                       |    |   Fraud Detect Entry Point    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Fraud Detect Entry Point    |       03        |                 PAYEEZY                  | 
|                       |    |   Fraud Detect Entry Point    |       00        |                 NONE                  | 
|                       |    |   Fraud Detect Entry Point    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Fraud Detect Entry Point    |       Y        |                 CHECKED                  | 
|                       |    |   Fraud Detect Entry Point    |       01        |                 FIRST_API                  | 
|                       |    |   Fraud Detect Entry Point    |       1        |                 OPTED_OUT                  | 
|                       |    |   Fraud Detect Entry Point    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Fraud Detect Entry Point    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Fraud Detect Entry Point    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Fraud Detect Entry Point    |       02        |                 IPG                  | 
|                       |    |   Fraud Detect Entry Point    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Fraud Detect Entry Point    |       04        |                 UCOMM                  | 
|                       |    |   Fraud Detect Entry Point    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Fraud Detect Entry Point    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Fraud Detect Entry Point    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Fraud Detect Entry Point    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Fraud Detect Entry Point    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Fraud Detect Entry Point    |       Y        |                 YES                  | 
|                       |    |   Fraud Detect Entry Point    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Fraud Detect Entry Point    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Fraud Detect Entry Point    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Fraud Detect Entry Point    |       N        |                 NO                  | 
|                       |    |   Fraud Detect Entry Point    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 

| VASGBSPOSINS| gbsPosInsStatus   |   Program Status for GBS POS Installment    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for GBS POS Installment    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for GBS POS Installment    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for GBS POS Installment    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for GBS POS Installment    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for GBS POS Installment    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for GBS POS Installment    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for GBS POS Installment    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for GBS POS Installment    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for GBS POS Installment    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for GBS POS Installment    |       L        |                 LIVE                  | 
|                       |    |   Program Status for GBS POS Installment    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for GBS POS Installment    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for GBS POS Installment    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for GBS POS Installment    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for GBS POS Installment    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for GBS POS Installment    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for GBS POS Installment    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for GBS POS Installment    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for GBS POS Installment    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for GBS POS Installment    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for GBS POS Installment    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for GBS POS Installment    |       R        |                 DENIED                  | 
|                       |    |   Program Status for GBS POS Installment    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for GBS POS Installment    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for GBS POS Installment    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for GBS POS Installment    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for GBS POS Installment    |       8        |                 ACTIVE                  | 
|                       | gbsPosInsofferingType   |   Offering Type for GBS POS Installment    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for GBS POS Installment    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for GBS POS Installment    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for GBS POS Installment    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for GBS POS Installment    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for GBS POS Installment    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for GBS POS Installment    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for GBS POS Installment    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for GBS POS Installment    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for GBS POS Installment    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for GBS POS Installment    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for GBS POS Installment    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for GBS POS Installment    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for GBS POS Installment    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for GBS POS Installment    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for GBS POS Installment    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for GBS POS Installment    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for GBS POS Installment    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for GBS POS Installment    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for GBS POS Installment    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for GBS POS Installment    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for GBS POS Installment    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for GBS POS Installment    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for GBS POS Installment    |       03        |                 ESSENTIALS                  | 

| VASTAP2PE| ingenicoOnguard   |   Ingenico On-Guard for Transarmor    |       N        |                 NO                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       A        |                 PROVISIONED                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       N        |                 NEW                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       I        |                 INITIATED                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       F        |                 FAILED                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |               |                 NONE                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       U        |                 UPGRADE                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       R        |                 RENEWAL                  | 
|                       |    |   Ingenico On-Guard for Transarmor    |       Y        |                 YES                  | 

| VASLCRDBT| lcrDebitStatus   |   Program Status for LCR Debit Flags (Optional)    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       L        |                 LIVE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       R        |                 DENIED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for LCR Debit Flags (Optional)    |       A        |                 ACTIVE_SURCHARGING                  | 

| VASLCRFB| lcrStatus   |   Program Status of LCR Fallback    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status of LCR Fallback    |       C        |                 CANCEL                  | 
|                       |    |   Program Status of LCR Fallback    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status of LCR Fallback    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status of LCR Fallback    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status of LCR Fallback    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status of LCR Fallback    |       L        |                 LIVE                  | 
|                       |    |   Program Status of LCR Fallback    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status of LCR Fallback    |       R        |                 DENIED                  | 
|                       |    |   Program Status of LCR Fallback    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status of LCR Fallback    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status of LCR Fallback    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status of LCR Fallback    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status of LCR Fallback    |       A        |                 APPROVED                  | 
|                       |    |   Program Status of LCR Fallback    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status of LCR Fallback    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status of LCR Fallback    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status of LCR Fallback    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status of LCR Fallback    |       D        |                 DECLINED                  | 
|                       |    |   Program Status of LCR Fallback    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status of LCR Fallback    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status of LCR Fallback    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status of LCR Fallback    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status of LCR Fallback    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status of LCR Fallback    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status of LCR Fallback    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status of LCR Fallback    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status of LCR Fallback    |       I        |                 IN_PROGRESS                  | 

| VASMSTTIST| mainStreetProgramstatus   |   Program Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status    |       C        |                 CANCEL                  | 
|                       |    |   Program Status    |       L        |                 LIVE                  | 
|                       |    |   Program Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status    |       R        |                 DENIED                  | 
|                       |    |   Program Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status    |       D        |                 DECLINED                  | 
|                       |    |   Program Status    |       A        |                 APPROVED                  | 
|                       |    |   Program Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status    |       4        |                 PENDING_CONTACTED                  | 
|                       | mainStreetbillingEffectiveDate   |   Billing Effective Date     |               |                                   | 

| VASNTWKTKN| masterCard   |   Master Card Network Tokens    |       CM        |                 CMM                  | 
|                       |    |   Master Card Network Tokens    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Master Card Network Tokens    |       N        |                 NO                  | 
|                       |    |   Master Card Network Tokens    |       A        |                 AGENT_ISV                  | 
|                       |    |   Master Card Network Tokens    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Master Card Network Tokens    |       Y        |                 YES                  | 
|                       |    |   Master Card Network Tokens    |       C        |                 CBS                  | 
|                       |    |   Master Card Network Tokens    |       Y        |                 CHECKED                  | 
|                       |    |   Master Card Network Tokens    |       Y        |                 USE_PRIMARY_EMAIL                  | 

| VASMSTPWLT| masterpassofferingType   |   Masterpass Offering Type    |       06        |                 STANDARD                  | 
|                       |    |   Masterpass Offering Type    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Masterpass Offering Type    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Masterpass Offering Type    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Masterpass Offering Type    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Masterpass Offering Type    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Masterpass Offering Type    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Masterpass Offering Type    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Masterpass Offering Type    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Masterpass Offering Type    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Masterpass Offering Type    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Masterpass Offering Type    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Masterpass Offering Type    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Masterpass Offering Type    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Masterpass Offering Type    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Masterpass Offering Type    |       05        |                 PREMIUM                  | 
|                       |    |   Masterpass Offering Type    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Masterpass Offering Type    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Masterpass Offering Type    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Masterpass Offering Type    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Masterpass Offering Type    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Masterpass Offering Type    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Masterpass Offering Type    |       03        |                 ESSENTIALS                  | 
|                       |    |   Masterpass Offering Type    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Masterpass Offering Type    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Masterpass Offering Type    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Masterpass Offering Type    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Masterpass Offering Type    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Masterpass Offering Type    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Masterpass Offering Type    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Masterpass Offering Type    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Masterpass Offering Type    |       02        |                 NT_STANDARD                  | 
|                       |    |   Masterpass Offering Type    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Masterpass Offering Type    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Masterpass Offering Type    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Masterpass Offering Type    |       03        |                 NT_HYBRID                  | 
|                       |    |   Masterpass Offering Type    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Masterpass Offering Type    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Masterpass Offering Type    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Masterpass Offering Type    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Masterpass Offering Type    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Masterpass Offering Type    |       04        |                 ADVANCED                  | 
|                       |    |   Masterpass Offering Type    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Masterpass Offering Type    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 ELIGIBLE                  | 
|                       |    |   Masterpass Offering Type    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Masterpass Offering Type    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Masterpass Offering Type    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Masterpass Offering Type    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Masterpass Offering Type    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Masterpass Offering Type    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Masterpass Offering Type    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Masterpass Offering Type    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Masterpass Offering Type    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Masterpass Offering Type    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Masterpass Offering Type    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       | masterpassstatus   |   Masterpass Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Masterpass Status    |       A        |                 ACTIVE                  | 
|                       |    |   Masterpass Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Masterpass Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Masterpass Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Masterpass Status    |       C        |                 CANCEL                  | 
|                       |    |   Masterpass Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Masterpass Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Masterpass Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Masterpass Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Masterpass Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Masterpass Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Masterpass Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Masterpass Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Masterpass Status    |       D        |                 DECLINED                  | 
|                       |    |   Masterpass Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Masterpass Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Masterpass Status    |       A        |                 APPROVED                  | 
|                       |    |   Masterpass Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Masterpass Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Masterpass Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Masterpass Status    |       R        |                 DENIED                  | 
|                       |    |   Masterpass Status    |       L        |                 LIVE                  | 
|                       |    |   Masterpass Status    |       8        |                 ACTIVE                  | 
|                       |    |   Masterpass Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Masterpass Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Masterpass Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Masterpass Status    |       Y        |                 DISCOVER_REVIEW                  | 

| VASMCMONEYSEND| mcMoneySendOfferingType   |   Offering Type for MC Moneysend    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for MC Moneysend    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for MC Moneysend    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for MC Moneysend    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for MC Moneysend    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for MC Moneysend    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for MC Moneysend    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for MC Moneysend    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for MC Moneysend    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for MC Moneysend    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for MC Moneysend    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for MC Moneysend    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for MC Moneysend    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for MC Moneysend    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for MC Moneysend    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for MC Moneysend    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for MC Moneysend    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for MC Moneysend    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for MC Moneysend    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for MC Moneysend    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for MC Moneysend    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for MC Moneysend    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for MC Moneysend    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for MC Moneysend    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for MC Moneysend    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for MC Moneysend    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for MC Moneysend    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for MC Moneysend    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for MC Moneysend    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for MC Moneysend    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for MC Moneysend    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for MC Moneysend    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for MC Moneysend    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for MC Moneysend    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for MC Moneysend    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for MC Moneysend    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for MC Moneysend    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for MC Moneysend    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for MC Moneysend    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for MC Moneysend    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for MC Moneysend    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for MC Moneysend    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for MC Moneysend    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for MC Moneysend    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for MC Moneysend    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for MC Moneysend    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       | mcMoneySendStatus   |   Program Status for MC Moneysend    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for MC Moneysend    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for MC Moneysend    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for MC Moneysend    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for MC Moneysend    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for MC Moneysend    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for MC Moneysend    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for MC Moneysend    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for MC Moneysend    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for MC Moneysend    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for MC Moneysend    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for MC Moneysend    |       L        |                 LIVE                  | 
|                       |    |   Program Status for MC Moneysend    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for MC Moneysend    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for MC Moneysend    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for MC Moneysend    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for MC Moneysend    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for MC Moneysend    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for MC Moneysend    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for MC Moneysend    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for MC Moneysend    |       R        |                 DENIED                  | 
|                       |    |   Program Status for MC Moneysend    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for MC Moneysend    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for MC Moneysend    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for MC Moneysend    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for MC Moneysend    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for MC Moneysend    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for MC Moneysend    |       D        |                 DECLINED                  | 

| VASSAMSPLS| memberShipId   |   SAMS Club Membership ID    |       00        |                 NONE                  | 
|                       |    |   SAMS Club Membership ID    |       02        |                 IPG                  | 
|                       |    |   SAMS Club Membership ID    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   SAMS Club Membership ID    |       03        |                 PAYEEZY                  | 
|                       |    |   SAMS Club Membership ID    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   SAMS Club Membership ID    |       Y        |                 CHECKED                  | 
|                       |    |   SAMS Club Membership ID    |       ABLS        |                 ABUELOS                  | 
|                       |    |   SAMS Club Membership ID    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   SAMS Club Membership ID    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   SAMS Club Membership ID    |       N        |                 NO                  | 
|                       |    |   SAMS Club Membership ID    |       Y        |                 YES                  | 
|                       |    |   SAMS Club Membership ID    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   SAMS Club Membership ID    |       01        |                 FIRST_API                  | 
|                       |    |   SAMS Club Membership ID    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   SAMS Club Membership ID    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   SAMS Club Membership ID    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   SAMS Club Membership ID    |       N        |                 NOT_CHECKED                  | 
|                       |    |   SAMS Club Membership ID    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   SAMS Club Membership ID    |       1        |                 OPTED_OUT                  | 
|                       |    |   SAMS Club Membership ID    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   SAMS Club Membership ID    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   SAMS Club Membership ID    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   SAMS Club Membership ID    |       B        |                 BREAD                  | 
|                       |    |   SAMS Club Membership ID    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   SAMS Club Membership ID    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   SAMS Club Membership ID    |       P        |                 PRINT_ONLY                  | 
|                       |    |   SAMS Club Membership ID    |       04        |                 UCOMM                  | 

| VASMERSRCH| merchSurchargeProgEffectiveDate   |   Surcharge Effective Date for Merchant Surcharge Program    |       N        |                 NO                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       CM        |                 CMM                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       A        |                 AGENT_ISV                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       C        |                 CBS                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       Y        |                 YES                  | 
|                       |    |   Surcharge Effective Date for Merchant Surcharge Program    |       Y        |                 CHECKED                  | 
|                       | merchSurchargeProgOfferingType   |   Offering Type for Merchant Surcharge Program    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Merchant Surcharge Program    |       P1        |                 FD_DSCV_PROMO                  | 
|                       | merchSurchargeProgSolutionType   |   Solution Type for Merchant Surcharge Program    |       01        |                 FDMS_POS                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       Y        |                 CHECKED                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       A        |                 ACTIVE                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       03        |                 BLANK                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       Y        |                 YES                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       P        |                 PENDING                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       C        |                 CANCEL                  | 
|                       |    |   Solution Type for Merchant Surcharge Program    |       N        |                 NO                  | 
|                       | merchSurchargeProgStatus   |   Program Status for Merchant Surcharge Program    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Merchant Surcharge Program    |       8        |                 ACTIVE                  | 
|                       | merchSurchargeProgSurchargeRate   |   Surcharge Rate for Merchant Surcharge Program    |       Y        |                 CHECKED                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       04        |                 UCOMM                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       B        |                 BREAD                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       Y        |                 YES                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       1        |                 OPTED_OUT                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       00        |                 NONE                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       01        |                 FIRST_API                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       N        |                 NO                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       02        |                 IPG                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       03        |                 PAYEEZY                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Surcharge Rate for Merchant Surcharge Program    |       SPKL        |                 SPRINKLES                  | 

| VASWSLENT| merchantIdentifier   |   Merchant Identifier for Wisely Entitlement    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       8        |                 ACTIVE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       D        |                 DECLINED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       C        |                 CANCEL                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       R        |                 DENIED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       L        |                 LIVE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       A        |                 ACTIVE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       A        |                 APPROVED                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Merchant Identifier for Wisely Entitlement    |       N        |                 ALLOW_DEBIT_FLAGS                  | 

| VASBPMOB| mobInd   |   Mobile Indicator for BP Mobile    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       02        |                 IPG                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       04        |                 UCOMM                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       03        |                 PAYEEZY                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       01        |                 FIRST_API                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       N        |                 NO                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       1        |                 OPTED_OUT                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       Y        |                 YES                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       B        |                 BREAD                  | 
|                       |    |   Mobile Indicator for BP Mobile    |       00        |                 NONE                  | 

| VASNTWKTKN| networkTokenBillingEffectiveDate   |   Billing Effective Date for Network Tokens    |               |                                   | 
|                       | networkTokenOfferingType   |   Offering Type for Network Tokens    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Network Tokens    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Network Tokens    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Network Tokens    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Network Tokens    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Network Tokens    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Network Tokens    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Network Tokens    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Network Tokens    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Network Tokens    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Network Tokens    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Network Tokens    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Network Tokens    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Network Tokens    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Network Tokens    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Network Tokens    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Network Tokens    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Network Tokens    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Network Tokens    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Network Tokens    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Network Tokens    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Network Tokens    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Network Tokens    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Network Tokens    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Network Tokens    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Network Tokens    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Network Tokens    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Network Tokens    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Network Tokens    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Network Tokens    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Network Tokens    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Network Tokens    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Network Tokens    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Network Tokens    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Network Tokens    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Network Tokens    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Network Tokens    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Network Tokens    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Network Tokens    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Network Tokens    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Network Tokens    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Network Tokens    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Network Tokens    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Network Tokens    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Network Tokens    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Network Tokens    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Network Tokens    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Network Tokens    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Network Tokens    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Network Tokens    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Network Tokens    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Network Tokens    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Network Tokens    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Network Tokens    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Network Tokens    |       01        |                 ELIGIBLE                  | 
|                       | networkTokenStatus   |   Program Status for Network Tokens    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Network Tokens    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Network Tokens    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Network Tokens    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Network Tokens    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Network Tokens    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Network Tokens    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Network Tokens    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Network Tokens    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Network Tokens    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Network Tokens    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Network Tokens    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Network Tokens    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Network Tokens    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Network Tokens    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Network Tokens    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Network Tokens    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Network Tokens    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Network Tokens    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Network Tokens    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Network Tokens    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Network Tokens    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Network Tokens    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Network Tokens    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Network Tokens    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Network Tokens    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Network Tokens    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Network Tokens    |       6        |                 NO_RESPONSE                  | 

| VASSAMSPLS| newUpgRnwlInd   |   SAMS Club New/Upgrade/Renewal Indicator    |       N        |                 NEW                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       N        |                 NO                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       U        |                 UPGRADE                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       F        |                 FAILED                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       A        |                 PROVISIONED                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |               |                 NONE                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       I        |                 INITIATED                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       Y        |                 CHECKED                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       N        |                 NOT_CHECKED                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       Y        |                 YES                  | 
|                       |    |   SAMS Club New/Upgrade/Renewal Indicator    |       R        |                 RENEWAL                  | 
|                       | nxtRnwlDt   |   SAMS Club Next Renewal Date    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   SAMS Club Next Renewal Date    |       A        |                 AGENT_ISV                  | 
|                       |    |   SAMS Club Next Renewal Date    |       N        |                 NOT_CHECKED                  | 
|                       |    |   SAMS Club Next Renewal Date    |       N        |                 NO                  | 
|                       |    |   SAMS Club Next Renewal Date    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   SAMS Club Next Renewal Date    |       C        |                 CBS                  | 
|                       |    |   SAMS Club Next Renewal Date    |       CM        |                 CMM                  | 
|                       |    |   SAMS Club Next Renewal Date    |       Y        |                 CHECKED                  | 
|                       |    |   SAMS Club Next Renewal Date    |       Y        |                 YES                  | 

| VASGBSPOSINS| partner   |   Partner for GBS POS Installments    |       01        |                 FIRST_API                  | 
|                       |    |   Partner for GBS POS Installments    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Partner for GBS POS Installments    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Partner for GBS POS Installments    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Partner for GBS POS Installments    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Partner for GBS POS Installments    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Partner for GBS POS Installments    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Partner for GBS POS Installments    |       1        |                 OPTED_OUT                  | 
|                       |    |   Partner for GBS POS Installments    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Partner for GBS POS Installments    |       02        |                 IPG                  | 
|                       |    |   Partner for GBS POS Installments    |       00        |                 NONE                  | 
|                       |    |   Partner for GBS POS Installments    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Partner for GBS POS Installments    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Partner for GBS POS Installments    |       Y        |                 CHECKED                  | 
|                       |    |   Partner for GBS POS Installments    |       03        |                 PAYEEZY                  | 
|                       |    |   Partner for GBS POS Installments    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Partner for GBS POS Installments    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Partner for GBS POS Installments    |       N        |                 NO                  | 
|                       |    |   Partner for GBS POS Installments    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Partner for GBS POS Installments    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Partner for GBS POS Installments    |       Y        |                 YES                  | 
|                       |    |   Partner for GBS POS Installments    |       04        |                 UCOMM                  | 
|                       |    |   Partner for GBS POS Installments    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Partner for GBS POS Installments    |       B        |                 BREAD                  | 
|                       |    |   Partner for GBS POS Installments    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Partner for GBS POS Installments    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Partner for GBS POS Installments    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 

| VASPAYEEZY| payezeeyBillingEffectiveDate   |   Billing Effective Date    |               |                                   | 
|                       | payezeeyOfferingType   |   Payeezy Offering Type    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Payeezy Offering Type    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Payeezy Offering Type    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Payeezy Offering Type    |       06        |                 STANDARD                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Payeezy Offering Type    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Payeezy Offering Type    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Payeezy Offering Type    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Payeezy Offering Type    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Payeezy Offering Type    |       03        |                 NT_HYBRID                  | 
|                       |    |   Payeezy Offering Type    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Payeezy Offering Type    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Payeezy Offering Type    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Payeezy Offering Type    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Payeezy Offering Type    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Payeezy Offering Type    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Payeezy Offering Type    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Payeezy Offering Type    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Payeezy Offering Type    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Payeezy Offering Type    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Payeezy Offering Type    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Payeezy Offering Type    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Payeezy Offering Type    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Payeezy Offering Type    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Payeezy Offering Type    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Payeezy Offering Type    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Payeezy Offering Type    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Payeezy Offering Type    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Payeezy Offering Type    |       02        |                 NT_STANDARD                  | 
|                       |    |   Payeezy Offering Type    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Payeezy Offering Type    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Payeezy Offering Type    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Payeezy Offering Type    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Payeezy Offering Type    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Payeezy Offering Type    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Payeezy Offering Type    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Payeezy Offering Type    |       03        |                 ESSENTIALS                  | 
|                       |    |   Payeezy Offering Type    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Payeezy Offering Type    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Payeezy Offering Type    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Payeezy Offering Type    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Payeezy Offering Type    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 ELIGIBLE                  | 
|                       |    |   Payeezy Offering Type    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Payeezy Offering Type    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Payeezy Offering Type    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Payeezy Offering Type    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Payeezy Offering Type    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Payeezy Offering Type    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Payeezy Offering Type    |       04        |                 ADVANCED                  | 
|                       |    |   Payeezy Offering Type    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Payeezy Offering Type    |       05        |                 PREMIUM                  | 
|                       |    |   Payeezy Offering Type    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Payeezy Offering Type    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Payeezy Offering Type    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Payeezy Offering Type    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Payeezy Offering Type    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       | payezeeyProgramStatus   |   Payeezy Program Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Payeezy Program Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Payeezy Program Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Payeezy Program Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Payeezy Program Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Payeezy Program Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Payeezy Program Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Payeezy Program Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Payeezy Program Status    |       D        |                 DECLINED                  | 
|                       |    |   Payeezy Program Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Payeezy Program Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Payeezy Program Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Payeezy Program Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Payeezy Program Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Payeezy Program Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Payeezy Program Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Payeezy Program Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Payeezy Program Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Payeezy Program Status    |       R        |                 DENIED                  | 
|                       |    |   Payeezy Program Status    |       8        |                 ACTIVE                  | 
|                       |    |   Payeezy Program Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Payeezy Program Status    |       C        |                 CANCEL                  | 
|                       |    |   Payeezy Program Status    |       A        |                 ACTIVE                  | 
|                       |    |   Payeezy Program Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Payeezy Program Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Payeezy Program Status    |       L        |                 LIVE                  | 
|                       |    |   Payeezy Program Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Payeezy Program Status    |       A        |                 APPROVED                  | 

| VASPERKA| perkaAccountNum   |   Perka Account Number    |       Y        |                 CHECKED                  | 
|                       |    |   Perka Account Number    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Perka Account Number    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Perka Account Number    |       N        |                 NO                  | 
|                       |    |   Perka Account Number    |       Y        |                 YES                  | 
|                       |    |   Perka Account Number    |       A        |                 AGENT_ISV                  | 
|                       |    |   Perka Account Number    |       C        |                 CBS                  | 
|                       |    |   Perka Account Number    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Perka Account Number    |       CM        |                 CMM                  | 
|                       | perkaAccountStatus   |   Account Status    |       C        |                 CANCEL                  | 
|                       |    |   Account Status    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Account Status    |       A        |                 ACTIVE                  | 
|                       |    |   Account Status    |       01        |                 FDMS_POS                  | 
|                       |    |   Account Status    |       N        |                 NO                  | 
|                       |    |   Account Status    |       Y        |                 CHECKED                  | 
|                       |    |   Account Status    |       03        |                 BLANK                  | 
|                       |    |   Account Status    |       Y        |                 YES                  | 
|                       |    |   Account Status    |       P        |                 PENDING                  | 
|                       |    |   Account Status    |       02        |                 NON_FDMS_POS                  | 
|                       | perkaBillingEffectiveDate   |   Billing Effective Date for Perka    |               |                                   | 
|                       | perkaProductType   |   Perka Product Type    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Perka Product Type    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Perka Product Type    |       Y        |                 CHECKED                  | 
|                       |    |   Perka Product Type    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Perka Product Type    |       02        |                 IPG                  | 
|                       |    |   Perka Product Type    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Perka Product Type    |       B        |                 BREAD                  | 
|                       |    |   Perka Product Type    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Perka Product Type    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Perka Product Type    |       00        |                 NONE                  | 
|                       |    |   Perka Product Type    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Perka Product Type    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Perka Product Type    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Perka Product Type    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Perka Product Type    |       04        |                 UCOMM                  | 
|                       |    |   Perka Product Type    |       N        |                 NO                  | 
|                       |    |   Perka Product Type    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Perka Product Type    |       Y        |                 YES                  | 
|                       |    |   Perka Product Type    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Perka Product Type    |       01        |                 FIRST_API                  | 
|                       |    |   Perka Product Type    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Perka Product Type    |       1        |                 OPTED_OUT                  | 
|                       |    |   Perka Product Type    |       03        |                 PAYEEZY                  | 
|                       |    |   Perka Product Type    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Perka Product Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Perka Product Type    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Perka Product Type    |       UJUL        |                 UNCLE_JULIO                  | 
|                       | perkaTrainInd   |   Perka Training Indicator    |       Y        |                 TRAINING_REQUESTED                  | 
|                       |    |   Perka Training Indicator    |       N        |                 TRAINING_NOT_REQUESTED                  | 
|                       | perkaUniqueId   |   Perka Unique Identifier    |               |                                   | 

| VASPDATAPRT| personalDataProtectionBillingEffectiveDate   |   Billing Effective Date for Personal Data Protection    |               |                                   | 
|                       | personalDataProtectionOfferingType   |   Offering Type for Personal Data Protection    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Personal Data Protection    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Personal Data Protection    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Personal Data Protection    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Personal Data Protection    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Personal Data Protection    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Personal Data Protection    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Personal Data Protection    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Personal Data Protection    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Personal Data Protection    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Personal Data Protection    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Personal Data Protection    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Personal Data Protection    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Personal Data Protection    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Personal Data Protection    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Personal Data Protection    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Personal Data Protection    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Personal Data Protection    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Personal Data Protection    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Personal Data Protection    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Personal Data Protection    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Personal Data Protection    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       | personalDataProtectionStatus   |   Program Status for Personal Data Protection    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Personal Data Protection    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Personal Data Protection    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Personal Data Protection    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Personal Data Protection    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Personal Data Protection    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Personal Data Protection    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Personal Data Protection    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Personal Data Protection    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Personal Data Protection    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Personal Data Protection    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Personal Data Protection    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Personal Data Protection    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Personal Data Protection    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Personal Data Protection    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Personal Data Protection    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Personal Data Protection    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Personal Data Protection    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Personal Data Protection    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Personal Data Protection    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Personal Data Protection    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Personal Data Protection    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Personal Data Protection    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Personal Data Protection    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Personal Data Protection    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Personal Data Protection    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Personal Data Protection    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Personal Data Protection    |       C        |                 CANCEL                  | 

| VASPINLESSECOM| pinlessEcomStatus   |   Program Status for Pinless Ecomm    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Pinless Ecomm    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Pinless Ecomm    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Pinless Ecomm    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Pinless Ecomm    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Pinless Ecomm    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Pinless Ecomm    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Pinless Ecomm    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Pinless Ecomm    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Pinless Ecomm    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Pinless Ecomm    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Pinless Ecomm    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Pinless Ecomm    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Pinless Ecomm    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Pinless Ecomm    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Pinless Ecomm    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Pinless Ecomm    |       9        |                 CANCELLED_BY_MERCHANT                  | 

| VASMSTTIST| primaryEmailInd   |   Primary Email Indicator    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Primary Email Indicator    |       N        |                 NO                  | 
|                       |    |   Primary Email Indicator    |       CM        |                 CMM                  | 
|                       |    |   Primary Email Indicator    |       A        |                 AGENT_ISV                  | 
|                       |    |   Primary Email Indicator    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Primary Email Indicator    |       C        |                 CBS                  | 
|                       |    |   Primary Email Indicator    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Primary Email Indicator    |       Y        |                 CHECKED                  | 
|                       |    |   Primary Email Indicator    |       Y        |                 YES                  | 

| VASEMVCMP| rebateAmount   |   EMV Rebate Amount    |       04        |                 UCOMM                  | 
|                       |    |   EMV Rebate Amount    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   EMV Rebate Amount    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   EMV Rebate Amount    |       02        |                 IPG                  | 
|                       |    |   EMV Rebate Amount    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   EMV Rebate Amount    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   EMV Rebate Amount    |       N        |                 NOT_CHECKED                  | 
|                       |    |   EMV Rebate Amount    |       1        |                 OPTED_OUT                  | 
|                       |    |   EMV Rebate Amount    |       N        |                 NO                  | 
|                       |    |   EMV Rebate Amount    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   EMV Rebate Amount    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   EMV Rebate Amount    |       03        |                 PAYEEZY                  | 
|                       |    |   EMV Rebate Amount    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   EMV Rebate Amount    |       Y        |                 YES                  | 
|                       |    |   EMV Rebate Amount    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   EMV Rebate Amount    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   EMV Rebate Amount    |       B        |                 BREAD                  | 
|                       |    |   EMV Rebate Amount    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   EMV Rebate Amount    |       00        |                 NONE                  | 
|                       |    |   EMV Rebate Amount    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   EMV Rebate Amount    |       ABLS        |                 ABUELOS                  | 
|                       |    |   EMV Rebate Amount    |       01        |                 FIRST_API                  | 
|                       |    |   EMV Rebate Amount    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   EMV Rebate Amount    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   EMV Rebate Amount    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   EMV Rebate Amount    |       Y        |                 CHECKED                  | 
|                       |    |   EMV Rebate Amount    |       P        |                 PRINT_ONLY                  | 

| VASPERKA| reccuringCharge   |   Recurring Charge    |       R        |                 RENEWAL                  | 
|                       |    |   Recurring Charge    |       U        |                 UPGRADE                  | 
|                       |    |   Recurring Charge    |               |                 NONE                  | 
|                       |    |   Recurring Charge    |       N        |                 NEW                  | 
|                       |    |   Recurring Charge    |       A        |                 PROVISIONED                  | 
|                       |    |   Recurring Charge    |       Y        |                 CHECKED                  | 
|                       |    |   Recurring Charge    |       N        |                 NO                  | 
|                       |    |   Recurring Charge    |       Y        |                 YES                  | 
|                       |    |   Recurring Charge    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Recurring Charge    |       F        |                 FAILED                  | 
|                       |    |   Recurring Charge    |       I        |                 INITIATED                  | 

| VASPAYEEZY| referralCode   |   Referral Code    |       N        |                 NO                  | 
|                       |    |   Referral Code    |       04        |                 UCOMM                  | 
|                       |    |   Referral Code    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Referral Code    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Referral Code    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Referral Code    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Referral Code    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Referral Code    |       1        |                 OPTED_OUT                  | 
|                       |    |   Referral Code    |       02        |                 IPG                  | 
|                       |    |   Referral Code    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Referral Code    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Referral Code    |       03        |                 PAYEEZY                  | 
|                       |    |   Referral Code    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Referral Code    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Referral Code    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Referral Code    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Referral Code    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Referral Code    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Referral Code    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Referral Code    |       B        |                 BREAD                  | 
|                       |    |   Referral Code    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Referral Code    |       Y        |                 YES                  | 
|                       |    |   Referral Code    |       01        |                 FIRST_API                  | 
|                       |    |   Referral Code    |       Y        |                 CHECKED                  | 
|                       |    |   Referral Code    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Referral Code    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Referral Code    |       00        |                 NONE                  | 

| VASVRUSRV| requestNewVruIdCd   |   Request New VRU Id For Compromised One    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Request New VRU Id For Compromised One    |       Y        |                 CHECKED                  | 
|                       |    |   Request New VRU Id For Compromised One    |       Y        |                 YES                  | 
|                       |    |   Request New VRU Id For Compromised One    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Request New VRU Id For Compromised One    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Request New VRU Id For Compromised One    |       00        |                 NONE                  | 
|                       |    |   Request New VRU Id For Compromised One    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Request New VRU Id For Compromised One    |       03        |                 PAYEEZY                  | 
|                       |    |   Request New VRU Id For Compromised One    |       1        |                 OPTED_OUT                  | 
|                       |    |   Request New VRU Id For Compromised One    |       02        |                 IPG                  | 
|                       |    |   Request New VRU Id For Compromised One    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Request New VRU Id For Compromised One    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Request New VRU Id For Compromised One    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Request New VRU Id For Compromised One    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Request New VRU Id For Compromised One    |       01        |                 FIRST_API                  | 
|                       |    |   Request New VRU Id For Compromised One    |       N        |                 NO                  | 
|                       |    |   Request New VRU Id For Compromised One    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Request New VRU Id For Compromised One    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Request New VRU Id For Compromised One    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Request New VRU Id For Compromised One    |       B        |                 BREAD                  | 
|                       |    |   Request New VRU Id For Compromised One    |       04        |                 UCOMM                  | 
|                       |    |   Request New VRU Id For Compromised One    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Request New VRU Id For Compromised One    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Request New VRU Id For Compromised One    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Request New VRU Id For Compromised One    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Request New VRU Id For Compromised One    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Request New VRU Id For Compromised One    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 

| VASSAMSPLS| rnwlAmtPaid   |   SAMS Club Renewal Amount Paid    |       01        |                 FDMS_POS                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       Y        |                 CHECKED                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       P        |                 PENDING                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       N        |                 NOT_CHECKED                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       A        |                 ACTIVE                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       03        |                 BLANK                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       C        |                 CANCEL                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       Y        |                 YES                  | 
|                       |    |   SAMS Club Renewal Amount Paid    |       N        |                 NO                  | 

| VASTAP2PE| rsavpki   |   rsavpki for Transarmor    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   rsavpki for Transarmor    |       Y        |                 YES                  | 
|                       |    |   rsavpki for Transarmor    |       01        |                 FIRST_API                  | 
|                       |    |   rsavpki for Transarmor    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   rsavpki for Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   rsavpki for Transarmor    |       1        |                 OPTED_OUT                  | 
|                       |    |   rsavpki for Transarmor    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   rsavpki for Transarmor    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   rsavpki for Transarmor    |       00        |                 NONE                  | 
|                       |    |   rsavpki for Transarmor    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   rsavpki for Transarmor    |       03        |                 PAYEEZY                  | 
|                       |    |   rsavpki for Transarmor    |       02        |                 IPG                  | 
|                       |    |   rsavpki for Transarmor    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   rsavpki for Transarmor    |       ABLS        |                 ABUELOS                  | 
|                       |    |   rsavpki for Transarmor    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   rsavpki for Transarmor    |       N        |                 NO                  | 
|                       |    |   rsavpki for Transarmor    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   rsavpki for Transarmor    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   rsavpki for Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   rsavpki for Transarmor    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   rsavpki for Transarmor    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   rsavpki for Transarmor    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   rsavpki for Transarmor    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   rsavpki for Transarmor    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   rsavpki for Transarmor    |       04        |                 UCOMM                  | 
|                       |    |   rsavpki for Transarmor    |       B        |                 BREAD                  | 
|                       |    |   rsavpki for Transarmor    |       P        |                 PRINT_ONLY                  | 

| VASTCKCP| tckCpPrcsInd   |   Process Indicator Telecheck CP    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Process Indicator Telecheck CP    |       A        |                 AGENT_ISV                  | 
|                       |    |   Process Indicator Telecheck CP    |       C        |                 CBS                  | 
|                       |    |   Process Indicator Telecheck CP    |       Y        |                 CHECKED                  | 
|                       |    |   Process Indicator Telecheck CP    |       Y        |                 YES                  | 
|                       |    |   Process Indicator Telecheck CP    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Process Indicator Telecheck CP    |       CM        |                 CMM                  | 
|                       |    |   Process Indicator Telecheck CP    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Process Indicator Telecheck CP    |       N        |                 NO                  | 
|                       | tckCpPrdct   |   Product for Telecheck CP    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Product for Telecheck CP    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Product for Telecheck CP    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Product for Telecheck CP    |       03        |                 PAYEEZY                  | 
|                       |    |   Product for Telecheck CP    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Product for Telecheck CP    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Product for Telecheck CP    |       N        |                 NO                  | 
|                       |    |   Product for Telecheck CP    |       Y        |                 YES                  | 
|                       |    |   Product for Telecheck CP    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Product for Telecheck CP    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Product for Telecheck CP    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Product for Telecheck CP    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Product for Telecheck CP    |       04        |                 UCOMM                  | 
|                       |    |   Product for Telecheck CP    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Product for Telecheck CP    |       02        |                 IPG                  | 
|                       |    |   Product for Telecheck CP    |       01        |                 FIRST_API                  | 
|                       |    |   Product for Telecheck CP    |       Y        |                 CHECKED                  | 
|                       |    |   Product for Telecheck CP    |       1        |                 OPTED_OUT                  | 
|                       |    |   Product for Telecheck CP    |       B        |                 BREAD                  | 
|                       |    |   Product for Telecheck CP    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Product for Telecheck CP    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Product for Telecheck CP    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Product for Telecheck CP    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Product for Telecheck CP    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Product for Telecheck CP    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Product for Telecheck CP    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Product for Telecheck CP    |       00        |                 NONE                  | 
|                       | tckCpServEntl   |   Service Entitlement for Telecheck CP    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       V        |                 MIVA                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       A        |                 ADD                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       C        |                 CANCEL                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       N        |                 NO                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       V        |                 VALUELINK                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       03        |                 MSI_APP                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       Y        |                 CHECKED                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       C        |                 CENPOS                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       C        |                 CLOVER                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       S        |                 SHOPIFY                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       X        |                 CARDX                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       T        |                 TEMPUS                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       D        |                 DELETE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       A        |                 ACTIVE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       O        |                 OTHER                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       3        |                 3DCART                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       M        |                 MAGENTO2                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       K        |                 KIBO                  | 
|                       |    |   Service Entitlement for Telecheck CP    |       Y        |                 YES                  | 
|                       | tckCpSettlInd   |   Settlement Indicator for Telecheck CP    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       Y        |                 CHECKED                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       N        |                 NO                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       01        |                 FDMS_POS                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       A        |                 ACTIVE                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       03        |                 BLANK                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       Y        |                 YES                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       P        |                 PENDING                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       02        |                 NON_FDMS_POS                  | 
|                       |    |   Settlement Indicator for Telecheck CP    |       C        |                 CANCEL                  | 
|                       | tckCpStatus   |   Program Status for Telecheck CP    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Telecheck CP    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Telecheck CP    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Telecheck CP    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Telecheck CP    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Telecheck CP    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Telecheck CP    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Telecheck CP    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Telecheck CP    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Telecheck CP    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Telecheck CP    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Telecheck CP    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Telecheck CP    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Telecheck CP    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Telecheck CP    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Telecheck CP    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Telecheck CP    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Telecheck CP    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Telecheck CP    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Telecheck CP    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Telecheck CP    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Telecheck CP    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Telecheck CP    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Telecheck CP    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Telecheck CP    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Telecheck CP    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Telecheck CP    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Telecheck CP    |       5        |                 PENDING_UPGRADE                  | 

| VASTEMPUS| tempusProgramStatus   |   Tempus Program Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Tempus Program Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Tempus Program Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Tempus Program Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Tempus Program Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Tempus Program Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Tempus Program Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Tempus Program Status    |       D        |                 DECLINED                  | 
|                       |    |   Tempus Program Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Tempus Program Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Tempus Program Status    |       L        |                 LIVE                  | 
|                       |    |   Tempus Program Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Tempus Program Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Tempus Program Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Tempus Program Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Tempus Program Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Tempus Program Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Tempus Program Status    |       A        |                 APPROVED                  | 
|                       |    |   Tempus Program Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Tempus Program Status    |       A        |                 ACTIVE                  | 
|                       |    |   Tempus Program Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Tempus Program Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Tempus Program Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Tempus Program Status    |       8        |                 ACTIVE                  | 
|                       |    |   Tempus Program Status    |       C        |                 CANCEL                  | 
|                       |    |   Tempus Program Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Tempus Program Status    |       R        |                 DENIED                  | 
|                       |    |   Tempus Program Status    |       A        |                 ACTIVE_SURCHARGING                  | 

| VASPERKA| term   |   Term    |       M        |                 MONTHLY                  | 
|                       |    |   Term    |       O        |                 OPTED_OUT                  | 
|                       |    |   Term    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Term    |       Y        |                 CHECKED                  | 
|                       |    |   Term    |       A        |                 PROVISIONED                  | 
|                       |    |   Term    |       A        |                 ANNUAL                  | 
|                       |    |   Term    |       P        |                 PENDING                  | 
|                       |    |   Term    |       I        |                 INITIATED                  | 
|                       |    |   Term    |       F        |                 FAILED                  | 

| VASBPMOB| terminalType01   |   Terminal Type 01 for BP Mobile    |       F        |                 FAILED                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       A        |                 PROVISIONED                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       U        |                 UPGRADE                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       I        |                 INITIATED                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       N        |                 NO                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       Y        |                 YES                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       R        |                 RENEWAL                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |               |                 NONE                  | 
|                       |    |   Terminal Type 01 for BP Mobile    |       N        |                 NEW                  | 
|                       | terminalType03   |   Terminal Type 03 for BP Mobile    |       P        |                 PENDING                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       O        |                 OPTED_OUT                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       A        |                 ANNUAL                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       M        |                 MONTHLY                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       F        |                 FAILED                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       Y        |                 CHECKED                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       I        |                 INITIATED                  | 
|                       |    |   Terminal Type 03 for BP Mobile    |       A        |                 PROVISIONED                  | 

| VASMERSRCH| thirdParty   |   Third Party for Merchant Surcharge Program    |       O        |                 OTHER                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       D        |                 DELETE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       K        |                 KIBO                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       X        |                 CARDX                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       03        |                 MSI_APP                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       C        |                 CENPOS                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       C        |                 CANCEL                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       Y        |                 YES                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       M        |                 MAGENTO2                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       A        |                 ADD                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       V        |                 VALUELINK                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       N        |                 NO                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       3        |                 3DCART                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       T        |                 TEMPUS                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       Y        |                 CHECKED                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       S        |                 SHOPIFY                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       A        |                 ACTIVE                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       V        |                 MIVA                  | 
|                       |    |   Third Party for Merchant Surcharge Program    |       C        |                 CLOVER                  | 

| VASTXNINS| transactionInsightBillingEffectiveDate   |   Billing Effective Date for Transaction Insights    |               |                                   | 
|                       | transactionInsightOfferingType   |   Offering Type for Transaction Insights    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Transaction Insights    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Transaction Insights    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Transaction Insights    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Transaction Insights    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Transaction Insights    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Transaction Insights    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Transaction Insights    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Transaction Insights    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Transaction Insights    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Transaction Insights    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Transaction Insights    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Transaction Insights    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Transaction Insights    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Transaction Insights    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Transaction Insights    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Transaction Insights    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Transaction Insights    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Transaction Insights    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Transaction Insights    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Transaction Insights    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Transaction Insights    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Transaction Insights    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Transaction Insights    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Transaction Insights    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Transaction Insights    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Transaction Insights    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Transaction Insights    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Transaction Insights    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Transaction Insights    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Transaction Insights    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Transaction Insights    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Transaction Insights    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Transaction Insights    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Transaction Insights    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Transaction Insights    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Transaction Insights    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Transaction Insights    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Transaction Insights    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Transaction Insights    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Transaction Insights    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Transaction Insights    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Transaction Insights    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Transaction Insights    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Transaction Insights    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Transaction Insights    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       | transactionInsightStatus   |   Program Status for Transaction Insights    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Transaction Insights    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Transaction Insights    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Transaction Insights    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Transaction Insights    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Transaction Insights    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Transaction Insights    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Transaction Insights    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Transaction Insights    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Transaction Insights    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Transaction Insights    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Transaction Insights    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Transaction Insights    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Transaction Insights    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Transaction Insights    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Transaction Insights    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Transaction Insights    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Transaction Insights    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Transaction Insights    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Transaction Insights    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Transaction Insights    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Transaction Insights    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Transaction Insights    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Transaction Insights    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Transaction Insights    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Transaction Insights    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Transaction Insights    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Transaction Insights    |       7        |                 FREE_TRIAL                  | 

| VASTAP2PE| transarmorP2peStatus   |   Transrmor P2PE Pragram Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       8        |                 ACTIVE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       A        |                 ACTIVE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       L        |                 LIVE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       C        |                 CANCEL                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       D        |                 DECLINED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       R        |                 DENIED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       A        |                 APPROVED                  | 
|                       |    |   Transrmor P2PE Pragram Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 

| VASTRNSARM| transarmorProgramstatus   |   Transarmor Program Status    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Transarmor Program Status    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Transarmor Program Status    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Transarmor Program Status    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Transarmor Program Status    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Transarmor Program Status    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Transarmor Program Status    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Transarmor Program Status    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Transarmor Program Status    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Transarmor Program Status    |       L        |                 LIVE                  | 
|                       |    |   Transarmor Program Status    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Transarmor Program Status    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Transarmor Program Status    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Transarmor Program Status    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Transarmor Program Status    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Transarmor Program Status    |       R        |                 DENIED                  | 
|                       |    |   Transarmor Program Status    |       C        |                 CANCEL                  | 
|                       |    |   Transarmor Program Status    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Transarmor Program Status    |       8        |                 ACTIVE                  | 
|                       |    |   Transarmor Program Status    |       D        |                 DECLINED                  | 
|                       |    |   Transarmor Program Status    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Transarmor Program Status    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Transarmor Program Status    |       A        |                 ACTIVE                  | 
|                       |    |   Transarmor Program Status    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Transarmor Program Status    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Transarmor Program Status    |       A        |                 APPROVED                  | 
|                       |    |   Transarmor Program Status    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Transarmor Program Status    |       Y        |                 DISCOVER_REVIEW                  | 
|                       | transarmorofferingType   |   Transarmor Offering Type    |       02        |                 NT_STANDARD                  | 
|                       |    |   Transarmor Offering Type    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Transarmor Offering Type    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Transarmor Offering Type    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Transarmor Offering Type    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Transarmor Offering Type    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Transarmor Offering Type    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Transarmor Offering Type    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Transarmor Offering Type    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Transarmor Offering Type    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Transarmor Offering Type    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Transarmor Offering Type    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Transarmor Offering Type    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Transarmor Offering Type    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Transarmor Offering Type    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Transarmor Offering Type    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Transarmor Offering Type    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Transarmor Offering Type    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Transarmor Offering Type    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Transarmor Offering Type    |       05        |                 PREMIUM                  | 
|                       |    |   Transarmor Offering Type    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Transarmor Offering Type    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Transarmor Offering Type    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Transarmor Offering Type    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Transarmor Offering Type    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 ELIGIBLE                  | 
|                       |    |   Transarmor Offering Type    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Transarmor Offering Type    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Transarmor Offering Type    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Transarmor Offering Type    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Transarmor Offering Type    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Transarmor Offering Type    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Transarmor Offering Type    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Transarmor Offering Type    |       03        |                 ESSENTIALS                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Transarmor Offering Type    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Transarmor Offering Type    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Transarmor Offering Type    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Transarmor Offering Type    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Transarmor Offering Type    |       06        |                 STANDARD                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Transarmor Offering Type    |       04        |                 ADVANCED                  | 
|                       |    |   Transarmor Offering Type    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   Transarmor Offering Type    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Transarmor Offering Type    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Transarmor Offering Type    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Transarmor Offering Type    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Transarmor Offering Type    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Transarmor Offering Type    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Transarmor Offering Type    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Transarmor Offering Type    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Transarmor Offering Type    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Transarmor Offering Type    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Transarmor Offering Type    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Transarmor Offering Type    |       03        |                 NT_HYBRID                  | 
|                       |    |   Transarmor Offering Type    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Transarmor Offering Type    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Transarmor Offering Type    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 

| VASTAP2PE| verifoneProtect   |   Verifone Protect for Transarmor    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Verifone Protect for Transarmor    |       S        |                 SHOPIFY                  | 
|                       |    |   Verifone Protect for Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Verifone Protect for Transarmor    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Verifone Protect for Transarmor    |       V        |                 MIVA                  | 
|                       |    |   Verifone Protect for Transarmor    |       T        |                 TEMPUS                  | 
|                       |    |   Verifone Protect for Transarmor    |       M        |                 MAGENTO2                  | 
|                       |    |   Verifone Protect for Transarmor    |       X        |                 CARDX                  | 
|                       |    |   Verifone Protect for Transarmor    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Verifone Protect for Transarmor    |       N        |                 NO                  | 
|                       |    |   Verifone Protect for Transarmor    |       Y        |                 YES                  | 
|                       |    |   Verifone Protect for Transarmor    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Verifone Protect for Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   Verifone Protect for Transarmor    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Verifone Protect for Transarmor    |       C        |                 CENPOS                  | 
|                       |    |   Verifone Protect for Transarmor    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Verifone Protect for Transarmor    |       C        |                 CANCEL                  | 
|                       |    |   Verifone Protect for Transarmor    |       A        |                 ACTIVE                  | 
|                       |    |   Verifone Protect for Transarmor    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Verifone Protect for Transarmor    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Verifone Protect for Transarmor    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Verifone Protect for Transarmor    |       V        |                 VALUELINK                  | 
|                       |    |   Verifone Protect for Transarmor    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Verifone Protect for Transarmor    |       C        |                 CLOVER                  | 
|                       |    |   Verifone Protect for Transarmor    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Verifone Protect for Transarmor    |       03        |                 MSI_APP                  | 
|                       |    |   Verifone Protect for Transarmor    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Verifone Protect for Transarmor    |       D        |                 DELETE                  | 
|                       |    |   Verifone Protect for Transarmor    |       A        |                 ADD                  | 
|                       |    |   Verifone Protect for Transarmor    |       3        |                 3DCART                  | 
|                       |    |   Verifone Protect for Transarmor    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Verifone Protect for Transarmor    |       K        |                 KIBO                  | 
|                       |    |   Verifone Protect for Transarmor    |       O        |                 OTHER                  | 
|                       | verifoneProtectWsp   |   Verifone Protect W/SP for  Transarmor    |       A        |                 AGENT_ISV                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       Y        |                 USE_PRIMARY_EMAIL                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       N        |                 NO                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       Y        |                 YES                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       Y        |                 CHECKED                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       CM        |                 CMM                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       N        |                 USE_USER_PROVIDED                  | 
|                       |    |   Verifone Protect W/SP for  Transarmor    |       C        |                 CBS                  | 

| VASVETPRG| veteransProgramType   |   Veterans Program Offering Type    |       ABLS        |                 ABUELOS                  | 
|                       |    |   Veterans Program Offering Type    |       UJUL        |                 UNCLE_JULIO                  | 
|                       |    |   Veterans Program Offering Type    |       BOJA        |                 BO_JANGLES                  | 
|                       |    |   Veterans Program Offering Type    |       N        |                 NO_REQUEST_OF_NEW_VRU                  | 
|                       |    |   Veterans Program Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Veterans Program Offering Type    |       Y        |                 CHECKED                  | 
|                       |    |   Veterans Program Offering Type    |       Y        |                 YES                  | 
|                       |    |   Veterans Program Offering Type    |       PFC        |                 PF_CHANGS                  | 
|                       |    |   Veterans Program Offering Type    |       Y        |                 NEW_VRU_ID_REQUESTED                  | 
|                       |    |   Veterans Program Offering Type    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Veterans Program Offering Type    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Veterans Program Offering Type    |       01        |                 FIRST_API                  | 
|                       |    |   Veterans Program Offering Type    |       2        |                 IAS_PRODUCT_EXCEPTION                  | 
|                       |    |   Veterans Program Offering Type    |       SPKL        |                 SPRINKLES                  | 
|                       |    |   Veterans Program Offering Type    |       03        |                 PAYEEZY                  | 
|                       |    |   Veterans Program Offering Type    |       C        |                 NEW_VRU_ID_COMPLETED                  | 
|                       |    |   Veterans Program Offering Type    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Veterans Program Offering Type    |       00        |                 NONE                  | 
|                       |    |   Veterans Program Offering Type    |       1        |                 OPTED_OUT                  | 
|                       |    |   Veterans Program Offering Type    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Veterans Program Offering Type    |       SBBQ        |                 SONNYS_BBQ                  | 
|                       |    |   Veterans Program Offering Type    |       04        |                 UCOMM                  | 
|                       |    |   Veterans Program Offering Type    |       02        |                 IPG                  | 
|                       |    |   Veterans Program Offering Type    |       USHG        |                 UNION_SQ_HOSPITAL                  | 
|                       |    |   Veterans Program Offering Type    |       FIBD        |                 FIREBIRDS                  | 
|                       |    |   Veterans Program Offering Type    |       N        |                 NO                  | 
|                       |    |   Veterans Program Offering Type    |       B        |                 BREAD                  | 
|                       | veteransProgramstatus   |   Veterans Program Account Status    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Veterans Program Account Status    |       Y        |                 YES                  | 
|                       |    |   Veterans Program Account Status    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Veterans Program Account Status    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Veterans Program Account Status    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Veterans Program Account Status    |       C        |                 CANCEL                  | 
|                       |    |   Veterans Program Account Status    |       T        |                 TEMPUS                  | 
|                       |    |   Veterans Program Account Status    |       N        |                 NO                  | 
|                       |    |   Veterans Program Account Status    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Veterans Program Account Status    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Veterans Program Account Status    |       A        |                 ACTIVE                  | 
|                       |    |   Veterans Program Account Status    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Veterans Program Account Status    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Veterans Program Account Status    |       3        |                 3DCART                  | 
|                       |    |   Veterans Program Account Status    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Veterans Program Account Status    |       Y        |                 CHECKED                  | 
|                       |    |   Veterans Program Account Status    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Veterans Program Account Status    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Veterans Program Account Status    |       X        |                 CARDX                  | 
|                       |    |   Veterans Program Account Status    |       V        |                 MIVA                  | 
|                       |    |   Veterans Program Account Status    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Veterans Program Account Status    |       V        |                 VALUELINK                  | 
|                       |    |   Veterans Program Account Status    |       A        |                 ADD                  | 
|                       |    |   Veterans Program Account Status    |       O        |                 OTHER                  | 
|                       |    |   Veterans Program Account Status    |       C        |                 CENPOS                  | 
|                       |    |   Veterans Program Account Status    |       03        |                 MSI_APP                  | 
|                       |    |   Veterans Program Account Status    |       K        |                 KIBO                  | 
|                       |    |   Veterans Program Account Status    |       M        |                 MAGENTO2                  | 
|                       |    |   Veterans Program Account Status    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Veterans Program Account Status    |       C        |                 CLOVER                  | 
|                       |    |   Veterans Program Account Status    |       S        |                 SHOPIFY                  | 
|                       |    |   Veterans Program Account Status    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Veterans Program Account Status    |       D        |                 DELETE                  | 

| VASNTWKTKN| visa   |   Visa Network Tokens    |       C        |                 CENPOS                  | 
|                       |    |   Visa Network Tokens    |       V        |                 MIVA                  | 
|                       |    |   Visa Network Tokens    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Visa Network Tokens    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Visa Network Tokens    |       S        |                 SHOPIFY                  | 
|                       |    |   Visa Network Tokens    |       V        |                 VALUELINK                  | 
|                       |    |   Visa Network Tokens    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Visa Network Tokens    |       Y        |                 CHECKED                  | 
|                       |    |   Visa Network Tokens    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Visa Network Tokens    |       A        |                 ACTIVE                  | 
|                       |    |   Visa Network Tokens    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Visa Network Tokens    |       D        |                 DELETE                  | 
|                       |    |   Visa Network Tokens    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Visa Network Tokens    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Visa Network Tokens    |       K        |                 KIBO                  | 
|                       |    |   Visa Network Tokens    |       03        |                 MSI_APP                  | 
|                       |    |   Visa Network Tokens    |       A        |                 ADD                  | 
|                       |    |   Visa Network Tokens    |       C        |                 CANCEL                  | 
|                       |    |   Visa Network Tokens    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 
|                       |    |   Visa Network Tokens    |       C        |                 CLOVER                  | 
|                       |    |   Visa Network Tokens    |       T        |                 TEMPUS                  | 
|                       |    |   Visa Network Tokens    |       N        |                 NO                  | 
|                       |    |   Visa Network Tokens    |       X        |                 CARDX                  | 
|                       |    |   Visa Network Tokens    |       3        |                 3DCART                  | 
|                       |    |   Visa Network Tokens    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Visa Network Tokens    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Visa Network Tokens    |       Y        |                 YES                  | 
|                       |    |   Visa Network Tokens    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Visa Network Tokens    |       O        |                 OTHER                  | 
|                       |    |   Visa Network Tokens    |       M        |                 MAGENTO2                  | 
|                       |    |   Visa Network Tokens    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Visa Network Tokens    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Visa Network Tokens    |       01        |                 CLOVER_ONLINE_STORE                  | 

| VASVISAACTUPD| visaAcctUpdStatus   |   Program Status for VISA Account Update    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for VISA Account Update    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for VISA Account Update    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for VISA Account Update    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for VISA Account Update    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for VISA Account Update    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for VISA Account Update    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for VISA Account Update    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for VISA Account Update    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for VISA Account Update    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for VISA Account Update    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for VISA Account Update    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for VISA Account Update    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for VISA Account Update    |       R        |                 DENIED                  | 
|                       |    |   Program Status for VISA Account Update    |       L        |                 LIVE                  | 
|                       |    |   Program Status for VISA Account Update    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for VISA Account Update    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for VISA Account Update    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for VISA Account Update    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for VISA Account Update    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for VISA Account Update    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for VISA Account Update    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for VISA Account Update    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for VISA Account Update    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for VISA Account Update    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for VISA Account Update    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for VISA Account Update    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for VISA Account Update    |       C        |                 CANCEL                  | 

| VASVISAACTFNDTRX| visaActFndOfferingType   |   Offering Type for Visa Account Funding    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Visa Account Funding    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Visa Account Funding    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Visa Account Funding    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Visa Account Funding    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Visa Account Funding    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Visa Account Funding    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Account Funding    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Visa Account Funding    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Visa Account Funding    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Visa Account Funding    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Visa Account Funding    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Visa Account Funding    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Account Funding    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Visa Account Funding    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Account Funding    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Visa Account Funding    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Visa Account Funding    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Visa Account Funding    |       RD        |                 RAPID_DEPOSIT                  | 
|                       | visaActFndStatus   |   Program Status for Visa Account Funding    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Visa Account Funding    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Visa Account Funding    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Visa Account Funding    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Visa Account Funding    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Visa Account Funding    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Visa Account Funding    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Visa Account Funding    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Visa Account Funding    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Visa Account Funding    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Visa Account Funding    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Visa Account Funding    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Visa Account Funding    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Visa Account Funding    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Visa Account Funding    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Visa Account Funding    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Visa Account Funding    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Visa Account Funding    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Status for Visa Account Funding    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Visa Account Funding    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Visa Account Funding    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Visa Account Funding    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Visa Account Funding    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Visa Account Funding    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Visa Account Funding    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Visa Account Funding    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Visa Account Funding    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Visa Account Funding    |       A        |                 ACTIVE                  | 

| VASVISACHKOUT| visaChkOutStatus   |   Program Sttatus for Visa Check Out    |       5        |                 PENDING_UPGRADE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       8        |                 ACTIVE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       A        |                 ACTIVE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       R        |                 DENIED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       D        |                 DECLINED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       A        |                 APPROVED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       C        |                 CANCEL                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       L        |                 LIVE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Sttatus for Visa Check Out    |       N        |                 APPLY_FALL_BACK                  | 

| VASVISAOCT| visaOctOfferingType   |   Offering Type for Visa Oct    |       01        |                 ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Oct    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   Offering Type for Visa Oct    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   Offering Type for Visa Oct    |       03        |                 ESSENTIALS                  | 
|                       |    |   Offering Type for Visa Oct    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   Offering Type for Visa Oct    |       04        |                 ADVANCED                  | 
|                       |    |   Offering Type for Visa Oct    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   Offering Type for Visa Oct    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Visa Oct    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   Offering Type for Visa Oct    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   Offering Type for Visa Oct    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   Offering Type for Visa Oct    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   Offering Type for Visa Oct    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Oct    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   Offering Type for Visa Oct    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   Offering Type for Visa Oct    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Oct    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Offering Type for Visa Oct    |       B        |                 BLACK_LISTED                  | 
|                       |    |   Offering Type for Visa Oct    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   Offering Type for Visa Oct    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   Offering Type for Visa Oct    |       00        |                 NOT_APPLICABLE                  | 
|                       |    |   Offering Type for Visa Oct    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Oct    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   Offering Type for Visa Oct    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   Offering Type for Visa Oct    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Visa Oct    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   Offering Type for Visa Oct    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   Offering Type for Visa Oct    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   Offering Type for Visa Oct    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   Offering Type for Visa Oct    |       03        |                 NT_HYBRID                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Oct    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   Offering Type for Visa Oct    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   Offering Type for Visa Oct    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Oct    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   Offering Type for Visa Oct    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   Offering Type for Visa Oct    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   Offering Type for Visa Oct    |       06        |                 STANDARD                  | 
|                       |    |   Offering Type for Visa Oct    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   Offering Type for Visa Oct    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   Offering Type for Visa Oct    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   Offering Type for Visa Oct    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   Offering Type for Visa Oct    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   Offering Type for Visa Oct    |       W        |                 WHITE_LISTED                  | 
|                       |    |   Offering Type for Visa Oct    |       05        |                 PREMIUM                  | 
|                       |    |   Offering Type for Visa Oct    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   Offering Type for Visa Oct    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   Offering Type for Visa Oct    |       02        |                 NT_STANDARD                  | 
|                       |    |   Offering Type for Visa Oct    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   Offering Type for Visa Oct    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   Offering Type for Visa Oct    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   Offering Type for Visa Oct    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   Offering Type for Visa Oct    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   Offering Type for Visa Oct    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   Offering Type for Visa Oct    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   Offering Type for Visa Oct    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   Offering Type for Visa Oct    |       RD        |                 RAPID_DEPOSIT                  | 
|                       | visaOctStatus   |   Program Status for Visa Oct    |       Y        |                 DISCOVER_REVIEW                  | 
|                       |    |   Program Status for Visa Oct    |       1        |                 SUBSCRIBED                  | 
|                       |    |   Program Status for Visa Oct    |       N        |                 NEW_APPLICATION                  | 
|                       |    |   Program Status for Visa Oct    |       C        |                 CANCEL                  | 
|                       |    |   Program Status for Visa Oct    |       3        |                 PENDING_UNCONTACTED                  | 
|                       |    |   Program Status for Visa Oct    |       A        |                 ACTIVE_SURCHARGING                  | 
|                       |    |   Program Status for Visa Oct    |       Y        |                 MERCH_EQ_EMV_CAPABLE                  | 
|                       |    |   Program Status for Visa Oct    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   Program Status for Visa Oct    |       C        |                 CANCEL_SURCHARGING                  | 
|                       |    |   Program Status for Visa Oct    |       M        |                 MIX_EMV_AND_NON_EMV                  | 
|                       |    |   Program Status for Visa Oct    |       I        |                 IN_PROGRESS                  | 
|                       |    |   Program Status for Visa Oct    |       9        |                 CANCELLED_BY_MERCHANT                  | 
|                       |    |   Program Status for Visa Oct    |       C        |                 CANCELLED_BY_FD                  | 
|                       |    |   Program Status for Visa Oct    |       8        |                 ACTIVE                  | 
|                       |    |   Program Status for Visa Oct    |       6        |                 NO_RESPONSE                  | 
|                       |    |   Program Status for Visa Oct    |       2        |                 UNSUBSCRIBED                  | 
|                       |    |   Program Status for Visa Oct    |       4        |                 PENDING_CONTACTED                  | 
|                       |    |   Program Status for Visa Oct    |       A        |                 ACTIVE                  | 
|                       |    |   Program Status for Visa Oct    |       Y        |                 DONT_APPLY_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Visa Oct    |       L        |                 LIVE                  | 
|                       |    |   Program Status for Visa Oct    |       D        |                 DECLINED                  | 
|                       |    |   Program Status for Visa Oct    |       N        |                 APPLY_FALL_BACK                  | 
|                       |    |   Program Status for Visa Oct    |       7        |                 FREE_TRIAL                  | 
|                       |    |   Program Status for Visa Oct    |       A        |                 APPROVED                  | 
|                       |    |   Program Status for Visa Oct    |       R        |                 DENIED                  | 
|                       |    |   Program Status for Visa Oct    |       Y        |                 DO_NOT_APPLY_FALLBACK                  | 
|                       |    |   Program Status for Visa Oct    |       N        |                 ALLOW_DEBIT_FLAGS                  | 
|                       |    |   Program Status for Visa Oct    |       5        |                 PENDING_UPGRADE                  | 

| VASVRUSRV| vruServiceofferingType   |   VRU Services Offering Type    |       C04        |                 GAMING_PAYMENTS                  | 
|                       |    |   VRU Services Offering Type    |       BI        |                 BANK_INITIATED_P2P                  | 
|                       |    |   VRU Services Offering Type    |       MI        |                 MNY_TRFR_MERCH_INIT                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 AUTHORIZATION_DATA                  | 
|                       |    |   VRU Services Offering Type    |       AA        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   VRU Services Offering Type    |       02        |                 FRAUD_DETECT_SMB_TRIAL                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 STANDARD_OFFERING                  | 
|                       |    |   VRU Services Offering Type    |       C57        |                 RAPID_DEPOSIT                  | 
|                       |    |   VRU Services Offering Type    |       GD        |                 GOVT_DISBURSEMENTS                  | 
|                       |    |   VRU Services Offering Type    |       PD        |                 PAYRL_PNSN_DISBRSMNT                  | 
|                       |    |   VRU Services Offering Type    |       C58        |                 CASH_2_ATM                  | 
|                       |    |   VRU Services Offering Type    |       F64        |                 TR_OWN_DB_OR_PP_CARD                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 FRAUD_DETECT_SMB                  | 
|                       |    |   VRU Services Offering Type    |       02        |                 SETTLEMENT_DATA                  | 
|                       |    |   VRU Services Offering Type    |       03        |                 ESSENTIALS                  | 
|                       |    |   VRU Services Offering Type    |       FT        |                 FUNDS_TRANSFER                  | 
|                       |    |   VRU Services Offering Type    |       F54        |                 PYMNT_OF_OWN_CC_BILL                  | 
|                       |    |   VRU Services Offering Type    |       MD        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   VRU Services Offering Type    |       C07        |                 PERSON_TO_PERSON                  | 
|                       |    |   VRU Services Offering Type    |       TU        |                 PREPAID_LOADS                  | 
|                       |    |   VRU Services Offering Type    |       F53        |                 AGENT_CASH_OUT                  | 
|                       |    |   VRU Services Offering Type    |       BI        |                 BANK_INITIATED_TRANS                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 ELIGIBLE                  | 
|                       |    |   VRU Services Offering Type    |       03        |                 NT_HYBRID                  | 
|                       |    |   VRU Services Offering Type    |       06        |                 STANDARD                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 CUP_ELIGIBLE                  | 
|                       |    |   VRU Services Offering Type    |       F08        |                 P2P_TRANSFER_TO_CARD                  | 
|                       |    |   VRU Services Offering Type    |       F55        |                 BUS_DISBURS_TO_CARD                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 NT_ON_THE_GO                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 ALIPAY_ELIGIBLE                  | 
|                       |    |   VRU Services Offering Type    |       W        |                 WHITE_LISTED                  | 
|                       |    |   VRU Services Offering Type    |       05        |                 PREMIUM                  | 
|                       |    |   VRU Services Offering Type    |       C52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   VRU Services Offering Type    |       BP        |                 NON-CARD_BILL_PAY                  | 
|                       |    |   VRU Services Offering Type    |       B        |                 BLACK_LISTED                  | 
|                       |    |   VRU Services Offering Type    |       P1        |                 FD_DSCV_PROMO                  | 
|                       |    |   VRU Services Offering Type    |       C59        |                 CASH_2_CARD                  | 
|                       |    |   VRU Services Offering Type    |       FD        |                 FUNDS_DISBURSEMENTS                  | 
|                       |    |   VRU Services Offering Type    |       OG        |                 ONLINE_GAMBLING                  | 
|                       |    |   VRU Services Offering Type    |       CB        |                 CREDIT_CARD_BILL_PAY                  | 
|                       |    |   VRU Services Offering Type    |       02        |                 NT_STANDARD                  | 
|                       |    |   VRU Services Offering Type    |       PP        |                 PERSON_TO_PERSON                  | 
|                       |    |   VRU Services Offering Type    |       F61        |                 STAGED_WALLET_LOAD                  | 
|                       |    |   VRU Services Offering Type    |       02        |                 NOT_ELIGIBLE_ACQ_ON                  | 
|                       |    |   VRU Services Offering Type    |       CD        |                 CASH_DEPOSIT                  | 
|                       |    |   VRU Services Offering Type    |       C55        |                 MERCH_DISBURSEMENTS                  | 
|                       |    |   VRU Services Offering Type    |       F52        |                 ACCOUNT_TO_ACCOUNT                  | 
|                       |    |   VRU Services Offering Type    |       BB        |                 BUSINESS_TO_BUSINESS                  | 
|                       |    |   VRU Services Offering Type    |       LO        |                 LOYALTY_N_OFFERS                  | 
|                       |    |   VRU Services Offering Type    |       F07        |                 P2P_TRANSFER                  | 
|                       |    |   VRU Services Offering Type    |       C56        |                 GOV-NPROF_DISBRMTS                  | 
|                       |    |   VRU Services Offering Type    |       GP        |                 GAMBLING_PAYOUT                  | 
|                       |    |   VRU Services Offering Type    |       C53        |                 AGENT_CASH_OUT                  | 
|                       |    |   VRU Services Offering Type    |       04        |                 ADVANCED                  | 
|                       |    |   VRU Services Offering Type    |       C54        |                 CREDIT_CARD_BILL_PMT                  | 
|                       |    |   VRU Services Offering Type    |       C65        |                 BUS_TO_BUS_TRANSFER                  | 
|                       |    |   VRU Services Offering Type    |       03        |                 AUTH_AND_SETTLEMENT                  | 
|                       |    |   VRU Services Offering Type    |       F65        |                 GEN_B2B_TRAN_TO_CARD                  | 
|                       |    |   VRU Services Offering Type    |       RD        |                 RAPID_DEPOSIT                  | 
|                       |    |   VRU Services Offering Type    |       WT        |                 WALLET_TRANSFER                  | 
|                       |    |   VRU Services Offering Type    |       01        |                 EMV_CAMPAIGN                  | 
|                       |    |   VRU Services Offering Type    |       00        |                 NOT_APPLICABLE                  | 

| VASPAYEEZY| webStore   |   Web Store    |       P        |                 PRINT_ONLY                  | 
|                       |    |   Web Store    |       Y        |                 CHECKED                  | 
|                       |    |   Web Store    |       V        |                 MIVA                  | 
|                       |    |   Web Store    |       S        |                 SHOPIFY                  | 
|                       |    |   Web Store    |       3        |                 3DCART                  | 
|                       |    |   Web Store    |       B        |                 ONLINE_AND_PRINT                  | 
|                       |    |   Web Store    |       O        |                 OTHER                  | 
|                       |    |   Web Store    |       S        |                 SNAPPAY_CARDX                  | 
|                       |    |   Web Store    |       M        |                 MAGENTO2                  | 
|                       |    |   Web Store    |       02        |                 MSI_EXPRESS                  | 
|                       |    |   Web Store    |       K        |                 KIBO                  | 
|                       |    |   Web Store    |       X        |                 CARDX                  | 
|                       |    |   Web Store    |       O        |                 ONLINE_ONLY                  | 
|                       |    |   Web Store    |       D        |                 DELETE                  | 
|                       |    |   Web Store    |       SF        |                 SALESFORCE_COMMERCE                  | 
|                       |    |   Web Store    |       B        |                 BIGCOMMERCE                  | 
|                       |    |   Web Store    |       NA        |                 NOT_APPLICABLE                  | 
|                       |    |   Web Store    |       01        |                 MAIN_STREET_INSIGHTS                  | 
|                       |    |   Web Store    |       N        |                 NO                  | 
|                       |    |   Web Store    |       T        |                 TEMPUS                  | 
|                       |    |   Web Store    |       N        |                 NOT_CHECKED                  | 
|                       |    |   Web Store    |       Y        |                 YES                  | 
|                       |    |   Web Store    |       A        |                 ACTIVE                  | 
|                       |    |   Web Store    |       03        |                 MSI_APP                  | 
|                       |    |   Web Store    |       C        |                 CENPOS                  | 
|                       |    |   Web Store    |       01        |                 CLOVER_ONLINE_STORE                  | 
|                       |    |   Web Store    |       A        |                 ADD                  | 
|                       |    |   Web Store    |       V        |                 VALUELINK                  | 
|                       |    |   Web Store    |       C        |                 CLOVER                  | 
|                       |    |   Web Store    |       C        |                 CANCEL                  | 
|                       |    |   Web Store    |       N        |                 ORACLE_NET_SUITE                  | 
|                       |    |   Web Store    |       W        |                 WOOCOMMERCE                  | 
|                       |    |   Web Store    |       N        |                 NON_SURCHARGE_SNAPPAY_CARDX                  | 

<!-- type: tab-end -->
