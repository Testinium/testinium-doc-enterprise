# Delete Alert By Id

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
* **Method**: `POST`
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

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location --request DELETE '<your-gateway-url>/alert/{alertId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
