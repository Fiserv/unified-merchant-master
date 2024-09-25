# Fee Product List

* Product Code: Any Fee Product  

Supported Fee Products  can be retrieved using Product Inquiry API Call. [Explore API](../api/?type=get&path=/internal/v1/products&branch=develop&version=1.0.0)

```http

GET https://connect.fiservapis.com/unifiedmerchantmaster/internal/v1/products?platformCode=$platform&productCategory=$category HTTP/1.1
x-consumer-name: $consume-name
x-encrypted-data: true

$category can have below Values: 

          - ENTITLEMENT
          - VAS
          - EQUIPMENT
          - PAYMENT_FEATURE
          - FEE

$platform can have below Values: 

          - NORTH
          - OMAHA
          - SOUTH
          - OMNIPAY26
          - OMNIPAY21

```

* Attribute List by Domain:

## feeAttr

---

 tags: [feeAttr]

---

<!-- type: tab 
titles: UMM, North, GMA 
-->


| Attribute                    | Description                                       | Values        | Value Description                                         | 
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|
| frequencyInd                 | Frequency Indicator                               | S             |  Special                                                  |
| frequencyInd                 | Frequency Indicator                               | B             |  BI_WEEKLY                                                |
| frequencyInd                 |Frequency Indicator                                | M             |  MONTHLY                                                  |
| frequencyInd                 |Frequency Indicator                                | D             |  DAILY                                                    |
| frequencyInd                 |Frequency Indicator                                | X             |   DELAYED_BILLING                                         |
| processingInd                | Processing Indicator                              | 1             |  Processing Indicator 1                                   |
| processingInd                | Processing Indicator                              | 2             |  Processing Indicator 2                                   |
| processingInd                | Processing Indicator                              | 3             |  Processing Indicator 3                                   |
| processingInd                | Processing Indicator                              | 4             |  Processing Indicator 4                                   |
| processingInd                | Processing Indicator                              | 5             |  Processing Indicator 5                                   |
| retailDate                   | Retail Date                                       | -             |  -                                                        |
| wholesaleDate                | Wholesale Date                                    | -             |  -                                                        |

<!-- type: tab -->

| Attribute                    | Description                                       | Values        | Value Description                                         | 
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|
| frequencyInd                 | Frequency Indicator                               | S             |  Special                                                  |
| frequencyInd                 | Frequency Indicator                               | B             |  BI_WEEKLY                                                |
| frequencyInd                 |Frequency Indicator                                | M             |  MONTHLY                                                  |
| frequencyInd                 |Frequency Indicator                                | D             |  DAILY                                                    |
| frequencyInd                 |Frequency Indicator                                | X             |   DELAYED_BILLING                                         |
| processingInd                | Processing Indicator                              | 1             |  Processing Indicator 1                                   |
| processingInd                | Processing Indicator                              | 2             |  Processing Indicator 2                                   |
| processingInd                | Processing Indicator                              | 3             |  Processing Indicator 3                                   |
| processingInd                | Processing Indicator                              | 4             |  Processing Indicator 4                                   |
| processingInd                | Processing Indicator                              | 5             |  Processing Indicator 5                                   |
| retailDate                   | Retail Date                                       | -             |  -                                                        |
| wholesaleDate                | Wholesale Date                                    | -             |  -                                                        |

<!-- type: tab -->
<!-- type: tab-end -->

---
