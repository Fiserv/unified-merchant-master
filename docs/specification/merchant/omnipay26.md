# Omnipay26 Merchant Specification

## Base Properties

| Name | Min Length | Max Length | Pattern |
|---|---|---|---|
| merchantId | 8 | 8 | `^[0-9]{8,8}$` |
| merchantHierarchies | [View Details](#merchantmierarchies) | [View Description](#merchantmierarchies) | [View Details](#merchantmierarchies) |

## Merchant Hierarchies

| Name | Min Length | Max Length | Pattern |
|---|---|---|---|
| hierarchyMerchantId | 8 | 8 | `^[0-9]{8,8}$` |
| hierarchyLevelCode | 5 | 9 | |

## Attributes

<!-- theme: info -->
Refer to [Attribute documentation](?path=docs/attribute/merchant/omnipay26.md) for more details
