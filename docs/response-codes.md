# Response Codes

Every GraphQL (inquiry/mutation) request to Unified Merchant Master, UMM returns a standard HTTP 200 status code. In case of an error, the reponse body will contain a `error` property, which in turn will contain the relevant HTTP status code

## HTTP Status Codes

HTTP status code indicates the result of an API call. 

For every successful or unsuccessful operation, one of the following HTTP Status Code is returned in the response message:

| HTTP Status Code | Description |
|---|---|
| `200  OK` | Successful request |
| `201  Created` | Successfully created a new resource |
| `400  Bad request` | Server is unable to process the request due to invalid syntax |
| `401  Unauthorized` | Invalid authentication credentials |
| `403  Forbidden` | Forbidden to access the valid URL |
| `404  Not found` | Server unable to find the requested resource |
| `405  Method not allowed` | Method not allowed |
| `422  Un-processable Entity` | Server is unable to process the request due to semantic errors |
| `500  Internal Server Error` | Server encountered an unexpected error while processing the request |
| `503  Service Unavailable` | Service is temporarily unavailable due to overload or maintenance activity |
