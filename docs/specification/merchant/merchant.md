# Merchant
* **Description**: Stores basic but critical information about the merchant. Any merchant in UMM will always have this entity.
* **API section**: root 
* **Table Name**: UMM.MERCHANT 
## List of Fields:
### MERCHANT_ID
* Description: Backend unique identifier for a merchant.
* API field: merchantId
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type |Minimum Length|Max Length| Inquiry | Create  | Update  |
|------|:----------:|:--------:|:--------:|:-------:|:-------:|
|String|BE specific|50|Required|Required|Required|

<!-- type: tab-->

##### North Specification
| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       12       |     12     |Required|Required|Required|

<!-- type: tab--> 

##### South Specification

| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       11       |     11     |Required|Required|Required|

<!-- type: tab-->

##### GMA Specification
| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       11       |     11     |Required|Required|Required|

<!-- type: tab-end -->

---

### PLATFORM_CODE 
* Description: Backend platform identifier e.g. North, South etc.
* API field: platformCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

##### UMM Specification
| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
| ENUM |      N/A       |     40     |Required|Required|Required|

See supported platform and values of the enum [here](?path=docs/specification/supportedPlatforms.md)
<!-- type: tab-end -->
---
### HIERARCHY_LEVEL_CODE 
* Description: Indicates the hierarchy level of the merchant.
* API field: hierarchyLevelCode
* Field Specification:

<!-- type: tab 
titles: UMM, North, South, GMA 
-->

##### UMM Specification
| Type |Minimum Length|Max Length| Inquiry | Create  | Update  |
|------|:----------:|:--------:|:--------:|:-------:|:-------:|
|String|BE specific|50|Required|Required|Required|

<!-- type: tab-->

##### North Specification
| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       12       |     12     |Required|Required|Required|

<!-- type: tab--> 

##### South Specification

| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       11       |     11     |Required|Required|Required|

<!-- type: tab-->

##### GMA Specification
| Type | Minimum Length | Max Length | Inquiry | Create  | Update  |
|------|:--------------:|:----------:|:--------:|:-------:|:-------:|
|String|       11       |     11     |Required|Required|Required|

<!-- type: tab-end -->