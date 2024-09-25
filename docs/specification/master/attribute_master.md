# Attribute Master

* **Description**: Stores attribute definition and tied with a domain.
* **Table Name**: `UMM.ATTRIBUTE_MASTER`

## List of Fields for UMM DOMAIN MASTER

### ID

* Description: Unique identifier of each record in this table, called attribute ID. 
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Number  |     NA    |    38        |    NA     | NA     | NA |    NA     |

---

### NAME

* Description: Name of the Attribute.
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    100        |    NA     | NA     | NA |    NA     |

---

### DESCRIPTION

* Description:  Detailed Description of the Attribute. 
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  |     1    |    500        |    NA     | NA     | NA |    NA     |

---

### DOMAIN_ID

* Description: ID from Domain Master table to link attribute with specific domain
* API field: NA
* Field Specification:

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Number  |     NA    |    38        |    NA     | NA     | NA |    NA     |

---