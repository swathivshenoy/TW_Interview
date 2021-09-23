 Token Introspection API

This API enables partners to fetch metadata information about the access/refresh token. This enables partners to generate a fresh token when an access token expires.


## API Request

POST [/oauth/v2/introspecttoken]



## Request Parameters
|
|       Name         |Description                         |Required                     |
|----------------|-------------------------------|-----------------------------|
|Client_ID|client ID generated            |Required          |
|PersonURN          |      URN for the access token    |     optional   |
Access token expiry/TTL |access token expiry period|optional|
Active |fetches active tokens|Required|
access Token Created Time|duration when the access token was created|Required|
Last Authorized At|duration when the access token was last authorized|Required|









 


## Sample Request

`

**POST [/oauth/v2/introspect](https://www.linkedin-ei.com/oauth/v2/introspect)** **HTTP/1.1**
