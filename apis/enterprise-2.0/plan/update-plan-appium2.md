# Update Plan(Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "planName": "Sample Test Plan",
  "groupPlan": false,
  "description": "This is a sample test plan for demonstration purposes.",
  "type": "APPIUM",
  "enabled": true,
  "deleted": false,
  "planParallelTestLimit": 5,
  "period": null,
  "projectId": 913,
  "userId": 1,
  "companyId": 1,
  "failedTestRetryCount": 2,
  "maxExecutionTime": 3600,
  "testRunType": "CROSS",
  "screenShotType": "YES",
  "videoEnabled": true,
  "uninstallApp": false,
  "clearAppData": false,
  "androidMobileApp": 134,
  "iosMobileApp": null,
  "isSigned": true,
  "alertsEnabled": true
}
```

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location --request PUT '<your-gateway-url>/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data '{
  "planName": "Sample Test Plan",
  "groupPlan": false,
  "description": "This is a sample test plan for demonstration purposes.",
  "type": "APPIUM",
  "enabled": true,
  "deleted": false,
  "planParallelTestLimit": 5,
  "period": null,
  "projectId": 913,
  "userId": 1,
  "companyId": 1,
  "failedTestRetryCount": 2,
  "maxExecutionTime": 3600,
  "testRunType": "CROSS",
  "screenShotType": "YES",
  "videoEnabled": true,
  "uninstallApp": false,
  "clearAppData": false,
  "androidMobileApp": 134,
  "iosMobileApp": null,
  "isSigned": true,
  "alertsEnabled": true
}'
```
