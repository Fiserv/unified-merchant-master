# Merchant Bank Account
* **Description**: Essential information about merchant bank account, including account number, account type, and contact information. 
* **API section**: root 
* **Table Name**: UMM.MERCHANT_BANK_ACCOUNT 

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
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant. 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required  |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
| String |     -    |          |              |       NA     |

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
| String  | 5        |    9        |    Required     | Required     | Required |    Required     |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     | 
| OMNIPAY26     |  Omnipay Backend ( GMA)      | 
| SOUTH     |     South  Backend | 
| OMNIPAY21     |    Omnipay ( Australia)    |      |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |  |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
| String |     -    |          |              |       NA     |

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
| Integer  | 1        |    3        |    Available     | Required     |  Allowable  |    NA |         |

* SEQUENCE_NUMBER will be used to update bank detail associated with a specific bank account

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     1st Bank Account    | 
| 2     |     2nd Bank Account   | 
| 3     |     3rd bank Account   | 
| 4     |     4th Bank Account   | 
| 5     |     5th Bank Account   |

<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| Integer| Available   | Required   |  Allowable    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     1st Bank Account    | 
| 2     |     2nd Bank Account   | 
| 3     |     3rd bank Account   | 
| 4     |     4th Bank Account   | 
| 5     |     5th Bank Account   |

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
* Description: Code that indicate the usage/purpose of an account.
* API field: `accountUsageCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 3        |    14        |    Available     |   Required   |Allowed  |  NA   |        

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| FUNDING     |     Funding Bank Account  | 
| LEASING     |     Leasing Bank Account   |
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


<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   |  NA  | NA |       

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| FUNDING     |     Funding Bank Account   | 
| LEASING     |     Leasing Bank Account    | 


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
| String  | 9        |    9        |    Available     | Required     |  Allowed  |    NA |    

<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   |  Allowed    | NA |    

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
| String  | 6        |    35        |    Available     | Required     |  Allowed  |    NA |    

* Since Account number is PII data, it will be stored in encrypted format in table. 

<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   |  Allowed    | NA |    

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
| Date  | 10        |    10        |    Available     | Required     |  Allowed  |    NA |    

<!-- type: tab -->

##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   |  Allowed    | NA |    

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
* Description: Code that indicates the funding file process associated with ABA/DDA.
* API field: `bankFundingFileCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 14        |    18        |    Available     | Required     |  Allowed  |    NA |         |

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
| String   | Available   | Required   |  Allowed    | NA |         |

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
### BANK_ACCOUNT_TYPE
* Description: Type of an account.

* API field: `bankAccountType`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 7        |    10        |    Available     | Required     |  Allowed  |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| CHECKING     |     Checking   | 
| SAVINGS     |     Savings   | 

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String | Available   | Required   |  Allowed    | NA |         |

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
