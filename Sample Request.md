 Token Introspection API

##Introduction
This API enables partners to fetch metadata information about the access/refresh token. This enables partners to generate a fresh token when an access token expires. You can fetch access token data using the /introspectToken endpoint. 

## API Endpoint
``` HTTP
host: www.linkedin.com
basePath: /oauth/v2
endpoint: /introspectToken
method: POST
Content-Type: application/x-www-form-urlencoded
```


## Request Parameters

|       Name         |Description                         |Required                     |
|----------------|-------------------------------|-----------------------------|
|Client_ID|client ID generated            |Required          |
|PersonURN          |      URN for the access token    |     optional   |
Access token expiry|access token expiry period|optional|
Active |fetches active tokens|Required|
Access Token Created Time|duration when the access token was created|Required|
Last Authorized At|duration when the access token was last authorized|Required|

## Sample Request
```HTTP
POST /oauth/v2/introspect HTTP/1.1
```

## Sample Response
**Token revoke Response**
```JSON
curli -d 'token=AQWLmNqvW4JCbEePhbGpLhr7OesejxQC9YhxisJvIY2t6Pv8zCjGksak3NaLt4gBgU1dyV8SdX5X2fA1ebcJ7eVdvwX7Ii_m3pSr_2OveUf4NpAr5vnkeNJXa7av6KBn4IKQhJ7ao0YqI91g6miZ3puQBksYFoTtckOBVvH4z-T_C4it5kcVsGTKcvZn5aQ9JdNABKTLhSeoFu6Q52cRWWaT_jbdHU6E4jjazjNQUKOZiKA6h5pnh2ppSJcQUUwCvBiSfiA2oe205Kp3txqvYkPdkDrEHuCqlUHDixQhWcepWL3pkV4fKLLj9kNJq0X2dCRYLSuTCZXYuye6yYsDfxmwt1Dp_Q&client_id=84o1i5mjq59xuv&client_secret=Yn4GaPGMZSwmG2J3' https://www.linkedin-ei.com/oauth/v2/introspectToken -v -H "Content-Type: application/x-www-form-urlencoded"
  {
    "active": false,
    "client_id": "84o1i5mjq59xuv",
    "created_at": 1587497291083,
    "status": "revoked",
    "expires_in": 1587497620127,
    "scope": "r_basicprofile,rw_organization,w_share"
}
```
**Token Expiry Response**
``` JSON
{
    "active": false,
    "client_id": "84o1i5mjq59xuv",
    "authorized_at": 1587497291000,
    "created_at": 1587497291083,
    "status": "expired",
    "expires_in": 1587497620127,
    "scope": "r_basicprofile,rw_organization,w_share"
}
```

**Valid Token Response**
```JSON
{
    "active": true,
    "client_id": "84o1i5mjq59xuv",
    "authorized_at": 1587497291000,
    "created_at": 1587497291083,
    "status": "active",
    "expires_in": 1587497620127,
    "scope": "r_basicprofile,rw_organization,w_share"
}
```
**Client Information Mismatch Response**
```JSON
{
    "active": false
}
```

## Response Status Codes

| Status Code       |Description                         |
|----------------|-------------------------------|
| 401 |Invalid client credentials        |
| 401 |Access token verification results in `member_restricted`           |
| 429 |App reaches the fuse throttling for this endpoint       |

## Reference Content

>  [Tools Information](https://tools.ietf.org/html/rfc7662 )


