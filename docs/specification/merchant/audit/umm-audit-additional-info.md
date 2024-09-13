# UMM Audit Additional Info Table

* **Description**: Stores changes happening in each entities
* **Table Name**: `UMM.UMM_AUDIT_ADDITIONAL_INFO`

## List of Fields for UMM Audit Additional Info

### ID

* Description: Unique identifier of each record in UMM_AUDIT_INFO table.
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

### KEY_COLUMN_NAME

* Description: Part of the parimay key ( apart from Merchant # and Platform code. )
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    100        |    NA     | NA     | NA |    NA     |

* For example, `MERCHANT_ATTRIBUTES` table has primary key on Merchant#, Platform code and attribute id.
* `UMM_AUDIT_INFO` will contain Merchant# and platform code as standard columns, where as third primary key
* `ATTRIBUTE_ID` will be stored under `KEY_COLUMN_NAME`

### KEY_COLUMN_VALUE

* Description: Value of the `KEY_COLUMN_NAME`
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    600        |    NA     | NA     | NA |    NA     |

### CREATED_DATE

* Description: Audit Date
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Date  |     10    |    10        |    NA     | NA     | NA |    NA     |
