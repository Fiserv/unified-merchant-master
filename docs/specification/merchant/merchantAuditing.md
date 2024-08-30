# UMM Audit Capability

UMM offers the functionality to track modifications made to each entity. Each entity includes columns for `EFFECTIVE_START_DATE` and `EFFECTIVE_END_DATE`, allowing users to access both the current and previous snapshots of records. The `EFFECTIVE_START_DATE` indicates when a record was added, while the `EFFECTIVE_END_DATE` indicates when a record was closed. Whenever the `EFFECTIVE_END_DATE` is null, it signifies the currently active record. By leveraging the combination of start and end dates, users can retrieve historical snapshots of records.

UMM has separate tables `UMM_AUDIT_INFO` & `UMM_AUDIT_ADDITIONAL_INFO` to track all changes happening in UMM database.

UMM also provides capability in Inquiry API to retrieve a snapshot of merchant data based on effective date.

---

## UMM Audit Info

* **Description**: Stores changes happening in each entities
* **Table Name**: `UMM.UMM_AUDIT_INFO`

### List of Fields for UMM Audit Info

<!-- type: tab 
titles: ID 
-->

* Description: Unique identifier of each record in this table.
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Number  |         |    38        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: TABLE_NAME 
-->

* Description: Name of the Table or entity got modified
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    100        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: MERCHANT_ID 
-->

* Description:  Merchant# got modified
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    50        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: BE_PLATFORM_CODE 
-->

* Description:  Backend Platform of the merchant  
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    10        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: ACTION 
-->

* Description:  Operation perfomred on the entity
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |     5    |    10        |    NA     | NA     | NA |    NA     |

#### Valid Values

|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| INSERT     |   Addition of New Record      |
| UPDATE     |   Update of existing Record       |
| DELETE     |   Deletion of existing Record|

<!-- type: tab-end -->

<!-- type: tab 
titles: AUDIT_COLUMN_NAME 
-->

* Description:  Specific column name got modified in a table
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     2    |    100        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: OLD_VALUE 
-->

* Description:  Old Value before modification
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    10000        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: NEW_VALUE 
-->

* Description:  New Value after modification
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    10000        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: CHANGED_TIMESTAMP 
-->

* Description:   Date when insert/update/delete event occured  
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Timestamp   |     NA    |    NA        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: CHANGED_BY 
-->

* Description:   Who performed the change  
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Timestamp   |     1    |    100        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

---

## UMM Audit Additional Info Table

* **Description**: Stores changes happening in each entities
* **Table Name**: `UMM.UMM_AUDIT_ADDITIONAL_INFO`

### List of Fields for UMM Audit Additional Info

<!-- type: tab 
titles: ID 
-->

* Description: Unique identifier of each record in UMM_AUDIT_INFO table.
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Number  |         |    38        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: TABLE_NAME 
-->

* Description: Name of the Table or entity got modified
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    100        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: KEY_COLUMN_NAME 
-->

* Description: Part of the parimay key ( apart from Merchant # and Platform code. )
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    100        |    NA     | NA     | NA |    NA     |

* For example, `MERCHANT_ATTRIBUTES` table has primary key on Merchant#, Platform code and attribute id.
* `UMM_AUDIT_INFO` will contain Merchant# and platform code as standard columns, where as third primary key
* `ATTRIBUTE_ID` will be stored under `KEY_COLUMN_NAME`

<!-- type: tab-end -->

<!-- type: tab 
titles: KEY_COLUMN_VALUE 
-->

* Description: Value of the KEY_COLUMN_NAME
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    600        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

<!-- type: tab 
titles: CREATED_DATE 
-->

* Description: Audit Date
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  |     10    |    10        |    NA     | NA     | NA |    NA     |

<!-- type: tab-end -->

---
