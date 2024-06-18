# Omnipay Merchant Attributes

The below section list the attributes grouped by **Domain**

## `contract`

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `clientRegion` |  `BY_COUNTRY`, `BY_TRANSACTION` | Client Region |

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

| Name | Allowed Values | Description |
| -------- | ------- | ------- |
| `settlementMethod` | `DE_DAILY_CUP`, `IFS_DAILY`, `IFS_MONTHLY_NEG`, `IFS_DAILY_NEG_CUP`, `DAILY`, `IFS_DAILY_CUP`, `DAILY_CUP`, `IFS_DAILY_NEG`, `IFS_TREASURY`, `DE_DAILY` | Settlement Method |

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
