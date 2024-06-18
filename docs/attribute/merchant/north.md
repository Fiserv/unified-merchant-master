# North Merchant Attributes

The below section list the attributes grouped by **Domain**

## `chargebackConfig`

| Name | Description | Allowed Values |
| -------- | ------- | ------- |
| `chargebackPrenoteIndicator` | Chargeback Prenote Indicator | `YES`, `NO` |

#### Sample:

```
"chargebackConfig": {
  "chargebackPrenoteIndicator": {
    "attributeDescription": "Chargeback Prenote Indicator",
    "values": [ "YES" ]
  }
}
```
---

## `fundingConfig`

| Name | Description | Allowed Values |
| -------- | ------- | ------- |
| `fundingRunCode` | Merchant Funding Run Code | `FUNDING_RUN6`, `FUNDING_RUN2`, `FUNDING_RUN1`, `FUNDING_RUNS`, `FUNDING_RUN6`, `FUNDING_RUN3`, `FUNDING_RUN4`|
| `fundingRollupCode` | Indicates how the funding transactions will be combined on DDA statement | `DEBIT_CREDIT`, `DEPOSIT_BATCH`, `EACH_TRANSFER`, `NET_ROLLUP`, `VIA_CATGRY`, `NET_FEE_TRANS` |
| `fundingExcludeCode` | Merchant funding exclusion code | `YES`, `NO`, '`DIVERT` |

#### Sample:

```
"fundingConfig": {
  "fundingRunCode": {
    "attributeDescription": "Merchant Funding Run Code",
    "values": [ "FUNDING_RUN6" ]
  },
  "fundingRollupCode": {
    "attributeDescription": "Indicates how the funding transactions will be combined on DDA statement",
    "values": [ "DEBIT_CREDIT" ]
  },
  "fundingExcludeCode": {
    "attributeDescription": "Merchant funding exclusion code",
    "values": [ "YES" ]
  }
}
```
---

## `statementConfig`

| Name | Description | Allowed Values |
| -------- | ------- | ------- |
| `icplusStatementFormatCode` | Interchange Plus Long Statement | `ICPLUS_LONG_STMT` |
| `statementMailToCode` | [View Description](#statementmailtocode) | [View Details](#statementmailtocode) |

> ### `statementMailToCode`
>
> | Allowed Values | Description |
> | ------- | ------- |
> | `MAIL_TO_OUTLET` | Mail To Outlet |
> | `RECAP_CORP_STMT_OUTLET` | Recap Corp/Stmt Outlet |
> | `SUPP_STMT_RECAP` | Suppress Stmts/Recap |
> | `MAIL_TO_CORP_NO_RECAP` | Mail to Corp, No Recap |
> | `MAIL_TO_CORP` | Mail to Corp |
> | `RECAP_NO_STMT` | Recap/No Statements |

#### Sample:

```
"statementConfig": {
  "icplusStatementFormatCode": {
    "attributeDescription": "Interchange Plus Long Statement",
    "values": [ "ICPLUS_LONG_STMT" ]
  },
  "statementMailToCode": {
    "attributeDescription": "Mail to Corp, No Recap",
    "values": [ "MAIL_TO_CORP_NO_RECAP" ]
  }
}
```
---
