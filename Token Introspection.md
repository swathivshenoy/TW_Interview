# Getting Started

Token Api introspection API will help the partners to generate access/refresh token and return metadata information. 

# URL 

https://www.linkedin.com/oauth/v2/introspectToken

# Header

| Header Name  | Description            | Required | Notes |
| ------------ | ---------------------- | -------- | ----- |
| Content-Type | x-www-form-url-encoded | Required |       |

# Methods

| Method | Description                 | Notes |
| ------ | --------------------------- | ----- |
| POST   | Token Introspection Request |       |

# Query Parameters

| Element   | Description           | Type   | Required | Notes                                                        |
| --------- | --------------------- | ------ | -------- | ------------------------------------------------------------ |
| Client_ID | Application Client ID | String | Required | Client ID of the third party application required for authentication |
| Client_Secret | Application Client Secret | String | Required | Client Secret of the third party application required for authentication |
| Token | Access token or the refresh token | String | Required | Access token or refresh token returned from the token endpoint |

# Sample Request
 ``` 
 POST /oauth/v2/introspectToken
 
 ```





