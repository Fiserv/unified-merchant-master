# What does this specification cover?

This document will help you to understand the UMM data specification that enables UMM to support multiple different back ends.

Consumers can use UMM data in two different ways -

* API
* Snowflake Database as a Canonical data source

> This documentation covers specifications for both way and provides in depth details on what any consumer needs to know in order to start using the UMM data

## General construct of the data store

Three Fundamental Models used by UMM to store merchant data

> **Entity**: Merchant data in UMM is logically grouped under multiple entities and stored as tables in Snowflake as well as represented in UMM APIs. See the [Entities](#entities) section for the full list of entities UMM has and click on each entity to further reading.
>
> **Product**: UMM maintains a list of products to represent subscribed card entitlements,fees, payment features, value added services and equipments. Additional information about product can be found [here](?path=docs/specification/merchant/merchantProduct.md)
>
> **Attribute**: Related fields logically grouped under a domain and stored as key value pair. This construct is used at both merchant level and product level. For additional information see [Merchant Level Attributes](?path=docs/specification/merchant/merchantAttributes.md) and [Product Level Attribute](?path=docs/specification/merchant/merchantProductAttributes.md)

Each entity has the below columns as part of their key

* `MERCHANT_ID`: Unique Identifier for the Merchant
* `PLATFORM_CODE`: Identifies the Backend Platform the merchant is on. Supported platforms on UMM can be found [here](?path=docs/specification/supportedPlatforms.md)
* `EFFECTIVE_START_DATE`: UMM audits and stores snapshot record of Merchant data for all entities. This date is when a record was added to the merchant
* `EFFECTIVE_END_DATE`: When there is change in any entity record for a merchant UMM snapshots the earlier record with previous date and creates a new record with this field set to NULL. Therefore, any record which is active at this moment will have this field as `NULL`

Each entity will provide a comprehensive list of all fields/columns it has , including their specifications such as minimum and maximum length, data type, allowable values (if applicable). Additionally, it will detail the corresponding API field name, indicate if the field is a mandatory component of the onboarding request, and specify whether it can be modified via an API call.

Moreover, each field will have tabs for UMM and specific backend , providing detailed information on the data type, restrictions, and allowable values for both UMM and the respective backend systems. For instance, the UMM tab will include allowable values specific to UMM, regardless of the backend system, while the backend-specific tab will list allowable values tailored to that particular backend. For instance, if a field can support values 'a' and 'b' for the North backend, and value 'C' for Omnipay GMA, UMM will list values 'a', 'b', and 'c' under the UMM tab. In contrast, the North backend tab will display values 'a' and 'b', while the GMA tab will list value 'C' only.

Refer to UMM's [Auditing strategy](?path=docs/specification/merchant/audit/merchantAuditing.md) for additional information.

## Entities

* [Merchant](?path=docs/specification/merchant/merchant.md): Stores basic but critical information about the merchant. Any merchant in UMM will always have this entity
* [Merchant Business Information](?path=docs/specification/merchant/merchantBusinessInformation.md): This entity stores information about the business of the merchant
* [Merchant Attributes](?path=docs/specification/merchant/merchantAttributes.md): This entity stores various merchant attributes grouped under logical domains
* [Merchant Hierarchy](?path=docs/specification/merchant/MerchantHierarchy.md): Hierarchy of the merchant
* [Merchant Address](?path=docs/specification/merchant/MerchantAddress.md): All addresses on file for a merchant
* [Merchant Owner](?path=docs/specification/merchant/MerchantOwner.md): Ownership details of the merchant business
* [Merchant Bank Account](?path=docs/specification/merchant/MerchantBankAccount.md): This entiry stores the bank accounts for a specific merchant
* [Merchant Cross Reference](?path=docs/specification/merchant/Merchant_Xref.md): This entiry stores the cross references for a specific merchant
* [Merchant IRS Information](?path=docs/specification/merchant/Tax_Adtnl_Data_US.md): All tax related information for a merchant
* [Merchant Products](?path=docs/specification/merchant/merchantProduct.md): Stores all entitlements, services, equipments fees a merchant has and further segregated into following logical groups
  * [Entitlements](?path=docs/specification/products_entitlements.md): Contains all acquiring entitlements e.g. MasterCard, VISA etc. [🔗](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
  * [Equipment](?path=docs/specification/products_equipments.md): Contains all acquiring entitlements e.g. MasterCard, VISA etc. [🔗](?path=docs/specification/merchant/productAttributes_equipment.md)
  * [Fees](?path=docs/specification/products_fees.md): All fees for a merchant [🔗](?path=docs/specification/merchant/productAttributes_fees.md)
  * [Value Added Services](?path=docs/specification/products_vas.md): Example of Value Added services would be TransArmor, Auth Optimization etc. [🔗](?path=docs/specification/merchant/productAttributes_VAS.md)
