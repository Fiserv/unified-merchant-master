# Product Attributes

* **Description**: <**$ Sample - to be updated**....>
 List of fields grouped under logical **Domains** and stored as key-value(s) pair as attributes.
  * Example of a **Domain**: chargebackConfig is a **domain** that groups all fields called as **Attributes** those configures chargeback related processing for a merchant. Example of some attributes are:
    * Chargeback Address code indicating where chargeback related information sent
    * Chargeback Pre-note Days
  * See [list of Domains](#list-of-domains)
* **API section**: productAttributes
* **Table Name**: UMM.MERCHANT_PRODUCT
* **How to Retrieve attributes from Snowflake Data tables?**: **<$ sample - to be updated>**
  * Master Tables: Attributes are defined using two Master tables in UMM
    * UMM.DOMAIN_MASTER : Contains the definition of the Domain
    * UMM.ATTRIBUTE_MASTER: Contains the definition of the attributes and tied to Domain
  * UMM.MERCHANT_ATTRIBUTES stores the ID of the UMM.ATTRIBUTE_MASTER for each attributes
  * Sample Query to pull the attributes:

  ```text

 _< $ Sample - to be updated >_

  ```

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String   | 12        |    12        | Required   | Required   | Required   | Required     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required  |       NA     |

<!-- type: tab-end -->

---

### PLATFORM_CODE

* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: platformCode
* Field Specification: See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)


<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |     40      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### PRDCT_CODE

* Description: Unique identifier assigned to a specific product for tracking and inventory purposes.
* API field: productCode
* Field Specification: _< $ sample - to be updated/checked>_  See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)


<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |    100      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### UNIQUE_IDENTIFIER

* Description: Distinct code to uniquely identify an entity within a system.
* API field: < _Not known / NA _ >
* Field Specification: _< $ sample - to be updated/checked>_  See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar |      NA       |     50      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### ATTRIBUTE_ID 

* _< $ sample - to be updated/checked>_
* Description: UMM defined attribute ID. See the query above for further details.
* API field: Not applicable - domain and attribute name along with respective descriptions are returned. Sample payload shows the domain  and the list of attributes under that domain.
  * Please see [List of Domains](#list-of-domains) for available domains and attributes.

```text

_< $ sample - to be updated/checked>_
              

```
<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Number  |      0         |     38     |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---

### EFFECTIVE_START_DATE

* Description: Date from which a particular product attribute becomes valid and applicable, used to manage changes and track historical data.
* API field: effectiveStartDate
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Date    |      N/A       |     NA      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->

---


### EFFECTIVE_END_DATE

* Description: Date on which a particular product attribute or record is no longer valid or applicable.
* API field: effectiveEndDate
* Field Specification: 

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Date    |      N/A       |     NA      |   NA   |  NA   |  NA   |

<!-- type: tab-end -->


---

* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type    | Minimum Length | Max Length | Inquiry | Create | Update |
|---------|:--------------:|:----------:|:-------:|:------:|:------:|
| Numeric |      N/A       |     6      |   N/A   |  N/A   |  N/A   |

<!-- type: tab-end -->

---

### VALUE

* Description: Value of the Attribute
* API field: values[0]  _< $ sample - to be updated/checked>_
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type     | Minimum Length | Max Length | Inquiry | Create | Update |
|----------|:--------------:|:----------:|:-------:|:------:|:------:|
| Varchar  |      1       |    200     |   Available   |  Optional   |  Allowed   |

*  _< $ sample - to be updated/checked>_
  
<!-- type: tab-end -->

---

### Product Attributes

* See **Entitlements** attribute [here](?path=docs/specification/merchant/prodAttributes_Entitlements.md)
* See **Fees** attrubute [here](?path=docs/specification/merchant/productAttributes_fees.md)
* See **Value Added Services (VAS)** attribute [here](?path=docs/specification/merchant/productAttributes_VAS.md)
