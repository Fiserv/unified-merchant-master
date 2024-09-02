# What does this specification cover?

Read this document to understand UMM data specifications across different back ends that UMM supports.
Consumers can use UMM data in two different ways -

* API
* Snowflake Database as a Canonical data source

## This documentation covers specifications for both ways and provides in depth details on what consumer needs to know to start using the UMM data

## General Construct of the UMM Data Store

* Three Fundamental Models used by UMM to store merchant data
  * Entity: Merchant data in UMM is logically grouped under multiple entities and stored as tables in Snowflake as well as represented in UMM APIs.
    See the [Entities](#entities) section for the full list of entities UMM has and click on each entity to further reading.
  * Product: UMM maintains a list of products to represent subscribed card entitlements,fees, payment features, value added services and equipments.
  Additional information about product can be found [here](?path=docs/specification/merchant/merchantProduct.md)
  * Attribute: Related fields logically grouped under a domain and stored as key value pair. This construct is used at both merchant level and product level.
    * Additional information about `Merchant Level Attributes` can be found [here](?path=docs/specification/merchant/merchantAttributes.md)
    * Additional information about `Product Level Attribute` can be found [here](?path=docs/specification/merchant/merchantProductAttributes.md)
* Each entity has the below columns as part of their key
  * `MERCHANT_ID`: Unique Identifier for the Merchant
  * `PLATFORM_CODE`: Identifies the Backend Platform the merchant is on. Supported platforms on UMM can be found [here](?path=docs/specification/supportedPlatforms.md)
  * `EFFECTIVE_START_DATE`: UMM audits and stores snapshot record of Merchant data for all entities. This date is when a record was added to the merchant.
  * `EFFECTIVE_END_DATE`: When there is change in any entity record for a merchant UMM snapshots the earlier record with previous date and creates a new record with this field set to NULL. Therefore, any record which is active at this moment will have this field as NULL.
Read [Auditing page](?path=docs/specification/merchant/merchantAuditing.md) for further information on Auditing with examples.

## Entities

* [Merchant](?path=docs/specification/merchant/merchant.md):Stores basic but critical information about the merchant. Any merchant in UMM will always have this entity.
* [Merchant Business Information](?path=docs/specification/merchant/merchantBusinessInformation.md): This entity stores information about the business of the merchant.
* [Merchant Attributes](?path=docs/specification/merchant/merchantAttributes.md): This entity stores various merchant attributes grouped under logical domains.
* [Merchant Hierarchy](?path=docs/specification/merchant/MerchantHierarchy.md): Hierarchy of the merchant.
* [Address](?path=docs/specification/merchant/MerchantAddress.md): All addresses on file for a merchant.
* [Owner](?path=docs/specification/merchant/MerchantOwner.md) : Ownership details of the merchant business.
* [Merchant Bank Account](?path=docs/specification/merchant/MerchantBankAccount.md): This entiry stores the bank accounts for a specific merchant.
* [Merchant Cross Reference](?path=docs/specification/merchant/Merchant_Xref.md): This entiry stores the cross references for a specific merchant.
* [Merchant IRS Information](?path=docs/specification/merchant/Tax_Adtnl_Data_US.md): All tax related information for a merchant.
* [Products](?path=docs/specification/merchant/merchantProduct.md) : Stores all entitlements, services, equipments fees a merchant has and further segregated into following logical groups
  * [Entitlements](?path=docs/specification/merchant/merchantProduct.md) : Contains all acquiring entitlements e.g. MasterCard, VISA etc.
  * [Fees](?path=docs/specification/merchant/merchantProduct.md) : All fees for a merchant.
  * [Value Added Services](?path=docs/specification/merchant/merchantProduct.md): Example of Value Added services would be TransArmor, Auth Optimization
