# Get Alert By Plan Id

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": [
        {
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
        {
            "id": null,
            "planId": 766,
            "alertType": "EMAIL",
            "target": "demo@testinium.com",
            "targetId": null,
            "targetType": null,
            "alertSendingStatus": "End of the Each Execution",
            "alertSendingStatusResult": [
                {
                    "id": 171,
                    "name": "Test Successful"
                }
            ],
            "language": null,
            "targetTimeZone": null,
            "enabled": true,
            "unsubscribeLinkEliminated": false
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
curl --location --request GET '<your-gateway-url>/alert/plan/{planId}' \
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
