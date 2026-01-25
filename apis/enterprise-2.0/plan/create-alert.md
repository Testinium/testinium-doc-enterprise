# Create Alert

### Endpoint Information

* **URL**: \<your-gateway-url>/alert/plan/{planId}
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

| Parameter                 | Type     | Description                                                                  |
| ------------------------- | -------- | ---------------------------------------------------------------------------- |
| alertType                 | `String` | Type of alert to send                                                        |
| alertSendingStatus        | `String` | Defines when the alert will be triggered                                     |
| target                    | `String` | Recipient of the alert.                                                      |
| alertSendingStatusResults | `Array`  | List of test result statuses for which alerts should be sent                 |
| targetId                  | `Long`   | Optional ID referencing a predefined alert target in the system.             |
| targetType                | String   | Optional target type                                                         |
| language                  | String   | Language code for the alert message content (e.g., "en", "tr").              |
| targetTimeZone            | String   | Time zone for scheduling or timestamp adjustments (e.g., "Europe/Istanbul"). |

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

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/alert/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'X-Company-Id: <company_id>' \
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
