# Login

The endpoint enables users to authenticate and acquire an access token. The access token is necessary to make authorized requests to secured endpoints in the system.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/oauth/token` _(Replace `<custom-env-url>` with the appropriate API base URL provided by your organization.)_
* **Method**: `POST`
* **Header**: Basic Authentication (`client_id` and `client_secret`) _(Please contact us to obtain these credentials.)_
* **Content-Type**: `application/x-www-form-urlencoded`

***

### Request Parameters

To obtain an access token, the following **form-data parameters** are required:

| Parameter    | Type     | Required | Description                                     |
| ------------ | -------- | -------- | ----------------------------------------------- |
| `grant_type` | `String` | Yes      | The grant type, typically `password`.           |
| `username`   | `String` | Yes      | The `username` of the customer.                 |
| `password`   | `String` | Yes      | The `password` of the customer.                 |
| `scope`      | `String` | No       | The scope of access for the token, e.g., `api`. |

***

### Response

Upon a successful request, the server returns a response containing the access token and additional token information. This token is required for subsequent API calls.

```json
{
  "access_token": "your-access-token",
  "token_type": "bearer",
  "refresh_token": "your-refresh-token",
  "expires_in": 3600,
  "scope": "api",
  "jti": "unique-token-identifier"
}
```

#### Response Fields

| Field           | Type     | Description                                        |
| --------------- | -------- | -------------------------------------------------- |
| `access_token`  | `String` | Token for authenticating API requests.             |
| `token_type`    | `String` | Type of token, usually `bearer`.                   |
| `refresh_token` | `String` | Token to refresh the access token upon expiration. |
| `expires_in`    | `Number` | Time in seconds until the access token expires.    |
| `scope`         | `String` | The scope of the token's granted access.           |
| `jti`           | `String` | Unique identifier for the token.                   |

***

### Error Codes

The following error codes may be encountered during token generation:

| HTTP Code | Error Message           | Description                                         |
| --------- | ----------------------- | --------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request is invalid or missing parameters.       |
| `401`     | `INVALID_CLIENT`        | The `username` or `password` is incorrect.          |
| `403`     | `ACCESS_DENIED`         | Authentication failed due to incorrect credentials. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server.         |

***

### Example Request

Below is an example of a `curl` command to obtain an access token:

```bash
curl --location '<custom-env-url>/Testinium.RestApi/oauth/token' \
--header 'Authorization: Basic <Base64(client_id:client_secret)>' \
--header 'Accept: application/json' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'password= customer-password' \
--data-urlencode 'username= customer-username' \
--data-urlencode 'scope=api'
```
