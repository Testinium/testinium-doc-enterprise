# Delete Alert By Id

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/{alertId}
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": null,
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
curl --location --request DELETE '<your-gateway-url>/alert/{alertId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
