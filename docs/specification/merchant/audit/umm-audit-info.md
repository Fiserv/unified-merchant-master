# UMM Audit Info

* **Description**: Stores changes happening in each entities
* **Table Name**: `UMM.UMM_AUDIT_INFO`

## List of Fields for UMM Audit Info

### ID

* Description: Unique identifier of each record in this table.
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Number  |         |    38        |    NA     | NA     | NA |    NA     |

### TABLE_NAME

* Description: Name of the Table or entity got modified
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    100        |    NA     | NA     | NA |    NA     |

### MERCHANT_ID

* Description: Merchant# got modified
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    50        |    NA     | NA     | NA |    NA     |

### BE_PLATFORM_CODE

* Description:  Backend Platform of the merchant  
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     5    |    10        |    NA     | NA     | NA |    NA     |

### ACTION

* Description:  Operation perfomred on the entity
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum  |     5    |    10        |    NA     | NA     | NA |    NA     |

#### Valid Values

|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| `INSERT`     |   Addition of New Record      |
| `UPDATE`     |   Update of existing Record       |
| `DELETE`     |   Deletion of existing Record |

### AUDIT_COLUMN_NAME

* Description:  Specific column name got modified in a table
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     2    |    100        |    NA     | NA     | NA |    NA     |

### OLD_VALUE

* Description:  Old Value before modification
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    10000        |    NA     | NA     | NA |    NA     |

### NEW_VALUE

* Description:  New Value after modification
* API field: NA
* Applicable only for Update operation

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    10000        |    NA     | NA     | NA |    NA     |

### CHANGED_TIMESTAMP

* Description:   Date when insert/update/delete event occured  
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Timestamp   |     NA    |    NA        |    NA     | NA     | NA |    NA     |

### CHANGED_BY

* Description:   Who performed the change  
* API field: NA

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Timestamp   |     1    |    100        |    NA     | NA     | NA |    NA     |
