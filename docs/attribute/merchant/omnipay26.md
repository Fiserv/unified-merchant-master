# Omnipay Merchant Attributes

The below section list the attributes grouped by **Domain**

## `contract`

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `clientRegion` | `BY_COUNTRY`, `BY_TRANSACTION`  | [View Description](#clientregion) |

#### Sample:

```
"contract": {
  "clientRegion": {
    "values": [ "BY_TRANSACTION" ]
  }
}
```
---

## `settlementConfig`

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `settlementMethod` | [View Details](#settlementmethod) | [View Description](#settlementmethod) |

> ### `settlementMethod`
>
> | Allowed Values | Description |
> | ------- | ------- |
> | `DE_DAILY_CUP` |  |
> | `IFS_DAILY` |  |
> | `IFS_MONTHLY_NEG` |  |
> | `IFS_DAILY_NEG_CUP` |  |
> | `DAILY` |  |
> | `IFS_DAILY_CUP` |  |
> | `DAILY_CUP` |  |
> | `IFS_DAILY_NEG` |  |
> | `IFS_TREASURY` |  |
> | `DE_DAILY` |  |

```
"settlementConfig": {
  "settlementMethod": {
    "values": [ "DAILY" ]
  }
}
```
---
