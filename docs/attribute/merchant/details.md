# Merchant Attributes

The below section list the attributes grouped by **Domain**

## `chargebackConfig`

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `email` | | |
| `mediaRetrievalCode` | | |
| `chargebackPrenoteIndicator` | `YES`, `NO` | Chargeback Prenote Indicator |

---

## `statementConfig`

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `icplusStatementFormatCode` | `ICPLUS_LONG_STMT` | Interchange Plus Long Statement |
| `statementMailToCode` | [View Details](#statementmailtocode) | [View Description](#statementmailtocode) |

> ### `statementMailToCode`
>
> | Allowed Values | Description |
> | ------- | ------- |
> | `SUPP_STMT_RECAP` | Suppress Stmts/Recap |
> | `MAIL_TO_OUTLET` | Mail To Outlet |
> | `RECAP_CORP_STMT_OUTLET` | Recap Corp/Stmt Outlet |
> | `SUPP_STMT_RECAP` | Suppress Stmts/Recap |
> | `MAIL_TO_CORP_NO_RECAP` | Mail to Corp, No Recap |
> | `MAIL_TO_OUTLET` | Mail To Outlet |
> | `MAIL_TO_CORP` | Mail to Corp |
> | `RECAP_NO_STMT` | Recap/No Statements |

---
