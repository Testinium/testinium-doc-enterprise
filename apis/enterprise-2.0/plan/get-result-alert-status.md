# Get Result Alert Status

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/status/type/result?executionStatusName=EXECUTION\_COMPLETED' \\
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": [
        "Test Successful",
        "Test Failed",
        "Test Unexecuted",
        "Test Stopped",
        "Test Error"
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
curl --location '<your-gateway-url>/alert/status/type/result?executionStatusName=EXECUTION_COMPLETED' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
