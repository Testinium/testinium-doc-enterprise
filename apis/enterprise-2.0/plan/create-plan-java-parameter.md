# Create Plan Java Parameter

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
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

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

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
