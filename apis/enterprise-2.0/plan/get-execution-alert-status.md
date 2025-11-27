# Get Execution Alert Status

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/status/type/execution
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": [
        {
            "name": "EXECUTION_STARTED",
            "description": "Beginning of the Each Execution",
            "multiSelect": false
        },
        {
            "name": "EXECUTION_COMPLETED",
            "description": "End of the Each Execution",
            "multiSelect": true
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
curl --location '<your-gateway-url>/alert/status/type/execution' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
