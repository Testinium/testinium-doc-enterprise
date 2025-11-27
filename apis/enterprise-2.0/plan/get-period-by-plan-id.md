# Get Period By Plan Id

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/period/{planId}
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": {
        "id": 628,
        "periodType": "MANUAL",
        "startDate": null,
        "endDate": null,
        "onceDate": null,
        "daysOfWeek": "2,3,4,5,6,7,1",
        "repeatPeriod": 60
    },
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
curl --location '<your-gateway-url>/plan/period/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
