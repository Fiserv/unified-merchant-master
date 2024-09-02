# Unified Merchant Master

Fiserv has multiple, diverse, and complex back-end merchant databases that lack a uniform definition for products, fees, pricing, merchant accounts, and acquiring hierarchy across platforms. The disparity in data taxonomy and conflicting semantics among different systems has resulted in substantial gaps in documentation and the absence of a single source of truth about a merchant. Additionally, the reliance on the availability of back-end services to access necessary data, combined with the distinct formats utilized by each backend system, complicates efficient data utilization. The presence of multiple copies of merchant data in downstream systems, tailored for specific purposes, further adds to the complexity, creating significant friction in processes like onboarding, account maintenance, offering management, and product rollout. Reconciling data and conducting comprehensive analytics of merchant information is also extremely challenging due to the lack of a co-located, unified data repository.
 
To address these issues, the Unified Merchant Master (UMM) offers a comprehensive solution by providing a Single Unified Definition of products and offerings, fees, equipment, and merchant demographic information. UMM establishes a unified or canonical data model for GBS Merchant Account and product offerings, hosted on a Snowflake Database and enhanced with a CRUD interface. It ensures real-time bi-directional synchronization with five back-end merchant master databases (North, Optis, South, Memphis, and OmniPay). This standardization of data and APIs facilitates seamless integration, reduces maintenance overhead, and enables the easy adoption of changes, thereby significantly cutting down the development time for merchant onboarding and maintenance activities.
 
By unifying data and APIs, UMM simplifies the integration process, reducing complexity and the need for extensive custom development. The standardized data model and enhanced integration capabilities significantly reduce the maintenance overhead traditionally associated with managing multiple disparate systems, and the development time required for merchant onboarding and maintenance activities is considerably accelerated. With a co-located, unified data repository in Snowflake, comprehensive and accurate analytics of merchant data become feasible, driving better business insights and decision-making. This results in improved data governance, operational efficiency, and advanced analytics capabilities, ultimately ensuring consistent, accurate, and actionable merchant data across the organization.

UMM provides access to data through direct Snowflake access or a unified API.

The unified API supports below operations for supported back-end platforms:

    •Merchant Onboarding 
    •Merchant Maintenance 
    •Merchant Inquiry  

## Supported Backend Platforms

Please find list of supported Backend Platforms [here](?path=docs/specification/supportedPlatforms.md)

## Integration Options

UMM supports two ways to integrate:

<!-- type: row -->

<!-- type: card
title: UMM API 
description: Use GraphQL queries to retrieve or manage merchant data as well as Rest APIs for UMM Master Data definition.
link: ?path=docs/getting-access/api-access.md
-->

<!-- type: card
title: Direct Access to UMM Snowflake Database
description: Consumer will have full read access to UMM Snowflake database and can use the data to Synch with their application incrementally or periodically.
link: ?path=docs/getting-access/database-access.md
-->

<!-- type: row-end -->

---

## Getting Started using UMM

Start here with UMM documentation [here](?path=docs/specification/readMe.md)
