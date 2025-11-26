# Create Period(Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}/period
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body



Manual

```
{
  "periodType": "MANUAL",
  "startDate": null,
  "endDate": null,
  "onceDate": null,
  "daysOfWeek": null,
  "repeatPeriod": null,
  "scheduled": false
}
```

ONCE

```
{
  "periodType": "ONCE",
  "startDate": null,
  "endDate": null,
  "onceDate": "2025-01-10T09:30:00.000Z",
  "daysOfWeek": null,
  "repeatPeriod": null,
  "scheduled": true
}
```

REPETITIVE

```
{
  "periodType": "REPETITIVE",
  "startDate": "2025-01-01T00:00:00.000Z",
  "endDate": "2025-02-01T00:00:00.000Z",
  "onceDate": null,
  "daysOfWeek": null,
  "repeatPeriod": 1,
  "scheduled": true
}
```



### Example Response

```
{
    "data": {
        "id": 631,
        "periodType": "MANUAL",
        "startDate": null,
        "endDate": null,
        "onceDate": null,
        "daysOfWeek": null,
        "repeatPeriod": null
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/plan/{planId}/period' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data '{
  "periodType": "MANUAL",
  "startDate": null,
  "endDate": null,
  "onceDate": null,
  "daysOfWeek": null,
  "repeatPeriod": null,
  "scheduled": false
}'
```
