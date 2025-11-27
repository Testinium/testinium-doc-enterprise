# Create Plan Java Parameter

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}/parameter
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

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
