# Authentication

UMM APIs use OAuth 2.0 access token to authenticate requests. Your access token authenticates and authorizes you to use the UMM API server served via Google ApigeeX.

To integrate with UMM API(s), you'll need to exchange newly generated Key and Secret for an access token.

Please contact <sanku.bairagya@fiserv.com> and/or <mukesh.kumar3@fiserv.com> for obtaining your application specific key and secret.

## Generating Token
```
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/token/generate' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic {token}' \
--data-urlencode 'grant_type=client_credentials'
```

## Invoking UMM API with token
```
curl --location 'https://connect.fiservapis.com/unifiedmerchantmaster/graphql' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {token}' \
--data {payload}
```
