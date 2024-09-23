# Access UMM GraphQL APIs

UMM API uses OAuth 2.0 access token for requests authentication . Access token authenticates and authorizes via Google ApigeeX.

## Steps to integrate with UMM API

### Generate an API Key and Secret

Please contact <sanku.bairagya@fiserv.com>  for obtaining  application specific key and secret.

### Generate Token

```shell
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/token/generate' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic {base64(key:secret)}' \
--data-urlencode 'grant_type=client_credentials'
```

### Invoking UMM API with token

```shell
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/graphql' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {token}' \
--data {payload}
```

---

## Sample API Interactions

```http
POST /unifiedmerchantmaster/token/generate HTTP/1.1
Host: connect-dev.fiservapis.com
Content-Type: application/x-www-form-urlencoded
Authorization: Basic QWNVdVdi******************************VM0TWhxckc=
Content-Length: 29

grant_type=client_credentials
```

```http
POST /unifiedmerchantmaster/graphql HTTP/1.1
Host: connect-dev.fiservapis.com
x-consumer-name: umm
x-encrypted-data: true
Content-Type: application/json
Authorization: Bearer Iq695ADpfG6yo0sG7hwTdqN1mAa4
Content-Length: 784

{
"query":"query inquiry {
  getMerchant(merchantId: \"122204450888\", platformCode: NORTH) {
    __typename ... on Merchant {
      merchantId
      platformCode
      dbaName
      taxId
      addresses {
        city
      }
      products {
        entitlements {
          productCode
          productLongDesc
          attributes
        }
        equipments {
          productCode
          productLongDesc
          attributes
        }
        fees {
          productCode
          productLongDesc
          attributes
        }
        valueAddedServices {
          productCode
          productLongDesc
          attributes
        }
      }
    }
  }
}"
}
```
