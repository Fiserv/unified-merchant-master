# What does this specification cover?
 
Read this document to understand UMM data specifications across different back ends that UMM supports.
Consumers can use UMM data in two different ways -
* API
* Snowflake Database as a Canonical data source

#### This documentation covers specifications for both ways and provides in depth details on what consumer needs to start using the UMM data.

# General Construct of the UMM Data Store

* Merchant data in UMM is logically grouped under multiple entities and stored as tables in Snowflake as well as represented in UMM APIs. 
See the [`List of Entities`](#Entities) section for the full list of entities UMM has and click on each entity to further reading.
* Each entity has the below columns as part of their key
    * MERCHANT_ID : Unique Identifier for the Merchant
    * PLATFORM_CODE: Identifies the Backend Platform the merchant is on. Supported platforms on UMM can be found [here](?path=docs/specification/supportedPlatforms.md)
    * EFFECTIVE_START_DATE : UMM audits and stores snapshot record of Merchant data for all entities. This date is when a record was added to the merchant. 
    * EFFECTIVE_END_DATE : When there is change in any entity record for a merchant UMM snapshots the earlier record with previous date and creates a new record with this field set to NULL. Therefore, any record which is active at this moment will have this field as NULL.<p></p>  
Read [Auditing page](?path=docs/specification/merchant/merchantAuditing.md) for further information on Auditing with examples.

      
# Entities
* [Merchant](?path=docs/specification/merchant/merchant.md):Stores basic but critical information about the merchant. Any merchant in UMM will always have this entity.
* [Merchant Business Information](?path=docs/specification/merchant/merchantBusinessInformation.md): This entity stores information about the business of the merchant.
* Merchant Hierarchy: Hierarchy of the merchant.
* Address: All addresses on file for a merchant. 
* Owner : Ownership details of the merchant business. 
* Products : Stores all products, services, equipments fees a merchant has and further segregated into following logical groups
  * Entitlements : Contains all acquiring entitlements e.g. MasterCard, VISA etc.
  * Fees : All fees for a merchant.
  * Value Added Services: Example of Value Added services would be TransArmor, Auth Optimization
  * Payment Features:
  * TBD: List Other groups
* TBD: List other entities
