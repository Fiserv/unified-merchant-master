# Merchant Bank Account
* **Description**: description to come here .....
* **API section**: root 
* **Table Name**: UMM.MERCHANT 
## List of Fields:

### SEQUENCE_NUMBER
* Description: ABA/DDA occurrence sequence number of a bank.
* API field: `sequenceNumber`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

##### UMM Specification
| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| INTEGER  | 1        |    3        |    Available     | NA     |  Required  |    NA |         |

**Valid Values**: 
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     Bank Sequence Number   | 
| 2     |     Bank Sequence Number   | 
| 3     |     Bank Sequence Number   | 
| 4     |     Bank Sequence Number   | 
| 5     |     Bank Sequence Number   |

<!-- type: tab -->


##### North Specification 
| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Available   | NA   |  Required    | NA |         |

**Valid Values**: 
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| 1     |     Bank Sequence Number   | 
| 2     |     Bank Sequence Number   | 
| 3     |     Bank Sequence Number   | 
| 4     |     Bank Sequence Number   | 
| 5     |     Bank Sequence Number   |

<!-- type: tab --> 

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

##### GMA Specification
| Type   | Inquiry  |  Create  |    Update    |    Delete    |
|--------|:--------:|:--------:|:------------:|:------------:|
|       |     -    |          |              |       NA     |

<!-- type: tab-end -->
