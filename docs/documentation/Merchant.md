

# Merchant


## Properties


| Name                            | Type                                                           | Description                                      | North                                                                           | South                                                                           | GMA                                                                            | Optis                                                                           |
|---------------------------------|----------------------------------------------------------------|--------------------------------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **merchantId**                  | **String**                                                     | Merchant Id                                      | <ul><li>max length : 12</li><li>min length : 12</li><li>Updatable: No</li></ul> | <ul><li>max length : 11</li><li>min length : 11</li><li>Updatable: No</li></ul> | <ul><li>max length : 7</li><li>min length : 7</li><li>Updatable: No</li></ul>  | <ul><li>max length : 16</li><li>min length : 16</li><li>Updatable: No</li></ul> |
| **platformCode**                | [**PlatformCodeEnum**](#PlatformCodeEnum)                      | Back-end platform code                           | "NORTH"                                                                         | "SOUTH"                                                                         | "GMA26"                                                                        | "OMAHA"                                                                         |
| **dbaName**                     | **String**                                                     | Merchant Doing Business As name aka trading name | <ul><li>max length : 24</li><li>min length : 4</li><li>Updatable: No</li></ul>  | <ul><li>max length : 30</li><li>min length : 4</li><li>Updatable: No</li></ul>  | <ul><li>max length : 30</li><li>min length : 4</li><li>Updatable: No</li></ul> | <ul><li>max length : 40</li><li>min length : 4</li><li>Updatable: No</li></ul>  |
| **legalName**                   | **String**                                                     | Legal Name of the merchant                       | <ul><li>max length : 24</li><li>min length : 4</li><li>Updatable: No</li></ul>  | <ul><li>max length : 30</li><li>min length : 4</li><li>Updatable: No</li></ul>  | <ul><li>max length : 30</li><li>min length : 4</li><li>Updatable: No</li></ul> | <ul><li>max length : 40</li><li>min length : 4</li><li>Updatable: No</li></ul>  |
| **merchantAttributes**          | **Map&lt;String, Object&gt;**                                  | TBD                                              | <ul><li>max length : 12</li><li>min length : 12</li><li>Updatable: No</li></ul> | <ul><li>max length : 11</li><li>min length : 11</li><li>Updatable: No</li></ul> | <ul><li>max length : 7</li><li>min length : 7</li><li>Updatable: No</li></ul>  | <ul><li>max length : 16</li><li>min length : 16</li><li>Updatable: No</li></ul> |
| **merchantBusinessInformation** | [**MerchantBusinessInformation**](MerchantBusinessInformation.md) | TBD                                              | <ul><li>max length : 12</li><li>min length : 12</li><li>Updatable: No</li></ul> | <ul><li>max length : 11</li><li>min length : 11</li><li>Updatable: No</li></ul> | <ul><li>max length : 7</li><li>min length : 7</li><li>Updatable: No</li></ul>  | <ul><li>max length : 16</li><li>min length : 16</li><li>Updatable: No</li></ul> |


## Enum: PlatformCodeEnum

| Name | Value |
|---- | -----|
| NORTH | &quot;NORTH&quot; |
| OMAHA | &quot;OMAHA&quot; |
| SOUTH | &quot;SOUTH&quot; |