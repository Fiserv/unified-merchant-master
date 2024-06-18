# Omnipay Merchant Attributes

The below section list the attributes grouped by **Domain**

## `contract`

| Name | Description | Allowed Values |
| -------- | ------- | ------- |
| `clientRegion` | Client Region | `BY_COUNTRY`, `BY_TRANSACTION` |

#### Sample:

```
"contract": {
  "clientRegion": {
    "attributeDescription": "Client Region",
    "values": [ "BY_TRANSACTION" ]
  }
}
```
---

## `settlementConfig`

| Name | Description | Allowed Values |
| -------- | ------- | ------- |
| `settlementMethod` | Settlement Method | `DE_DAILY_CUP`, `IFS_DAILY`, `IFS_MONTHLY_NEG`, `IFS_DAILY_NEG_CUP`, `DAILY`, `IFS_DAILY_CUP`, `DAILY_CUP`, `IFS_DAILY_NEG`, `IFS_TREASURY`, `DE_DAILY` |

#### Sample:

```
"settlementConfig": {
  "settlementMethod": {
    "attributeDescription": "Settlement Method",
    "values": [ "DAILY" ]
  }
}
```
---
