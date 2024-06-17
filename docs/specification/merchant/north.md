# North Merchant Specification

## Base Properties

| Name | Min Length | Max Length | Pattern |
|---|---|---|---|
| `merchantId` | 8 | 50 | `^[0-9]{8}$` |
| `owners` | [View Details](#owners) | [View Details](#owners) | [View Details](#owners) |

## Owners

| Name | Min Length | Max Length | Pattern |
|---|---|---|---|
| `firstName` | 20 | 100 | `^[a-zA-Z]*$` |
| `middleName` | 20 | 100 | `^[a-zA-Z]*$` |
| `lastName` | 20 | 100 | `^[a-zA-Z]*$` |
| `title` | 20 | 80 | `^[a-zA-Z]*$` |

## Attributes

<!-- theme: info -->
Refer to [Attribute documentation](?path=docs/attribute/merchant/north.md) for more details
