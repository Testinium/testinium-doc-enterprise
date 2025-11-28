# Create Test Plan(Appium2)

The endpoint creates a new test plan for a specific project. The user must provide project details and plan specifications in the request body. The API validates the input and returns the created plan as a ProjectDTO object.



Note: After the plan is created, the Create Period, Create Plan Scenarios, and Create Plan Environment APIs must be executed to ensure the workflow runs correctly.

***

### Endpoint Information

* **URL**: \<your-gateway-url>/plan
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body Table

The JSON format request data that needs to be sent for creating a test plan is as follows:

```json
{
  "planName": "Sample Test Plan",
  "groupPlan": false,
  "description": "This is a sample test plan for demonstration purposes.",
  "type": "APPIUM",
  "enabled": true,
  "deleted": false,
  "planParallelTestLimit": 5,
  "projectId": 709,
  "userId": 1,
  "companyId": 1,
  "failedTestRetryCount": 2,
  "maxExecutionTime": 3600,
  "testRunType": "CROSS",
  "screenShotType": "YES",
  "videoEnabled": true,
  "uninstallApp": false,
  "clearAppData": false,
  "androidMobileApp": null,
  "iosMobileApp": 118,
  "isSigned": true,
  "alertsEnabled": false
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

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

```json
{
    "data": {
        "id": 766,
        "planName": "Sample Test Plan",
        "groupPlan": false,
        "description": "This is a sample test plan for demonstration purposes.",
        "enabled": true,
        "deleted": false,
        "planParallelTestLimit": 5,
        "projectId": 709,
        "projectName": "Appium2GaugeCalisan",
        "projectTestFramework": "APPIUM2",
        "userId": 1,
        "companyId": 1,
        "failedTestRetryCount": 2,
        "maxExecutionTime": 3600,
        "testRunType": "CROSS",
        "screenShotType": "YES",
        "videoEnabled": false,
        "uninstallApp": false,
        "clearAppData": false,
        "selectedIosMobileApp": {
            "id": 118,
            "mobileAppName": "demo",
            "mobileAppHash": "demo",
            "mobileAppMetadata": "demo",
            "operatingSystem": "IOS",
            "createdAt": "2025-04-07T04:58:11.588+00:00",
            "apkMetaData": {
                "packageName": null,
                "activityName": null,
                "label": null,
                "icon": null,
                "versionName": null,
                "versionCode": null,
                "installLocation": null,
                "minSdkAndroidVersion": null,
                "minSdkVersion": null,
                "targetSdkVersion": null,
                "maxSdkVersion": null,
                "glEsVersion": null
            },
            "iosMetaData": {
                "bundleName": "demo",
                "bundleDisplayName": "demo",
                "bundleVersion": "3.2.15",
                "bundleMinOsVersion": "12.0",
                "bundleDevelopmentRegion": "tr",
                "bundleExecutable": "demo",
                "bundleIconFiles": "",
                "bundleInfoDictVersion": "6.0",
                "bundlePackageType": "APPL",
                "bundleMainStoryBoardFile": "Main",
                "bundleIdentifier": "demos",
                "teamName": "demo"
            }
        },
        "isSigned": true,
        "testFileType": "APPIUM_GAUGE",
        "testRunnerTool": "MAVEN",
        "testDispatchMethodType": "ONE_BY_ONE",
        "alertsEnabled": false
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

***

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

###

Application Error Codes

| Code    | Error Message                         |
| ------- | ------------------------------------- |
| `10000` | {filed} with id {projectId} not found |
| `10009` | `Mobile App with {id} not found!`     |
| `10010` | `{field} must not be null`            |
| `10011` | `Plan name {0} already exists!`       |

***

### Example Request

```bash
curl --location '<your-gateway-url>/plan' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--header 'Cookie: JSESSIONID=0D9219B3E88D8FE8513FF21049407F10' \
--data '{
  "planName": "Sample Test Plan",
  "groupPlan": false,
  "description": "This is a sample test plan for demonstration purposes.",
  "type": "APPIUM",
  "enabled": true,
  "deleted": false,
  "planParallelTestLimit": 5,
  "projectId": 709,
  "userId": 1,
  "companyId": 1,
  "failedTestRetryCount": 2,
  "maxExecutionTime": 3600,
  "testRunType": "CROSS",
  "screenShotType": "YES",
  "videoEnabled": true,
  "uninstallApp": false,
  "clearAppData": false,
  "androidMobileApp": null,
  "iosMobileApp": 118,
  "isSigned": true,
  "alertsEnabled": false
}
'
```
