# Equipment Product

* Product Code: Any Equipment Product  

Supported Equipment Products  can be retrieved using Product Inquiry API Call.

```http

GET https://connect.fiservapis.com/unifiedmerchantmaster/internal/v1/products?platformCode=$platform&productCategory=$category HTTP/1.1
x-consumer-name: $consumer-name
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

## Attributes

### Domain:equipmentFeatures

<!-- type: tab 
titles: UMM, North, GMA 
-->
| Attribute                    | Description                                       | Values        | Value Description                                         |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|
|autoCloseHhmm|Auto close HHMM|||
|equipmentFeatures|autoCloseMethod|Auto close method||
|equipmentFeatures|autoTidPopulate|Auto tid populate||
|equipmentFeatures|captureType1|Capture 1||
|equipmentFeatures|captureType2|Capture 2||
|equipmentFeatures|captureType3|Capture 3||
|equipmentFeatures|captureType4|Capture 4||
|equipmentFeatures|dialPrefix|Dial prefix||
|equipmentFeatures|dldId|Dld id||
|equipmentFeatures|forceSinglePayToken|Force single pay token||
|equipmentFeatures|ip|IP||
|equipmentFeatures|stepupRate|Step up rate||
|equipmentFeatures|stepupRateType|Step up rate type||
|equipmentFeatures|taEncryptionType|TA encryption type||
|equipmentFeatures|terminalClass|Terminal class||
|equipmentFeatures|transarmorSecurityLevel|Transarmor security level||
|equipmentFeatures|varPaymentMonths|Var payment months||
|equipmentFeatures|varPaymentPype|Var payment pype||
|equipmentFeatures|leaseTerm|Lease Term||
|equipmentFeatures|wholesaleMonthlyRentalCharge|Wholesale Monthly Rental Charge||
|equipmentFeatures|maintenanceCharge|Maintenance Charge||
|equipmentFeatures|resaleCharge|Resale Charge||
|equipmentFeatures|wholesaleMonthlyMaintenanceCharge|Wholesale Monthly Maintenance Charge||
|equipmentFeatures|serialNumber|Serial Number||
|equipmentFeatures|requestCreatedDate|Date when the equipment was requested||
|equipmentFeatures|salesRepId|Sales Rep associated with the equipment sale/lease||
|equipmentFeatures|dateAdded|Date when the equipment was installed||

<!-- type: tab -->

| Attribute                    | Description                                       | Values        | Value Description                                         |
|:-----------------------------|:--------------------------------------------------|:--------------|:----------------------------------------------------------|
|autoCloseHhmm|Auto close HHMM|||
|equipmentFeatures|autoCloseMethod|Auto close method||
|equipmentFeatures|autoTidPopulate|Auto tid populate||
|equipmentFeatures|captureType1|Capture 1||
|equipmentFeatures|captureType2|Capture 2||
|equipmentFeatures|captureType3|Capture 3||
|equipmentFeatures|captureType4|Capture 4||
|equipmentFeatures|dialPrefix|Dial prefix||
|equipmentFeatures|dldId|Dld id||
|equipmentFeatures|forceSinglePayToken|Force single pay token||
|equipmentFeatures|ip|IP||
|equipmentFeatures|stepupRate|Step up rate||
|equipmentFeatures|stepupRateType|Step up rate type||
|equipmentFeatures|taEncryptionType|TA encryption type||
|equipmentFeatures|terminalClass|Terminal class||
|equipmentFeatures|transarmorSecurityLevel|Transarmor security level||
|equipmentFeatures|varPaymentMonths|Var payment months||
|equipmentFeatures|varPaymentPype|Var payment pype||
|equipmentFeatures|leaseTerm|Lease Term||
|equipmentFeatures|wholesaleMonthlyRentalCharge|Wholesale Monthly Rental Charge||
|equipmentFeatures|maintenanceCharge|Maintenance Charge||
|equipmentFeatures|resaleCharge|Resale Charge||
|equipmentFeatures|wholesaleMonthlyMaintenanceCharge|Wholesale Monthly Maintenance Charge||
|equipmentFeatures|serialNumber|Serial Number||
|equipmentFeatures|requestCreatedDate|Date when the equipment was requested||
|equipmentFeatures|salesRepId|Sales Rep associated with the equipment sale/lease||
|equipmentFeatures|dateAdded|Date when the equipment was installed||

<!-- type: tab -->

<!-- type: tab-end -->

---
