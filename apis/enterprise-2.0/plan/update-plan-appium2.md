# Update Plan(Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}
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

| Parameter             | Type      | Description                                                         |
| --------------------- | --------- | ------------------------------------------------------------------- |
| planName              | `string`  | The name of the test plan displayed in the user interface.          |
| groupPlan             | `boolean` | Indicates whether the plan is a group plan.                         |
| description           | `string`  | A detailed explanation or note describing the test plan.            |
| enabled               | `boolean` | Determines whether the plan is active and can be executed.          |
| deleted               | `boolean` | Marks the plan as deleted without permanently removing it.          |
| planParallelTestLimit | `integer` | The maximum number of tests allowed to run in parallel.             |
| projectId             | `integer` | The ID of the project to which this plan belongs.                   |
| userId                | `integer` | The ID of the user who created or last updated the plan.            |
| companyId             | `integer` | The ID of the company associated with this plan.                    |
| failedTestRetryCount  | `integer` | Specifies how many times failed tests will be retried.              |
| maxExecutionTime      | `integer` | Maximum allowed execution time for this plan in seconds.            |
| testRunType           | `string`  | Determines how tests will run .                                     |
| screenShotType        | `string`  | The screenshot capture behavior (e.g., YES, NO, ON\_FAILURE).       |
| videoEnabled          | `boolean` | Indicates whether video recording will be enabled during execution. |
| uninstallApp          | `boolean` | Whether the app should be uninstalled before execution starts.      |
| clearAppData          | `boolean` | Whether the app’s data should be cleared before execution.          |
| androidMobileApp      | `integer` | The ID of the Android application used in this plan.                |
| iosMobileApp          | `integer` | The ID of the iOS application used in this plan.                    |
| isSigned              | `boolean` | Indicates whether the associated mobile application is signed.      |
| alertsEnabled         | `boolean` | Enables or disables alert notifications for this plan.              |

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

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
