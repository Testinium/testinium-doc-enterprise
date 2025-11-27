# Get Plan By ID (Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

### Path Variables

| Parameter | Type   | Required | Description              |
| --------- | ------ | -------- | ------------------------ |
| planId    | `Long` | Yes      | The ID of the test plan. |

### Response Body

```
{
    "data": {
        "id": 316,
        "planName": "Demo",
        "groupPlan": false,
        "description": "",
        "enabled": true,
        "deleted": false,
        "planParallelTestLimit": 50,
        "periodId": 318,
        "projectId": 913,
        "projectName": "Demo",
        "projectTestFramework": "APPIUM2",
        "userId": 13,
        "companyId": 2,
        "failedTestRetryCount": 0,
        "testRunType": "CROSS",
        "screenShotType": "YES",
        "videoEnabled": true,
        "uninstallApp": false,
        "clearAppData": false,
        "selectedIosMobileApp": {
            "id": 84,
            "mobileAppName": "Demo.ipa",
            "mobileAppHash": "Demo",
            "mobileAppMetadata": "{\"Demo"}",
            "operatingSystem": "IOS",
            "createdAt": "2025-03-04T13:00:02.784+00:00",
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
                "bundleName": "Demo",
                "bundleDisplayName": "Demo",
                "bundleVersion": "3.2.15",
                "bundleMinOsVersion": "12.0",
                "bundleDevelopmentRegion": "tr",
                "bundleExecutable": "Demo",
                "bundleIconFiles": "",
                "bundleInfoDictVersion": "6.0",
                "bundlePackageType": "APPL",
                "bundleMainStoryBoardFile": "Main",
                "bundleIdentifier": "Demo",
                "teamName": null
            }
        },
        "testFileType": "APPIUM_GAUGE",
        "testRunnerTool": "MAVEN",
        "gridType": "TESTINIUM_ENTERPRISE"
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| Field                    | Type      | Description                                                                |
| ------------------------ | --------- | -------------------------------------------------------------------------- |
| `id`                     | `long`    | Unique identifier of the test plan.                                        |
| `plan_name`              | `string`  | The display name of the test plan.                                         |
| `groupPlan`              | `boolean` | Indicates whether the plan is a grouped plan.                              |
| `description`            | `string`  | A detailed explanation or note describing the plan.                        |
| `enabled`                | `boolean` | Specifies whether the plan is active and can be executed.                  |
| deleted                  | boolean   | Marks the plan as deleted without permanently removing it.                 |
| planParallelTestLimit    | `integer` | Maximum number of tests allowed to run in parallel for this plan.          |
| `periodId`               | `integer` | Identifier of the associated period configuration for scheduled execution. |
| `project_id`             | `integer` | ID of the project to which this plan belongs.                              |
| projectName              | String    | Name of the associated project.                                            |
| projectTestFramework     | String    | The test framework used by the project                                     |
| userId                   | `integer` | ID of the user who created or updated the plan.                            |
| `company_id`             | `integer` | ID of the company owning this plan.                                        |
| failedTestRetryCount     | `integer` | Number of times failed tests will be retried automatically.                |
| testRunType              | String    | Defines how tests are executed                                             |
| screenShotType           | String    | Determines screenshot capturing behavior during test execution.            |
| videoEnabled             | boolean   | Indicates whether video recording is enabled for test runs.                |
| uninstallApp             | boolean   | Whether the mobile application should be uninstalled before execution.     |
| clearAppData             | boolean   | Whether app data should be cleared before test execution.                  |
| selectedIosMobileApp     | Object    | The selected iOS application associated with the plan.                     |
| selectedAndroidMobileApp | Object    | The selected Android application associated with the plan.                 |
| testFileType             | String    | Type of test files used in this plan                                       |
| testRunnerTool           | String    | The automation tool used to run tests                                      |
| gridType                 | String    | Execution type within the grid environment                                 |

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
