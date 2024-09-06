# Merchant Additional Data - US

* **Description**: Stores Tax related information for merchants
* **API schema**: `merchantIrsDetails`
* **Table Name**: `UMM.MERCHANT_TAX_ADTNL_DATA_US`

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
| String  | 8        |    8        |    Required     | Required     | Required |    NA     |

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
| Enum  | NA        |    NA        |    Required     | Required     | Required |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->
---

### EXCLUSION_CODE

* Description: Code that indicates weather the merchant is excluded from the IRS processing.
* API field: `exclusionCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |    NA     |

**Valid Values**:

|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|FOREIGN_ENTITY_PENDING_VERIFICATION | Fgn Entity Pend Verify|
|FOREIGN_ENTITY_PRIOR_1/1/11 | Fgn Entity prior 1/11/11|
|NONPROFIT_VERIFIED | Non profit verified|
|NONPROFIT_NOT_VERIFIED | Non profit not verified|
|FOREIGN_ENTITY_VERIFIED | Foreign Entity Verified|
|GOVERNMENT_ENTITY | Government entity|
|FINANCIAL_INSTITUTION | Financial institution|
|NOT_EXCLUDED | Not excluded|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |    NA     |

**Valid Values**:

|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|FOREIGN_ENTITY_PENDING_VERIFICATION | Fgn Entity Pend Verify|
|FOREIGN_ENTITY_PRIOR_1/1/11 | Fgn Entity prior 1/11/11|
|NONPROFIT_VERIFIED | Non profit verified|
|NONPROFIT_NOT_VERIFIED | Non profit not verified|
|FOREIGN_ENTITY_VERIFIED | Foreign Entity Verified|
|GOVERNMENT_ENTITY | Government entity|
|FINANCIAL_INSTITUTION | Financial institution|
|NOT_EXCLUDED | Not excluded|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### IRS_TIN_VALIDATION_CODE

* Description: Code that indicates the validation of the merchant's taxpayer identification number (TIN).
* API field: `irsTinValidationCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIN_MATCHED | TIN and name match IRS|
|TIN_MISSING | TIN missing / not 9 digits|
|TIN_UNISSUED | TIN not currently issued|
|TIN_NOTMATCHED | TIN/NAME not equal to IRS|
|INVALID_TIN | Invalid TIN match request|
|DUPLICATE_TIN | Duplicate TIN matching request|
|TIN_MATCHED_SSN | TIN/name match IRS/SSN|
|TIN_MATCHED_EIN | TIN/name match IRS/EIN|
|TIN_MATCHED_SSN_EIN | TIN/name match IRS/SSN/EIN|
|IN_PROCESS_NO_UPDATE_MMF | In progress no update MMF|
|TEST_ACCOUNT | Test account ex val by IRS|
|INVALID_TIN_MULTI_TFN | Invalid TIN with multi TFN|
|IN_PROCESS | In process|
|INVALID_NOT_TFN | Invalid passed TIN not TFN|
|FAILED_PRESCREEN | TIN failed prescreening|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |    NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIN_MATCHED | TIN and name match IRS|
|TIN_MISSING | TIN missing / not 9 digits|
|TIN_UNISSUED | TIN not currently issued|
|TIN_NOTMATCHED | TIN/NAME not equal to IRS|
|INVALID_TIN | Invalid TIN match request|
|DUPLICATE_TIN | Duplicate TIN matching request|
|TIN_MATCHED_SSN | TIN/name match IRS/SSN|
|TIN_MATCHED_EIN | TIN/name match IRS/EIN|
|TIN_MATCHED_SSN_EIN | TIN/name match IRS/SSN/EIN|
|IN_PROCESS_NO_UPDATE_MMF | In progress no update MMF|
|TEST_ACCOUNT | Test account ex val by IRS|
|INVALID_TIN_MULTI_TFN | Invalid TIN with multi TFN|
|IN_PROCESS | In process|
|INVALID_NOT_TFN | Invalid passed TIN not TFN|
|FAILED_PRESCREEN | TIN failed prescreening|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TIN_VALIDATION_DATE

* Description: Date on which the IRS taxpayer identification number (TIN) validation was last performed for a merchant.
* API field: `tinValidationDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |       NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |       NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### PAYEE_CODE

* Description: Code that indicates the unique code assigned to a payee or recipient for tax reporting purposes by the Internal Revenue Service (IRS).
* API field: `payeeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |       NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|CHAIN_PAYEE_AGREGATOR | Chain Payee Agregator|
|CHAIN_PAYEE | Chain Payee|
|CHAIN_NON_PAYEE | Chain Non Payee|
|CHAIN_OUTLET_NO_1099K | Chain/Outlet no 1099k|
|OUTLET_NONPAYEE_UNRELATD | Outlet nonpayee unrelatd|
|OUTLET_NON_PAYEE_RELATED | Outlet non payee related|
|OUTLET_PAYEE_RELATED | Outlet payee related|
|SINGLETON_PAYEE | Singleton payee|
|OUTLET_PAYEE_UNRELATED | Outlet payee unrelated|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |       NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|CHAIN_PAYEE_AGREGATOR | Chain Payee Agregator|
|CHAIN_PAYEE | Chain Payee|
|CHAIN_NON_PAYEE | Chain Non Payee|
|CHAIN_OUTLET_NO_1099K | Chain/Outlet no 1099k|
|OUTLET_NONPAYEE_UNRELATD | Outlet nonpayee unrelatd|
|OUTLET_NON_PAYEE_RELATED | Outlet non payee related|
|OUTLET_PAYEE_RELATED | Outlet payee related|
|SINGLETON_PAYEE | Singleton payee|
|OUTLET_PAYEE_UNRELATED | Outlet payee unrelated|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CP2100_NOTICE_RECEIVED_DATE

* Description: Date on which the merchant received a IRS CP2100 notice.
 Format: CCYY-MM-DD
 Example: 2024-05-15
* API field: `cp2100NoticeReceivedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### CP2100_NOTICE_EFFECTIVE_DATE

* Description: Date on which the IRS CP2100 notice  becomes effective.
  Format: CCYY-MM-DD
  Example: 2024-05-15
* API field: `cp2100NoticeEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available     | NA     | Allowed |    NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_CODE

* Description: Code that indicates the IRS withholding is required or not.
* API field: `withholdingCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |       NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|REQUIRED | Backup Withhold is Required|
|NOT_REQUIRED | Previously required backup withholding is not required now|
| NO_WITHHOLDING_IS_REQUIRED| No withholding is required |
| OUT_OBLIGATION | Out Obligation |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available     | NA     | Allowed |       NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|REQUIRED | Backup Withhold is Required|
|NOT_REQUIRED | Previously required backup withholding is not required now|
| NO_WITHHOLDING_IS_REQUIRED| No withholding is required |
| OUT_OBLIGATION | Out Obligation |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_NOTIFICATION_CODE

* Description: Code that indicates the IRS back up withholding notification.
* API field: `withholdingNotificationCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA       |    NA        |    Available   | NA   | Allowed   |    NA   |  

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|1ST_BUW_NOTICE | First BUW Notice|
|2ND_BUW_NOTICE | Second BUW Notice|
|BUW_WARN_LETTER | BUW Warning Letter|
|1099K_REPORT | 1099K Reporting|
|1099K_REPORT_AND_STATE | 1099K Report and State|
|BUW_MISSING_TIN | BUW Missing TIN|
|TIMS_MANL_BUW | TIMS Manual BUW On|
|W8_EXP | W8 Expiration|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA       |    NA        |    Available   | NA   | Allowed   |    NA   |  

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|1ST_BUW_NOTICE | First BUW Notice|
|2ND_BUW_NOTICE | Second BUW Notice|
|BUW_WARN_LETTER | BUW Warning Letter|
|1099K_REPORT | 1099K Reporting|
|1099K_REPORT_AND_STATE | 1099K Report and State|
|BUW_MISSING_TIN | BUW Missing TIN|
|TIMS_MANL_BUW | TIMS Manual BUW On|
|W8_EXP | W8 Expiration|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_NOTIFICATION_DATE

* Description: Date on which the taxpayer received a notification related to income withholding.
  Format: CCYY-MM-DD
  Example: 2024-05-15
* API field: `withholdingNotificationDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |     Available   | NA   | Allowed   |   NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |     Available   | NA   | Allowed   |   NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_REASON_CODE

* Description: Code that indicates the IRS back up withholding reason.
* API field: `withholdingReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available   | NA   | Allowed   |   NA   |  

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIMS_MANUAL_BUW_OFF | TIMS Manual BUW Off|
|W9_ON_FILE | W9 on file / received|
|FORM_CERTIFY_PENDING | Form certify pending|
|INCOMPLETE_PAPERWORK | Incomplete paperwork|
|SS_CARDCOPY_OR_LTR147C | SS cardcopy or ltr147c|
|W8_FOREIGN_PNDING_REVIEW | W8 foreign pnding review|
|W8_FOREIGN_COMPLETE | W8 foreign complete|
|W8_NO_EXPIRATIONS | W8 no expirations|
|W9_RECEIVED_EXEMPTION | W9 received exemption|
|W8_EXPIRATION_PENDING | W8 expiration pending|
| NOT_APPLICABLE | Not Applicable |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available   | NA   | Allowed   |   NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIMS_MANUAL_BUW_OFF | TIMS Manual BUW Off|
|W9_ON_FILE | W9 on file / received|
|FORM_CERTIFY_PENDING | Form certify pending|
|INCOMPLETE_PAPERWORK | Incomplete paperwork|
|SS_CARDCOPY_OR_LTR147C | SS cardcopy or ltr147c|
|W8_FOREIGN_PNDING_REVIEW | W8 foreign pnding review|
|W8_FOREIGN_COMPLETE | W8 foreign complete|
|W8_NO_EXPIRATIONS | W8 no expirations|
|W9_RECEIVED_EXEMPTION | W9 received exemption|
|W8_EXPIRATION_PENDING | W8 expiration pending|
| NOT_APPLICABLE | Not Applicable |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_EFFECTIVE_DATE

* Description: Date on which the IRS back up withholding becomes effective.
  Format: CCYY-MM-DD
  Example: 2024-05-15
* API field: `withholdingEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### WITHHOLDING_END_DATE

* Description: Date from which the IRS back up withholding is not effective.
  Format: CCYY-MM-DD
  Example: 2024-05-15
* API field: `withholdingEndDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |    Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### FED_WITHHOLDING_PERCENT

* Description: Percentage of backup withholding that is required to be withheld by the the IRS.
* API field: `fedWithHoldingPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal |       3       |    3        |     Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal |       3        |    3        |     Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### STATE_WITHHOLDING_PERCENT

* Description: Percentage that applies to the withholding of state income tax.
* API field: `stateWithholdingPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |    3        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       3        |    3        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### FORM_CERT_STATUS_CODE

* Description: Code that indicates the status of IRS form certification.
* API field: `formCertStatusCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |     Available   | NA   | Allowed   |   NA   |  

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIMS_MANUAL_BUW_OFF | TIMS Manual BUW Off|
|W9_ON_FILE | W9 on file / received|
|FORM_CERTIFY_PENDING | Form certify pending|
|INCOMPLETE_PAPERWORK | Incomplete paperwork|
|SS_CARDCOPY_OR_LTR147C | SS cardcopy or ltr147c|
|W8_FOREIGN_PNDING_REVIEW | W8 foreign pnding review|
|W8_FOREIGN_COMPLETE | W8 foreign complete|
|W8_NO_EXPIRATIONS | W8 no expirations|
|W9_RECEIVED_EXEMPTION | W9 received exemption|
|W8_EXPIRATION_PENDING | W8 expiration pending|
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |     Available   | NA   | Allowed   |   NA   |  

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|TIMS_MANUAL_BUW_OFF | TIMS Manual BUW Off|
|W9_ON_FILE | W9 on file / received|
|FORM_CERTIFY_PENDING | Form certify pending|
|INCOMPLETE_PAPERWORK | Incomplete paperwork|
|SS_CARDCOPY_OR_LTR147C | SS cardcopy or ltr147c|
|W8_FOREIGN_PNDING_REVIEW | W8 foreign pnding review|
|W8_FOREIGN_COMPLETE | W8 foreign complete|
|W8_NO_EXPIRATIONS | W8 no expirations|
|W9_RECEIVED_EXEMPTION | W9 received exemption|
|W8_EXPIRATION_PENDING | W8 expiration pending|
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### FORM_CERT_STATUS_RECEIVED_DATE

* Description: Date on which the certification status of an IRS form was received.
  Format: CCYY-MM-DD
  Example: 2024-05-15
* API field: `formCertStatusReceivedDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date |       10        |    10        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date |       10        |    10        |    Available   | NA   | Allowed   | NA   |  

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |  

<!-- type: tab-end -->
---

### TURF_EFFECTIVE_DATE

* Description: Effective date from when the Taxpayer's United Reporting Federation (TURF) makes an agreement with the IRS.
 Format: CCYY-MM-DD
 Example: 2024-05-15
* API field: `turfEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date |       10        |    10        |     Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date |       10        |    10        |     Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TURF_REASON_CODE

* Description: Code that indicates the reason of updating the IRS TURF agreement.
* API field: `turfReasonCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available   | NA   | Allowed   |   NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|ADD_MISSING_TIN/TFN | Add missing TIN/TFN|
|CORRECT_WRONG_TIN/TFN | Correct wrong TIN/TFN|
|NO_TIN/TFN_CHANGE | No TIN/TFN change|
|CHANGE_IN_OWNERSHIP | Change in ownership|
|CHANGE_IN_FILING_STATUS | Change in filing status|
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA        |    Available   | NA   | Allowed   |   NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|ADD_MISSING_TIN/TFN | Add missing TIN/TFN|
|CORRECT_WRONG_TIN/TFN | Correct wrong TIN/TFN|
|NO_TIN/TFN_CHANGE | No TIN/TFN change|
|CHANGE_IN_OWNERSHIP | Change in ownership|
|CHANGE_IN_FILING_STATUS | Change in filing status|
| NONE | Blank Value |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TURF_UPDATE_DATE

* Description: Date on which the Taxpayer's United Reporting Federation (TURF) agreement with the IRS was last updated.
 Format: CCYY-MM-DD
 Example: 2024-05-15
* API field: `turfUpdateDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |     Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    10        |     Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TAX_EFFECTIVE_YEAR

* Description: Year from which the IRS tax regulations, rules, and rates come into effect.
* API field: `taxEffectiveYear`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |    4        |   Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       4        |    4        |   Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### TIMS_ACCT_NUMBER

* Description: Account number associated with the Taxpayer Information Management System (TIMS).
* API field: `timsAccountNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    20        |    Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    20        |    Available   | NA   | Allowed   | NA   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |
<!-- type: tab-end -->
---

### TAX_PAY_INDICATOR

* Description: Value that indicates whether a taxpayer has made the required tax payments for a specific period or tax year.
* API field: `taxPayIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |       NA        |    NA        |     Available   | NA   | Allowed   |   NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NO | Tax Pay Indicator|
|YES | Tax Pay Indicator|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |       NA        |    NA        |     Available   | NA   | Allowed   |   NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NO | Tax Pay Indicator|
|YES | Tax Pay Indicator|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---
