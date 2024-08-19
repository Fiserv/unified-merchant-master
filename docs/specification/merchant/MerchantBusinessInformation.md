# Merchant Business Information

* **Description**: Stores essential information about merchants, including contact details, business type, and contractual data, ensuring efficient transaction processing and management. Every merchant has an entry in this critical repository.
* **API schema**: `merchantBusinessInformation`
* **Table Name**: `UMM.MERCHANT`

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required  |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required |    NA         |

<!-- type: tab-end -->
---

### PLATFORM_CODE

* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA       |    NA        |    Required     | Required     | Required |    Required   |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     |
| OMNIPAY26     |  Omnipay Backend ( GMA)      |
| SOUTH     |     South  Backend |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA       |    NA        |    Required     | Required     | Required |       NA      |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->
---

### LEGAL_ENTITY_TYPE_CODE

* Description: Code that indicates the type of legal merchant entity.
* API field: `legalEntityTypeCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA      |    Available     | Required     | Allowed |    NA    |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|PUBLIC_PRIVATE_CORP | Public/Private Corp|
|OTHER | Other|
|PROPRIETOR | Proprietorship|
|PARTNERSHIP | Partnership|
|ASSOCIATION_ESTATE_TRUST | Association/Estate/Trust|
|TAX_EXEMPT_GOVERNMENT | Tax Exempt/Government|
|INTERNATIONAL_ORG | International Org|
|LTD_LIABILITY_COMP | Limited Liability Compny|
|CO_OPERATIVE | Co-Operative|
|JOINT_STOCK_SPA | JOINT_STOCK-ITALY SPA|
|LLC | Limited|
|SOLE_TRADER | Sole Trader|
|PRIVATE_COMPANY | Private Company|
|PUBLIC_LIMITED_COMPANY | Plc|
|SOCIETE_ANONYME | CORPORATION-FRANCE SOCIETE ANONYME|
|EXTERNAL_COMPANY | External Company|
|LLC_GMBH | LLC-GERMANY GMBH|
|NON_PROFIT_ORGANIZATION | Non Profit Org|
|FOUNDATION | Foundation|
|CLOSED_CORPORATION | Closed Corp.|
|CO_OPERATIVE_SCRL | CO_OPERATIVE-BELGIUM SCRL|
|PUBLIC_COMPANY | Public Company|
|LIMITED_PARTNERS | Limited partners|
|PARTNERSHIP_SNC | PARTNERSHIP-FRANCE SNC|
|PARTNERSHIP | Partnership|
|LEGAL_FORM | Legal Form|
|PERSONAL_LIABILITY_COMPANY | Pers Liab Comp|
|NOT_APPLICABLE | Not Applicable|
|CHARITY | Charity|
|ASSOCIATIONS | Associations|
|BUSINESS_TRUST | Business Trust|
|JOINT_STOCK | Joint stock|
|CORPORATION | Corporation|
|NON_PROFIT_ORGANIZATION_ONLUS | NON_PROFIT_ORGANIZATION-ITALY ONLUS|
|GENERAL_PARTNERS | General partners|
|COMPANY | Company|
|CIVIL_LAW_ASSOCIATION | Civil Law Assoc.|
|ALTRO | Altro|
|NON_PROFIT_COMPANY | NonProfitCompany|
|OTHERS | Others|
|LLC_SRL | LLC-ITALY SRL|
|PROPRIETORSHIP | Sole proprietor|
|PROPRIETORSHIP_DITTA_INDIVIDUAL | PROPRIETORSHIP-ITALY DITTA INDIVIDUAL|
|SIMPLIFIED_SHAREHOLDER_COMPANY | SAS|
|INDIVIDUAL | Individual|
|TRUST | Trust|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA      |    Available     | Required     | Allowed |    NA    |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
|PUBLIC_PRIVATE_CORP | Public/Private Corp|
|OTHER | Other|
|PROPRIETOR | Proprietorship|
|PARTNERSHIP | Partnership|
|ASSOCIATION_ESTATE_TRUST | Association/Estate/Trust|
|TAX_EXEMPT_GOVERNMENT | Tax Exempt/Government|
|INTERNATIONAL_ORG | International Org|
|LTD_LIABILITY_COMP | Limited Liability Compny|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |       NA        |    NA      |    Available     | Required     | Allowed |    NA    |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:----------------------------------------------|
|CO_OPERATIVE | Co-Operative|
|JOINT_STOCK_SPA | JOINT_STOCK-ITALY SPA|
|LLC | Limited|
|SOLE_TRADER | Sole Trader|
|PRIVATE_COMPANY | Private Company|
|PUBLIC_LIMITED_COMPANY | Plc|
|SOCIETE_ANONYME | CORPORATION-FRANCE SOCIETE ANONYME|
|EXTERNAL_COMPANY | External Company|
|LLC_GMBH | LLC-GERMANY GMBH|
|NON_PROFIT_ORGANIZATION | Non Profit Org|
|FOUNDATION | Foundation|
|CLOSED_CORPORATION | Closed Corp.|
|CO_OPERATIVE_SCRL | CO_OPERATIVE-BELGIUM SCRL|
|PUBLIC_COMPANY | Public Company|
|LIMITED_PARTNERS | Limited partners|
|PARTNERSHIP_SNC | PARTNERSHIP-FRANCE SNC|
|PARTNERSHIP | Partnership|
|LEGAL_FORM | Legal Form|
|PERSONAL_LIABILITY_COMPANY | Pers Liab Comp|
|NOT_APPLICABLE | Not Applicable|
|CHARITY | Charity|
|ASSOCIATIONS | Associations|
|BUSINESS_TRUST | Business Trust|
|JOINT_STOCK | Joint stock|
|CORPORATION | Corporation|
|NON_PROFIT_ORGANIZATION_ONLUS | NON_PROFIT_ORGANIZATION-ITALY ONLUS|
|GENERAL_PARTNERS | General partners|
|COMPANY | Company|
|CIVIL_LAW_ASSOCIATION | Civil Law Assoc.|
|ALTRO | Altro|
|NON_PROFIT_COMPANY | NonProfitCompany|
|OTHERS | Others|
|LLC_SRL | LLC-ITALY SRL|
|PROPRIETORSHIP | Sole proprietor|
|PROPRIETORSHIP_DITTA_INDIVIDUAL | PROPRIETORSHIP-ITALY DITTA INDIVIDUAL|
|SIMPLIFIED_SHAREHOLDER_COMPANY | SAS|
|INDIVIDUAL | Individual|
|TRUST | Trust|

<!-- type: tab-end -->

---

### LEGAL_CONTACT_TITLE

* Description: Title or designation given to the legal contact person.
* API field: `legalContactTitle`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       1        |    30        |   Available     | Required     | Allowed |    NA    |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### CUSTOMER_SERVICE_PHONE_NUMBER

* Description: Phone number of the merchant customer serivce.
* API field: `customerServicePhoneNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |       10        |    15        |  Available     | Required     | Allowed |    NA    |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### SALES_TAX_EXEMPT_INDICATOR

* Description: Value that indicates whether the merchant is exempt from paying tax.
* API field: `salesTaxExemptIndicator`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |        NA       |    NA       |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NO | Sales Tax not exempted|
|YES | Sales Tax  exempted|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   |        NA       |    NA       |    Available     | Required     | Allowed |    NA   |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NO | Sales Tax not exempted|
|YES | Sales Tax  exempted|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### THIRD_PARTY_PROCESSOR_CODE

* Description: Code that indicates the third party payment processor.
* API field: `thirdPartyProcessorCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North , GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |    15       |    Available     | Required     | Allowed |    NA |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NONE | None|
|YAHOO | Yahoo|
|AUTH.NET | Authorize.Net|
|CYBERSOURCE | Cybersource|
|VERIFONE | Verifone|
|MER_LINK | Merchant Link|
|SHIFT4 | Shift 4|
|APRIVA | Apriva|
|FIS | FIS|
|SIX_PMT_SVC_GRP | Six Payment Svc Group|
|VERISIGN | Verisign|
|OTHER | Other|

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
|NONE | None|
|YAHOO | Yahoo|
|AUTH.NET | Authorize.Net|
|CYBERSOURCE | Cybersource|
|VERIFONE | Verifone|
|MER_LINK | Merchant Link|
|SHIFT4 | Shift 4|
|APRIVA | Apriva|
|FIS | FIS|
|SIX_PMT_SVC_GRP | Six Payment Svc Group|
|VERISIGN | Verisign|
|OTHER | Other|

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### HIGHEST_TICKET_AMOUNT

* Description: Maximum or highest amount of a single transaction that a customer makes at the merchant's establishment.
* API field: `highestTicketAmount`
* Field Specification:

<!-- type: tab 
titles: UMM, North , GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |            |    Available     | NA     | NA |   NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### KEYED_PERCENT

* Description: Percentage entered manually rather than being automatically calculated or derived from a system.
* API field: `keyedPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        1       |    5        |    Available     | Required     | Allowed |   NA    |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | Required   | Allowed   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### FIRST_ACTIVITY_DATE

* Description: Date on which the first activity was recorded.

Format: CCYY-MM-DD
Example: 2024-05-15

* API field: `firstActivityDate`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date |          10     |     10       |   Available     | NA     | NA | NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->

---

### THIRD_PARTY_PROCESSOR_TEXT

* Description: Name of the third party processor.
* API field: `thirdPartyProcessorName`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        10       |    15        |     Available     | NA     | NA |  NA |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   | NA   | NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab-end -->
---

### REGISTRATION_NUMBER

* Description: The merchant registration number is a field that is conditional based on the configuration setup of an institution. By default, this field is mandatory, but it can be made optional at the institution level. If the field is provided in the payload, it must have a minimum length of 5 characters. Note that this value will be encrypted before storage, as it is considered PII data. To ensure proper encryption, a minimum length of 5 characters is required.
* API field: `registrationNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        5       |     15       |    Available     | Optional     | Allowed |     NA  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
|   NA   |       NA       |    NA      |    NA    |      NA      |       NA     |       NA     |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        5       |     15       |    Available     | Optional     | Allowed |     NA  |

<!-- type: tab-end -->
---

### ANNUAL_SALES_AMOUNT

* Description: Contracted sales value for the merchant. Whether this value is per week, per month, per year, etc. is defined at institution level.
* API field: `annualSalesAmount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal |        3       |     38       |    Available     | Optional     | Allowed | NA  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |               |         | NA   | NA   | NA   |    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        3       |     18       |    Available     | Optional     | Allowed | NA  |

<!-- type: tab-end -->
---

### AVERAGE_TICKET_AMOUNT

* Description: Contracted average ticket value for the merchant. Whether this value is per week, per month, per year, etc. is defined at institution level.
* API field: `averageTicketAmount`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal |        3       |     38       |    Available     | Optional     | Allowed | NA  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        1       |      5     |   Available   | Optional   |  Allowed  |  NA    |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        4       |     39       |    Available     | Optional     | Allowed | NA  |

<!-- type: tab-end -->
---
