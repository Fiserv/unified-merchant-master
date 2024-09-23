# UMM Overview

## Motivation behind UMM

> Fiserv has multiple diverse and complex back-end merchant data stores that lack a uniform definition for products, fees, pricing, merchant accounts and acquiring hierarchy across platforms.

The disparity in data taxonomy and conflicting semantics among different systems has resulted in substantial gaps in documentation and the absence of a single source of truth about a merchant. Additionally, the reliance on the availability of back-end services to access necessary data, combined with the distinct formats utilized by each backend system, complicates efficient data utilization. The presence of multiple copies of merchant data in downstream systems, tailored for specific purposes, further adds to the complexity, creating significant friction in processes like onboarding, account maintenance, offering management, and product rollout. Reconciling data and conducting comprehensive analytics of merchant information is also extremely challenging due to the lack of a co-located, unified data repository.

## Solution

> To address these issues, the Unified Merchant Master (UMM) offers Single Unified Definition of products and offerings, fees, equipment and merchant demographic information.

## Solution Golas

* Unified/canonical data model for GBS Merchant Account and product offerings, hosted on a Snowflake Database
* CRUD Interface integrated with  Developer Studio with single Taxonomy and Metadata to simplify Integration using platform-agnostic  GraphQL API
* Realtime/batc bi-directional data Synch with Backend Merchant Masters to keep UMM in sync with backends
* Auditing and Notification for change events
* Low Maintenance through efficient framework and Management Portal to manage metadata definition

By unifying data and APIs, UMM simplifies the integration process, reducing complexity and the need for extensive custom development. The standardized data model and enhanced integration capabilities significantly reduce the maintenance overhead traditionally associated with managing multiple disparate systems. With a co-located, unified data repository in Snowflake, comprehensive and accurate analytics of merchant data become feasible, driving better business insights and decision-making.

## Functionality

* Merchant Onboarding
* Merchant Maintenance
* Merchant Inquiry
* Product Catalog
* Audit and Change notification
