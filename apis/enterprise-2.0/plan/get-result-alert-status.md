# Get Result Alert Status

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/status/type/result?executionStatusName=EXECUTION\_COMPLETED' \\
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
curl --location '<your-gateway-url>/alert/status/type/result?executionStatusName=EXECUTION_COMPLETED' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'X-Company-Id: <company_id>' \
--header 'X-Company-Id: <company_id>' \
--header 'content-type: application/json'
```
