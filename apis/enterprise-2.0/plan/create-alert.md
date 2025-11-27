# Create Alert

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/plan/{planId}
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "alertType": "EMAIL",
  "alertSendingStatus": "End of Each Execution",
  "target": "demo@testinium.com",
  "alertSendingStatusResults": [
    "Test Successful",
    "Test Failed",
    "Test Unexecuted",
    "Test Stopped",
    "Test Error"
  ],
  "targetId": null,
  "targetType": null,
  "language": null,
  "targetTimeZone": null
}
```

```
{
  "alertType": "EMAIL",
  "alertSendingStatus": "Beginning of the Each Execution",
  "target": "demo@testinium.com",
  "alertSendingStatusResults": [],
  "targetId": null,
  "targetType": null,
  "language": null,
  "targetTimeZone": null
}
```

### Response Body

```
{
    "data": {
        "id": 173,
        "planId": 766,
        "alertType": "EMAIL",
        "target": "demo@testinium.com",
        "targetId": null,
        "targetType": null,
        "alertSendingStatus": "Beginning of the Each Execution",
        "alertSendingStatusResult": null,
        "language": null,
        "targetTimeZone": null,
        "enabled": true,
        "unsubscribeLinkEliminated": false
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/alert/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data-raw '{
  "alertType": "EMAIL",
  "alertSendingStatus": "Beginning of the Each Execution",
  "target": "furkan.kartal@testinium.com",
  "alertSendingStatusResults": [],
  "targetId": null,
  "targetType": null,
  "language": null,
  "targetTimeZone": null
}'
```
