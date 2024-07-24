# Merchant Bank Account
* **Description**: Essential information about merchant account, including account number, type, and contact information. 
* **API section**: root 
* **Table Name**: UMM.MERCHANT 

## List of Fields:

### MERCHANT_ID
* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   | 12        |    50        |    NA     | Required     | NA |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | NA   | Required   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### PLATFORM_CODE
* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   |         |            |    NA     | Required     | Required |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | NA   | Required   | Required   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### SEQUENCE_NUMBER
* Description: ABA/DDA occurrence sequence number of a bank.
* API field: `sequenceNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| INTEGER  | 1        |    3        |    Available     | NA     |  Required  |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     Bank Sequence Number   | 
| 2     |     Bank Sequence Number   | 
| 3     |     Bank Sequence Number   | 
| 4     |     Bank Sequence Number   | 
| 5     |     Bank Sequence Number   |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   |  Required    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1      |     Bank Sequence Number   | 
| 2     |     Bank Sequence Number   | 
| 3     |     Bank Sequence Number   | 
| 4     |     Bank Sequence Number   | 
| 5     |     Bank Sequence Number   |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### ROUTING_NUMBER
* Description: Routing number of a bank.
* API field: `routingNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 9        |    50        |    Available     | Allowed     |  Required  |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Allowed   |  Required    | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### ACCOUNT_EFFECTIVE_DT
* Description: Date on which the account was activated.
* API field: `accountEffectiveDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| DATE  | 10        |    10        |    Available     | Allowed     |  Required  |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Allowed   |  Required    | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### ACCT_NUMBER
* Description: Account number assigned to the merchant's bank account.
* API field: `accountNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 17        |    50        |    Available     | Allowed     |  Required  |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Allowed   |  Required    | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### ACCT_USAGE_CODE
* Description: Code that indicate the usage of an account.
* API field: `accountUsageCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    32        |    Available     |      |  |     |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   | 
| PAR     |     Payment Account Retail   | 
| APM_PAR     |     APM Payment Account Retail   | 
| ACQ_DISP     |     Acquirer Dispute Transactions   | 
| AMEX_MERCH     |     AMEX Merchant Account   | 
| INTERBANK_SUSP     |     Interbank Suspense   | 
| DINERS_MERCH     |     Diners Merchant Account   | 
| CUP_MERCH     |     CUP Merchant Account   | 
| SM_PAR     |     Sub-Merchant Payment Account Retail   | 
| FEE_COLLECT     |     Fee Collect Account   | 
| MERCH_RSRV     |     Merchant Reserve Account   | 
| MERCH_PYMT      |     Merchant Payment Rejects   | 
| APM     |     Alternative Payments   | 
| SAVINGS     |     Savings   |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   |    |    |  |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   | 
| PAR     |     Payment Account Retail   | 
| APM_PAR     |     APM Payment Account Retail   | 
| ACQ_DISP     |     Acquirer Dispute Transactions   | 
| AMEX_MERCH     |     AMEX Merchant Account   | 
| INTERBANK_SUSP     |     Interbank Suspense   | 
| DINERS_MERCH     |     Diners Merchant Account   | 
| CUP_MERCH     |     CUP Merchant Account   | 
| SM_PAR     |     Sub-Merchant Payment Account Retail   | 
| FEE_COLLECT     |     Fee Collect Account   | 
| MERCH_RSRV     |     Merchant Reserve Account   | 
| MERCH_PYMT      |     Merchant Payment Rejects   | 
| APM     |     Alternative Payments   | 
| SAVINGS     |     Savings   |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### BANK_FUNDING_FILE_CODE
* Description: Code that indicate the funding file process associated with ABA/DDA.
* API field: `bankFundingFileCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 14        |    18        |    Available     | Allowed     |  Required  |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| DDA_AGENT_LEVEL     |     DDA Agent Level   | 
| FED_AGENT_LEVEL     |     Fed Agent Level   | 
| FED_BANK_LEVEL     |     Fed Bank Level   | 
| DDA_BANK_LEVEL     |     DDA Bank Level   | 
| DDA_BUSINESS_LEVEL     |     DDA Business Level   | 
| FED_BUSINESS_LEVEL     |     Fed Business Level   |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Allowed   |  Required    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| DDA_AGENT_LEVEL     |     DDA Agent Level   | 
| FED_AGENT_LEVEL     |     Fed Agent Level   | 
| FED_BANK_LEVEL     |     Fed Bank Level   | 
| DDA_BANK_LEVEL     |     DDA Bank Level   | 
| DDA_BUSINESS_LEVEL     |     DDA Business Level   | 
| FED_BUSINESS_LEVEL     |     Fed Business Level   |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### PHONE_NUMBER
* Description: Phone number of the principal owner.
* API field: `phoneNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   | 10        |    15        |    Available     | NA     | NA |    NA |    

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|    | Available   | NA   | NA   | NA |    

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
---

### BANK_ACCOUNT_TYPE
* Description: Type of an account.

Example: Checking/Savings/GL purposes
* API field: `bankAccountType`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    10        |    Available     | Allowed     |  Required  |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   | 
| SAVINGS     |     Savings   | 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
|    | Available   | Allowed   |  Required    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   | 
| SAVINGS     |     Savings   | 

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
