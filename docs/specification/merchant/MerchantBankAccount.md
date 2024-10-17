# Merchant Bank Account

* **Description**: Essential information about merchant bank account, including account number, account type, and contact information.
* **API schema**: `merchantAccounts`
* **Table Name**: `UMM.MERCHANT_BANK_ACCOUNT`

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |      12       |    12      |    Required     | Required     | Required |    Required     |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required |    NA         |

<!-- type: tab-end -->
---

### PLATFORM_CODE

* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     |
| OMNIPAY26     |  Omnipay Backend ( GMA)      |
| SOUTH     |     South  Backend |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->
---

### SEQUENCE_NUMBER

* Description: ABA/DDA occurrence sequence number of a bank.
* API field: `sequenceNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  |     1        |    1       |    Available     | Required     |  Allowed  |    NA    |

* SEQUENCE_NUMBER will be used to update bank detail associated with a specific bank account for North backend platform

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     1st Bank Account    |
| 2     |     2nd Bank Account   |
| 3     |     3rd bank Account   |
| 4     |     4th Bank Account   |
| 5     |     5th Bank Account   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  |     1        |    1       |    Available     | Required     |  Allowed  |    NA    |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     1st Bank Account    |
| 2     |     2nd Bank Account   |
| 3     |     3rd bank Account   |
| 4     |     4th Bank Account   |
| 5     |     5th Bank Account   |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    4        |    Available| NA           |  NA          |    NA        |

<!-- type: tab-end -->
---

### ACCT_USAGE_CODE

* Description: Code that indicate the usage/purpose of an account.
* API field: `accountUsageCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     |   Required   | Allowed  |  NA         |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| FUNDING     |     Funding Bank Account  |
| LEASING     |     Leasing Bank Account   |
| PAR_PAYABLE | Account Usage Code |
| APM_PAR_PAYABLE | Account Usage Code |
| ACQ_DISP_PAYABLE | Account Usage Code |
| DINERS_MERCH_PAYABLE | Account Usage Code |
| INTERBANK_SUSP_PAYABLE | Account Usage Code |
| AMEX_MERCH_PAYABLE | Account Usage Code |
| SM_PAR_PAYABLE | Account Usage Code |
| CUP_MERCH_PAYABLE | Account Usage Code |
| FEE_COLLECT_PAYABLE | Account Usage Code |
| MERCH_RSRV_PAYABLE | Account Usage Code |
| FEE_COLLECT_PAYABLE | Account Usage Code |
| MERCH_PYMT_PAYABLE | Account Usage Code |
| APM_PAYABLE | Account Usage Code |
| VISA_PAR_PAYABLE | Account Usage Code |
| TREASURY_PYMT_MC_PAYABLE | Account Usage Code |
| WRITEOFF_SP_PAYABLE | Account Usage Code |
| FEDERAL_TAX_PAYABLE | Account Usage Code |
| TREASURY_PYMT_VISA_PAYABLE | Account Usage Code |
| FEE_COLL_INET_PAYABLE | Account Usage Code |
| TREASURY_PYMT_U_PAYABLE | Account Usage Code |
| CHBK_HOLD_PAYABLE | Account Usage Code |
| PAGOBANCOMAT_PAYABLE | Account Usage Code |
| PAYMENT_SUSPENSE_PAYABLE | Account Usage Code |
| MERCHANT_HOLD_PAYABLE | Account Usage Code |
| PAR_DR_PAYABLE | Account Usage Code |
| MANUAL_ADJUSTMENTS_PAYABLE | Account Usage Code |
| INTERBANK_SUSP_VISA_PAYABLE | Account Usage Code |
| TREASURY_PYMT_FDELGBP_PAYABLE | Account Usage Code |
| MC_PAR_PAYABLE | Account Usage Code |
| PAR_HOLDING_PAYABLE | Account Usage Code |
| FX_ROUNDING_DIFF_PAYABLE | Account Usage Code |
| TREASURY_PYMT_ALL_PAYABLE | Account Usage Code |
| FEE_COLL_VISA_PAYABLE | Account Usage Code |
| MERCH_FACTOR_PAYABLE | Account Usage Code |
| STATE_TAX_PAYABLE | Account Usage Code |
| FEE_HOLD_BCMC_PAYABLE | Account Usage Code |
| FEXCO_COMM_REVENUE_PAYABLE | Account Usage Code |
| PAR_BCMC_PAYABLE | Account Usage Code |
| INTEREST_RECEIVABLE_PAYABLE | Account Usage Code |
| FEE_COLL_BCMC_PAYABLE | Account Usage Code |
| MERC_ROLLIN_RESERVE_PAYABLE | Account Usage Code |
| WRITEOFF_ACQ_PAYABLE | Account Usage Code |
| MERCH_COMM_REVENUE_PAYABLE | Account Usage Code |
| VISA_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTED_SOURCE_PAYABLE | Account Usage Code |
| FX_PL_CHARGEBACK_2_PAYABLE | Account Usage Code |
| TREASURY_PYMT_EUR_PAYABLE | Account Usage Code |
| FEE_COLL_IPM_PAYABLE | Account Usage Code |
| VAT_HOLD_PAYABLE | Account Usage Code |
| FEE_COLL_ECCF_PAYABLE | Account Usage Code |
| TREASURY_PYMT_BAMS_PAYABLE | Account Usage Code |
| ACQ_COMM_REVENUE_PAYABLE | Account Usage Code |
| INTERCHANGE_REJ_SUSP_PAYABLE | Account Usage Code |
| REJECTS_VISA_PAYABLE | Account Usage Code |
| FX_PI_CHARGEBACK_PAYABLE | Account Usage Code |
| REJECTS_IPM_PAYABLE | Account Usage Code |
| REJECTS_ECCF_PAYABLE | Account Usage Code |
| MERCHANT_BILLBACK_PAYABLE | Account Usage Code |
| IDEAL_PAR_PAYABLE | Account Usage Code |
| SP_PAYMENT_PAYABLE | Account Usage Code |
| JCB_MERCHANT_PAYABLE | Account Usage Code |
| AMEX_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTS_INET_PAYABLE | Account Usage Code |
| TREASURY_PYMT_WELLS_PAYABLE | Account Usage Code |
| TREASURY_PYMT_BASECAD_PAYABLE | Account Usage Code |
| FEE_HOLD_PAYABLE | Account Usage Code |
| MC_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTED_DESC_PAYABLE | Account Usage Code |
| GST_COLLECT_PAYABLE | Account Usage Code |
| VEASE_FUND_CLEAR_PAYABLE | Account Usage Code |
| PAR_RECEIVABLE | Account Usage Code |
| APM_PAR_RECEIVABLE | Account Usage Code |
| ACQ_DISP_RECEIVABLE | Account Usage Code |
| DINERS_MERCH_RECEIVABLE | Account Usage Code |
| INTERBANK_SUSP_RECEIVABLE | Account Usage Code |
| AMEX_MERCH_RECEIVABLE | Account Usage Code |
| SM_PAR_RECEIVABLE | Account Usage Code |
| CUP_MERCH_RECEIVABLE | Account Usage Code |
| FEE_COLLECT_RECEIVABLE | Account Usage Code |
| MERCH_RSRV_RECEIVABLE | Account Usage Code |
| FEE_COLLECT_RECEIVABLE | Account Usage Code |
| MERCH_PYMT_RECEIVABLE | Account Usage Code |
| APM_RECEIVABLE | Account Usage Code |
| VISA_PAR_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_MC_RECEIVABLE | Account Usage Code |
| WRITEOFF_SP_RECEIVABLE | Account Usage Code |
| FEDERAL_TAX_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_VISA_RECEIVABLE | Account Usage Code |
| FEE_COLL_INET_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_U_RECEIVABLE | Account Usage Code |
| CHBK_HOLD_RECEIVABLE | Account Usage Code |
| PAGOBANCOMAT_RECEIVABLE | Account Usage Code |
| PAYMENT_SUSPENSE_RECEIVABLE | Account Usage Code |
| MERCHANT_HOLD_RECEIVABLE | Account Usage Code |
| PAR_DR_RECEIVABLE | Account Usage Code |
| MANUAL_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| INTERBANK_SUSP_VISA_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_FDELGBP_RECEIVABLE | Account Usage Code |
| MC_PAR_RECEIVABLE | Account Usage Code |
| PAR_HOLDING_RECEIVABLE | Account Usage Code |
| FX_ROUNDING_DIFF_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_ALL_RECEIVABLE | Account Usage Code |
| FEE_COLL_VISA_RECEIVABLE | Account Usage Code |
| MERCH_FACTOR_RECEIVABLE | Account Usage Code |
| STATE_TAX_RECEIVABLE | Account Usage Code |
| FEE_HOLD_BCMC_RECEIVABLE | Account Usage Code |
| FEXCO_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| PAR_BCMC_RECEIVABLE | Account Usage Code |
| INTEREST_RECEIVABLE_RECEIVABLE | Account Usage Code |
| FEE_COLL_BCMC_RECEIVABLE | Account Usage Code |
| MERC_ROLLIN_RESERVE_RECEIVABLE | Account Usage Code |
| WRITEOFF_ACQ_RECEIVABLE | Account Usage Code |
| MERCH_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| VISA_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTED_SOURCE_RECEIVABLE | Account Usage Code |
| FX_PL_CHARGEBACK_2_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_EUR_RECEIVABLE | Account Usage Code |
| FEE_COLL_IPM_RECEIVABLE | Account Usage Code |
| VAT_HOLD_RECEIVABLE | Account Usage Code |
| FEE_COLL_ECCF_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_BAMS_RECEIVABLE | Account Usage Code |
| ACQ_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| INTERCHANGE_REJ_SUSP_RECEIVABLE | Account Usage Code |
| REJECTS_VISA_RECEIVABLE | Account Usage Code |
| FX_PI_CHARGEBACK_RECEIVABLE | Account Usage Code |
| REJECTS_IPM_RECEIVABLE | Account Usage Code |
| REJECTS_ECCF_RECEIVABLE | Account Usage Code |
| MERCHANT_BILLBACK_RECEIVABLE | Account Usage Code |
| IDEAL_PAR_RECEIVABLE | Account Usage Code |
| SP_PAYMENT_RECEIVABLE | Account Usage Code |
| JCB_MERCHANT_RECEIVABLE | Account Usage Code |
| AMEX_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTS_INET_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_WELLS_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_BASECAD_RECEIVABLE | Account Usage Code |
| FEE_HOLD_RECEIVABLE | Account Usage Code |
| MC_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTED_DESC_RECEIVABLE | Account Usage Code |
| GST_COLLECT_RECEIVABLE | Account Usage Code |
| VEASE_FUND_CLEAR_RECEIVABLE | Account Usage Code |
| EFTPOS_PYMT | Account Usage Code |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     |   Required   | NA  |  NA         |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| FUNDING     |     Funding Bank Account   |
| LEASING     |     Leasing Bank Account    |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     |   Required   | NA  |  NA              |

* ACCT_USAGE_CODE will be used to update bank detail associated with a specific bank account for GMA (Omnipay) backend platform. The valid values for ACCT_USAGE_CODE is applicable for both PAYABLE and RECEIVABLE and hence, they have been noted separately below. This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| PAR_PAYABLE | Account Usage Code |
| APM_PAR_PAYABLE | Account Usage Code |
| ACQ_DISP_PAYABLE | Account Usage Code |
| DINERS_MERCH_PAYABLE | Account Usage Code |
| INTERBANK_SUSP_PAYABLE | Account Usage Code |
| AMEX_MERCH_PAYABLE | Account Usage Code |
| SM_PAR_PAYABLE | Account Usage Code |
| CUP_MERCH_PAYABLE | Account Usage Code |
| FEE_COLLECT_PAYABLE | Account Usage Code |
| MERCH_RSRV_PAYABLE | Account Usage Code |
| FEE_COLLECT_PAYABLE | Account Usage Code |
| MERCH_PYMT_PAYABLE | Account Usage Code |
| APM_PAYABLE | Account Usage Code |
| VISA_PAR_PAYABLE | Account Usage Code |
| TREASURY_PYMT_MC_PAYABLE | Account Usage Code |
| WRITEOFF_SP_PAYABLE | Account Usage Code |
| FEDERAL_TAX_PAYABLE | Account Usage Code |
| TREASURY_PYMT_VISA_PAYABLE | Account Usage Code |
| FEE_COLL_INET_PAYABLE | Account Usage Code |
| TREASURY_PYMT_U_PAYABLE | Account Usage Code |
| CHBK_HOLD_PAYABLE | Account Usage Code |
| PAGOBANCOMAT_PAYABLE | Account Usage Code |
| PAYMENT_SUSPENSE_PAYABLE | Account Usage Code |
| MERCHANT_HOLD_PAYABLE | Account Usage Code |
| PAR_DR_PAYABLE | Account Usage Code |
| MANUAL_ADJUSTMENTS_PAYABLE | Account Usage Code |
| INTERBANK_SUSP_VISA_PAYABLE | Account Usage Code |
| TREASURY_PYMT_FDELGBP_PAYABLE | Account Usage Code |
| MC_PAR_PAYABLE | Account Usage Code |
| PAR_HOLDING_PAYABLE | Account Usage Code |
| FX_ROUNDING_DIFF_PAYABLE | Account Usage Code |
| TREASURY_PYMT_ALL_PAYABLE | Account Usage Code |
| FEE_COLL_VISA_PAYABLE | Account Usage Code |
| MERCH_FACTOR_PAYABLE | Account Usage Code |
| STATE_TAX_PAYABLE | Account Usage Code |
| FEE_HOLD_BCMC_PAYABLE | Account Usage Code |
| FEXCO_COMM_REVENUE_PAYABLE | Account Usage Code |
| PAR_BCMC_PAYABLE | Account Usage Code |
| INTEREST_RECEIVABLE_PAYABLE | Account Usage Code |
| FEE_COLL_BCMC_PAYABLE | Account Usage Code |
| MERC_ROLLIN_RESERVE_PAYABLE | Account Usage Code |
| WRITEOFF_ACQ_PAYABLE | Account Usage Code |
| MERCH_COMM_REVENUE_PAYABLE | Account Usage Code |
| VISA_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTED_SOURCE_PAYABLE | Account Usage Code |
| FX_PL_CHARGEBACK_2_PAYABLE | Account Usage Code |
| TREASURY_PYMT_EUR_PAYABLE | Account Usage Code |
| FEE_COLL_IPM_PAYABLE | Account Usage Code |
| VAT_HOLD_PAYABLE | Account Usage Code |
| FEE_COLL_ECCF_PAYABLE | Account Usage Code |
| TREASURY_PYMT_BAMS_PAYABLE | Account Usage Code |
| ACQ_COMM_REVENUE_PAYABLE | Account Usage Code |
| INTERCHANGE_REJ_SUSP_PAYABLE | Account Usage Code |
| REJECTS_VISA_PAYABLE | Account Usage Code |
| FX_PI_CHARGEBACK_PAYABLE | Account Usage Code |
| REJECTS_IPM_PAYABLE | Account Usage Code |
| REJECTS_ECCF_PAYABLE | Account Usage Code |
| MERCHANT_BILLBACK_PAYABLE | Account Usage Code |
| IDEAL_PAR_PAYABLE | Account Usage Code |
| SP_PAYMENT_PAYABLE | Account Usage Code |
| JCB_MERCHANT_PAYABLE | Account Usage Code |
| AMEX_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTS_INET_PAYABLE | Account Usage Code |
| TREASURY_PYMT_WELLS_PAYABLE | Account Usage Code |
| TREASURY_PYMT_BASECAD_PAYABLE | Account Usage Code |
| FEE_HOLD_PAYABLE | Account Usage Code |
| MC_ADJUSTMENTS_PAYABLE | Account Usage Code |
| REJECTED_DESC_PAYABLE | Account Usage Code |
| GST_COLLECT_PAYABLE | Account Usage Code |
| VEASE_FUND_CLEAR_PAYABLE | Account Usage Code |
| PAR_RECEIVABLE | Account Usage Code |
| APM_PAR_RECEIVABLE | Account Usage Code |
| ACQ_DISP_RECEIVABLE | Account Usage Code |
| DINERS_MERCH_RECEIVABLE | Account Usage Code |
| INTERBANK_SUSP_RECEIVABLE | Account Usage Code |
| AMEX_MERCH_RECEIVABLE | Account Usage Code |
| SM_PAR_RECEIVABLE | Account Usage Code |
| CUP_MERCH_RECEIVABLE | Account Usage Code |
| FEE_COLLECT_RECEIVABLE | Account Usage Code |
| MERCH_RSRV_RECEIVABLE | Account Usage Code |
| FEE_COLLECT_RECEIVABLE | Account Usage Code |
| MERCH_PYMT_RECEIVABLE | Account Usage Code |
| APM_RECEIVABLE | Account Usage Code |
| VISA_PAR_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_MC_RECEIVABLE | Account Usage Code |
| WRITEOFF_SP_RECEIVABLE | Account Usage Code |
| FEDERAL_TAX_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_VISA_RECEIVABLE | Account Usage Code |
| FEE_COLL_INET_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_U_RECEIVABLE | Account Usage Code |
| CHBK_HOLD_RECEIVABLE | Account Usage Code |
| PAGOBANCOMAT_RECEIVABLE | Account Usage Code |
| PAYMENT_SUSPENSE_RECEIVABLE | Account Usage Code |
| MERCHANT_HOLD_RECEIVABLE | Account Usage Code |
| PAR_DR_RECEIVABLE | Account Usage Code |
| MANUAL_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| INTERBANK_SUSP_VISA_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_FDELGBP_RECEIVABLE | Account Usage Code |
| MC_PAR_RECEIVABLE | Account Usage Code |
| PAR_HOLDING_RECEIVABLE | Account Usage Code |
| FX_ROUNDING_DIFF_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_ALL_RECEIVABLE | Account Usage Code |
| FEE_COLL_VISA_RECEIVABLE | Account Usage Code |
| MERCH_FACTOR_RECEIVABLE | Account Usage Code |
| STATE_TAX_RECEIVABLE | Account Usage Code |
| FEE_HOLD_BCMC_RECEIVABLE | Account Usage Code |
| FEXCO_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| PAR_BCMC_RECEIVABLE | Account Usage Code |
| INTEREST_RECEIVABLE_RECEIVABLE | Account Usage Code |
| FEE_COLL_BCMC_RECEIVABLE | Account Usage Code |
| MERC_ROLLIN_RESERVE_RECEIVABLE | Account Usage Code |
| WRITEOFF_ACQ_RECEIVABLE | Account Usage Code |
| MERCH_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| VISA_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTED_SOURCE_RECEIVABLE | Account Usage Code |
| FX_PL_CHARGEBACK_2_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_EUR_RECEIVABLE | Account Usage Code |
| FEE_COLL_IPM_RECEIVABLE | Account Usage Code |
| VAT_HOLD_RECEIVABLE | Account Usage Code |
| FEE_COLL_ECCF_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_BAMS_RECEIVABLE | Account Usage Code |
| ACQ_COMM_REVENUE_RECEIVABLE | Account Usage Code |
| INTERCHANGE_REJ_SUSP_RECEIVABLE | Account Usage Code |
| REJECTS_VISA_RECEIVABLE | Account Usage Code |
| FX_PI_CHARGEBACK_RECEIVABLE | Account Usage Code |
| REJECTS_IPM_RECEIVABLE | Account Usage Code |
| REJECTS_ECCF_RECEIVABLE | Account Usage Code |
| MERCHANT_BILLBACK_RECEIVABLE | Account Usage Code |
| IDEAL_PAR_RECEIVABLE | Account Usage Code |
| SP_PAYMENT_RECEIVABLE | Account Usage Code |
| JCB_MERCHANT_RECEIVABLE | Account Usage Code |
| AMEX_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTS_INET_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_WELLS_RECEIVABLE | Account Usage Code |
| TREASURY_PYMT_BASECAD_RECEIVABLE | Account Usage Code |
| FEE_HOLD_RECEIVABLE | Account Usage Code |
| MC_ADJUSTMENTS_RECEIVABLE | Account Usage Code |
| REJECTED_DESC_RECEIVABLE | Account Usage Code |
| GST_COLLECT_RECEIVABLE | Account Usage Code |
| VEASE_FUND_CLEAR_RECEIVABLE | Account Usage Code |
| EFTPOS_PYMT | Account Usage Code |

<!-- type: tab-end -->
---

### ROUTING_NUMBER

* Description: Routing number of a bank.
* API field: `routingNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    22        |    Available     | Required     |  Allowed  |    NA      |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     7        |    9        | Available | Required     |  Allowed  |    NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 9        |    22       |    Available     | Optional     |  Allowed  |    NA       |

<!-- type: tab-end -->
---

### ACCT_NUMBER

* Description: Account number assigned to the merchant's bank account.
* API field: `accountNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 6        |    35        |    Available     | Required     |  Allowed  |    NA      |

* Since Account number is PII data, it will be stored in encrypted format in table.
* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     12        |    17      |    Available     | Required     |  Allowed  |    NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 6        |    35        |    Available     | Optional     |  Allowed  |    NA      |

<!-- type: tab-end -->

---

### ACCOUNT_EFFECTIVE_DT

* Description: Date on which the account was activated.
* API field: `accountEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  | 10        |    10        |    Available     | Required     |  Allowed  |    NA |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String | 10        |    10        |    Available     | Required     |  Allowed  |    NA |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### BANK_FUNDING_FILE_CODE

* Description: Code that indicates the funding file process associated with ABA/DDA.
* API field: `bankFundingFileCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     |  Allowed  |    NA      |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| DDA_AGENT_LEVEL     |     DDA Agent Level   |
| FED_AGENT_LEVEL     |     Fed Agent Level   |
| FED_BANK_LEVEL     |     Fed Bank Level   |
| DDA_BANK_LEVEL     |     DDA Bank Level   |
| DDA_BUSINESS_LEVEL     |     DDA Business Level   |
| FED_BUSINESS_LEVEL     |     Fed Business Level   |
| RESTRCTD_ET_FILE | Restricted ET File |
| BASE_ACH | Base ACH |
| NONE | Blank value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     |  Allowed  |    NA      |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| DDA_AGENT_LEVEL     |     DDA Agent Level   |
| FED_AGENT_LEVEL     |     Fed Agent Level   |
| FED_BANK_LEVEL     |     Fed Bank Level   |
| DDA_BANK_LEVEL     |     DDA Bank Level   |
| DDA_BUSINESS_LEVEL     |     DDA Business Level   |
| FED_BUSINESS_LEVEL     |     Fed Business Level   |
| RESTRCTD_ET_FILE | Restricted ET File |
| BASE_ACH | Base ACH |
| NONE | Blank value |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### BANK_ACCOUNT_TYPE

* Description: Type of an account.

* API field: `bankAccountType`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     |  Allowed  |    NA |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   |
| SAVINGS     |     Savings   |
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     |  Allowed  |    NA |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   |
| SAVINGS     |     Savings   |
| NONE | Blank Value |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### PAYMENT_DELAY_DAYS

* Description: Number of days to hold payment to the merchant.

* API field: `paymentDelayDays`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Integer  | 1        |    3        |    Available     | Optional     |  NA  |    NA          |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available | Optional     |  NA  |    NA               |

<!-- type: tab-end -->
---

### BANK_NAME

* Description: Merchant's bank name. When Billing Level set to true Bank Name must be populated.

* API field: `bankName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available     | Optional |  NA  |    NA             |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    40        |    Available | Optional     |  NA   |    NA              |

<!-- type: tab-end -->
---

### NAME_ON_ACCT

* Description: Merchant's bank account name. Mandatory if billing level is set to true.

* API field: `nameOnAccount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Optional |  NA  |    NA             |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available | Optional     |  NA   |    NA              |

<!-- type: tab-end -->
---

### IBAN

* Description: International Bank Account Number (IBAN) is a series of alphanumeric characters that uniquely identifies a customer's account held at a bank anywhere in the world. This is considered PII data; the value will be encrypted prior to storing.

* API field: `iban`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Optional |  NA  |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available | Optional     |  NA   |    NA              |

<!-- type: tab-end -->
---

### PHONE_NUMBER

* Description: The telephone number of the merchant bank.

* API field: `phoneNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available     | Optional |  NA  |    NA             |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 10        |    15        |    Available | Optional     |  NA  |    NA              |

<!-- type: tab-end -->
---

### CONTACT_NAME

* Description: Name of contact at the merchant's bank. Mandatory if billing level is set to true.

* API field: `contactName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Optional |  NA  |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available | Optional     |  NA  |     NA              |

<!-- type: tab-end -->
---

### CORRESPONDENT_BANK_NO

* Description: For institutions using IFS funding file this field should contain the swift code of the payable bank (mapped to international bank code field on the IFS file).

* API field: `correspondentBankNo`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    11        |    Available     | Optional |  NA  |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    11        |    Available | Optional     |  NA   |    NA              |

<!-- type: tab-end -->
---

### BANK_CITY

* Description: CREDIT ACCOUNT Bank City (optional field).

* API field: `bankCity`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available     | Optional |  NA  |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    35        |    Available | Optional     |  NA   |    NA              |

<!-- type: tab-end -->
---

### PAYMENT_FORMAT_ID

* Description: Format to be used to present payments to the clearing entity. Only applicable to institutions using the IFS file for funding merchants. If not provided while adding a merchant account, then system will default to the first occurrence (ordered by Index) defined for an institution.

* API field: `paymentFormat`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional |  NA  |    NA               |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
| BACS | BACS |
| SWT | SWT |
| FWT | FWT |
| NA | Not Applicable |
| SDC | SDC |
| CCD | CCD |
| SCT | SCT |
| CCT | CCT |
| ACH | ACH |
| XML | XML |
| EDIFACT | EDIFACT |
| FPT | FPT |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available | Optional     |  NA  |    NA               |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
| BACS | BACS |
| SWT | SWT |
| FWT | FWT |
| NA | Not Applicable |
| SDC | SDC |
| CCD | CCD |
| SCT | SCT |
| CCT | CCT |
| ACH | ACH |
| XML | XML |
| EDIFACT | EDIFACT |
| FPT | FPT |

<!-- type: tab-end -->
---

### CLEARING_ENTITY

* Description: The financial institution that will receive the payment. Only applicable to institutions using the IFS file for funding merchants.

* API field: `clearingEntity`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional |  NA  |     NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
| ABN_AMRO | ABN Amro |
| BANA_HONG_KONG_BHK | BANA Hong Kong - BHK |
| BANA_GERMANY_BGE | BANA Germany BGE |
| JP_MORGAN_CHASE | JP Morgan Chase |
| RBS | RBS |
| NOT_APPLICABLE | Not Applicable |
| SCB | SCB |
| DEUTSCHE_BANK_DEU | Deutsche Bank - DEU |
| BANA_LONDON | BANA London |
| VOCA_BACS | VOCA [BACS] |
| BANA_SINGAPORE_BSG | BANA Singapore - BSG |
| WELLS_FARGO_WFG | Wells Fargo - WFG |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA             |    NA      |  Available | Optional   |       NA     |    NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
| ABN_AMRO | ABN Amro |
| BANA_HONG_KONG_BHK | BANA Hong Kong - BHK |
| BANA_GERMANY_BGE | BANA Germany BGE |
| JP_MORGAN_CHASE | JP Morgan Chase |
| RBS | RBS |
| NOT_APPLICABLE | Not Applicable |
| SCB | SCB |
| DEUTSCHE_BANK_DEU | Deutsche Bank - DEU |
| BANA_LONDON | BANA London |
| VOCA_BACS | VOCA [BACS] |
| BANA_SINGAPORE_BSG | BANA Singapore - BSG |
| WELLS_FARGO_WFG | Wells Fargo - WFG |

<!-- type: tab-end -->
---

### CORRESPONDENT_BANK_ACCOUNT

* Description: Bank account number for the intermediary bank used for fund transfers. Used in cases where merchant uses a small financial institution, for example a local credit union.

* API field: `correspondentBankAccount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 6        |    16        |    Available     | Optional |  NA   |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 6        |    16        |    Available | Optional     |  NA  |    NA               |

<!-- type: tab-end -->
---

### BILLING_LEVEL

* Description: Indicates if the account will be settled to on a funding.

* API field: `billingLevel`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Boolean  | 4        |    5        |    Available     | Required |  NA   |    NA              |

* Note: This field is applicable for both PAYABLE and RECEIVABLE entities for GMA. Defaults to false.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Boolean  | 4        |    5        |    Available     | Required |  NA   |    NA              |

<!-- type: tab-end -->
---

### CURRENCY_CODE

* Description: Indicates if the account will be settled to on a funding.

* API field: `currencyCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required |  NA  |    NA               |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|EUR | Euro|
|CHF | Swiss Franc|
|HKD | Hong Kong Dollar|
|DKK | Danish Krone|
|USD | US Dollar|
|CAD | Canadian Dollar|
|ZAR | Rand|
|NOK | Norwegian Krone|
|JPY  | Yen|
|AUD | Australian Dollar|
|SGD | Singapore Dollar|
|GBP | Pound Sterling|
|SEK | Swedish Krona|
|NZD | New Zealand Dollar|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required |  NA  |    NA               |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|EUR | Euro|
|CHF | Swiss Franc|
|HKD | Hong Kong Dollar|
|DKK | Danish Krone|
|USD | US Dollar|
|CAD | Canadian Dollar|
|ZAR | Rand|
|NOK | Norwegian Krone|
|JPY  | Yen|
|AUD | Australian Dollar|
|SGD | Singapore Dollar|
|GBP | Pound Sterling|
|SEK | Swedish Krona|
|NZD | New Zealand Dollar|

<!-- type: tab-end -->
---

### PAYMENT_REFERENCE

* Description: For institutions using IFS funding file this field should contain the direct debit contract number (required for merchant debits). For others it is a reference text to display on merchant's bank statement if supported on the funding file.

* API field: `paymentReference`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    18        |    Available     | Optional |  NA   |    NA              |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    18        |    Available     | Optional |  NA   |    NA              |

<!-- type: tab-end -->
---

### RECEIVER_COUNTRY

* Description: ISO-3166 alpha country code for the merchant's bank country. Mandatory if billing level is set to true. If not provided while adding an account then system will default to null.

* API field: `receiverCountry`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Optional |  NA   |    NA               |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    3        |    Available     | Optional |  NA   |    NA               |

<!-- type: tab-end -->
---

### STATEMENT_GENERATION

* Description: Option for statement generation. Defauts to GENERATE_IF_ACTIVITY.

* API field: `statementGeneration`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional |  NA  |     NA              |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|SUPPRESS | Suppress Statement Generation for Merchant account|
|GENERATE | Generate statements for Merchant account|
|GENERATE_IF_ACTIVITY | Generate statements for Merchant if there is activity on the account|
|GENERATE_IF_NO_ACTIVITY | Generate statements for Merchant if there is no activity on the account|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | 8        |    23        |    Available     | Optional |    NA  |    NA              |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|SUPPRESS | Suppress Statement Generation for Merchant account|
|GENERATE | Generate statements for Merchant account|
|GENERATE_IF_ACTIVITY | Generate statements for Merchant if there is activity on the account|
|GENERATE_IF_NO_ACTIVITY | Generate statements for Merchant if there is no activity on the account|

<!-- type: tab-end -->
---

### STATEMENT_TYPE

* Description: Statement type to be generated. Allowed to provide valid value if the institution level configuration enabled to override at merchant level. If no value provided while adding a merchant account, then system will default to "900".

* API field: `statementType`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Optional |  NA  |    NA             |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|CHARGE_INVOICE | Charge Invoice|
|MERCHANT_STATEM_G_C_FEE | Merchant Statem. g+c fee|
|CARDHOLDER_STATEMENT_15 | Cardholder Statement 15|
|DETAIL_WKLY_CHAIN_STATEMENT_S | Detail wkly chain statement-S|
|CARDHOLDER_STATEMENT_EOM | Cardholder Statement EOM|
|DETAIL_MNTHLY_SINGLE_STATEMENT | Detail mnthly single statement|
|DETAIL_WEEKLY_CHAIN_STATEMENT | Detail weekly chain statement|
|GSS_CARDHOLDER_STATEMENT | GSS Cardholder Statement|
|BATCH_WEEKLY_CHAIN_STATEMENT | Batch weekly chain statement|
|BATCH_MNTHLY_SINGLE_STATEMENT | Batch mnthly single statement|
|BATCH_WEEKLY_CHAIN_STATEMENT_S | Batch weekly chain statement-S|
|DETAIL_MNTHLY_CHAIN_STATEMENT | Detail mnthly chain statement|
|MERCHANT_STATEMENT_NET | Merchant Statement net|
|BATCH_MNTHLY_CHAIN_STATEMENT | Batch mnthly chain statement|
|DETAIL_MTHLY_SINGL_STATEMENT_S | Detail mthly single statement-S|
|USE_DEFAULT | Use Default|
|BATCH_MNTHLY_CHAIN_STATEMENT_S | Batch mnthly chain statement-S|
|PAYMENT_ADVICE | Payment Advice|
|BATCH_WEEKLY_SINGLE_STATEMENT | Batch weekly single statement|
|BATCH_WEEKLY_SINGL_STATEMENT_S | Batch weekly single statement-S|
|NOT_APPLICABLE | Not Applicable|
|BATCH_MNTHLY_SINGL_STATEMENT_S | Batch mnthly single statement-S|
|MERCHANT_STATEMENT_EOM | Merchant Statement EOM|
|DETAIL_WEEKLY_SINGLE_STATEMENT | Detail weekly single statement|
|GSS_MERCHANT_STATEMENT | GSS  Merchant Statement|
|SERVICE_PROVIDER_STATEMENT | Service Provider Statement|
|DETAIL_WKLY_SINGLE_STATEMENT_S | Detail wkly single statement-S|
|DETAIL_MTHLY_CHAIN_STATEMENT_S | Detail mthly chain statement-S|
|MERCHANT_STATEMENT_G_C | Merchant Statement g+c|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|    NA  |       NA       |     NA     |    NA    |     NA       |      NA      |      NA      |

<!-- type: tab -->

<!--#### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |   NA        |    Available     | Optional |  NA  |     NA               |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|CHARGE_INVOICE | Charge Invoice|
|MERCHANT_STATEM_G_C_FEE | Merchant Statem. g+c fee|
|CARDHOLDER_STATEMENT_15 | Cardholder Statement 15|
|DETAIL_WKLY_CHAIN_STATEMENT_S | Detail wkly chain statement-S|
|CARDHOLDER_STATEMENT_EOM | Cardholder Statement EOM|
|DETAIL_MNTHLY_SINGLE_STATEMENT | Detail mnthly single statement|
|DETAIL_WEEKLY_CHAIN_STATEMENT | Detail weekly chain statement|
|GSS_CARDHOLDER_STATEMENT | GSS Cardholder Statement|
|BATCH_WEEKLY_CHAIN_STATEMENT | Batch weekly chain statement|
|BATCH_MNTHLY_SINGLE_STATEMENT | Batch mnthly single statement|
|BATCH_WEEKLY_CHAIN_STATEMENT_S | Batch weekly chain statement-S|
|DETAIL_MNTHLY_CHAIN_STATEMENT | Detail mnthly chain statement|
|MERCHANT_STATEMENT_NET | Merchant Statement net|
|BATCH_MNTHLY_CHAIN_STATEMENT | Batch mnthly chain statement|
|DETAIL_MTHLY_SINGL_STATEMENT_S | Detail mthly single statement-S|
|USE_DEFAULT | Use Default|
|BATCH_MNTHLY_CHAIN_STATEMENT_S | Batch mnthly chain statement-S|
|PAYMENT_ADVICE | Payment Advice|
|BATCH_WEEKLY_SINGLE_STATEMENT | Batch weekly single statement|
|BATCH_WEEKLY_SINGL_STATEMENT_S | Batch weekly single statement-S|
|NOT_APPLICABLE | Not Applicable|
|BATCH_MNTHLY_SINGL_STATEMENT_S | Batch mnthly single statement-S|
|MERCHANT_STATEMENT_EOM | Merchant Statement EOM|
|DETAIL_WEEKLY_SINGLE_STATEMENT | Detail weekly single statement|
|GSS_MERCHANT_STATEMENT | GSS  Merchant Statement|
|SERVICE_PROVIDER_STATEMENT | Service Provider Statement|
|DETAIL_WKLY_SINGLE_STATEMENT_S | Detail wkly single statement-S|
|DETAIL_MTHLY_CHAIN_STATEMENT_S | Detail mthly chain statement-S|
|MERCHANT_STATEMENT_G_C | Merchant Statement g+c|
<!-- type: tab-end -->
