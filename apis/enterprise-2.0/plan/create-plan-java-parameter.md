# Create Plan Java Parameter

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}/parameter
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

#### Headers

| Header Name     | Required | Description                          |
| --------------- | -------- | ------------------------------------ |
| Authorization   | Yes      | Bearer token used for authentication |
| X-Company-Id    | Yes      | Your CompanyId                       |
| Accept-Language | No       | Your language(tr or en)              |
| content-type    | Yes      | application/json                     |

### Response Body

### Request Body

```
[
  {
    "name": "env",
    "value": "prod",
    "description": "Environment selection parameter",
    "type": "ENVIRONMENT_PARAMETER"
  }
]
```

### Response Body

```
{
    "data": [
        {
            "name": "env",
            "value": "prod",
            "description": "Environment selection parameter",
            "type": "ENVIRONMENT_PARAMETER"
        }
    ],
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

### Error Codes

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/plan/{planId}/parameter' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'X-Company-Id: <company_id>' \
--header 'content-type: application/json' \
--data '[
  {
    "name": "env",
    "value": "prod",
    "description": "Environment selection parameter",
    "type": "ENVIRONMENT_PARAMETER"
  }
]'
```
