# Tradesolution API authentication 
Tradesolution protect its APIs with OAUTH2 using bearer tokens/access tokens. If you need your systems to talk to ours, please contact us at post@tradesolution.no to get clientId and secret.

## How to get a bearer token
To get a bearer token that can be used against Tradesolution APIs, your system must do a POST call like this:

`POST https://login.microsoftonline.com/trades.no/oauth2/v2.0/token`

### Headers
`Content-Type: application/x-www-form-urlencoded`


### Body
`client_id=<insert_client_id>&client_secret=<insert_secret>&grant_type=client_credentials&scope=https://trades.no/TradesolutionApi/.default`

### Response
```
{
  "access_token": "eyJhbG*****",
  "expires_in": 36000,
  "token_type": "Bearer",
  "ext_expires_in": 36000
}
```
The token is valid for 10 hours

## How to use the bearer token 
Add the access_token to all request headers going to our APIs

### Headers
`Authorization: Bearer <access_token>`

## Some of our API's
- [EpdApi](https://epdapi.tradesolution.no/swagger/index.html)
- [MediastoreApi](https://mediastore.tradesolution.no/api/swagger/index.html)
- [KjederegisteretApi](https://kjederegisteretapi.tradesolution.no/swagger/index.html)
- [SalgsApi](https://salgsapi.tradesolution.no/swagger/index.html)
