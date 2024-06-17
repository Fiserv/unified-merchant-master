# Access UMM GraphQL APIs

UMM API uses OAuth 2.0 access token for requests authentication . Access token authenticates and authorizes via Google ApigeeX.

## Steps to integrate with UMM API 

#### Step 1 : Generate an API Key and Secret

Please contact <sanku.bairagya@fiserv.com>  for obtaining  application specific key and secret.

#### Step 2: Generate Token
```
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/token/generate' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic {base64(key:secret)}' \
--data-urlencode 'grant_type=client_credentials'
```

#### Stpe 3: Invoking UMM API with token 
```
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/graphql' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {token}' \
--data {payload}
```
---
