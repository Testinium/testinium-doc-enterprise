# Get Plan By ID (Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}
* **Method**: `POST`
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

| Field                    | Type      |
| ------------------------ | --------- |
| `id`                     | `integer` |
| `plan_name`              | `string`  |
| `groupPlan`              | `boolean` |
| `description`            | `string`  |
| `enabled`                | `boolean` |
| deleted                  | boolean   |
| planParallelTestLimit    | `integer` |
| `periodId`               | `integer` |
| `project_id`             | `integer` |
| projectName              | String    |
| projectTestFramework     | String    |
| userId                   | `integer` |
| `company_id`             | `integer` |
| failedTestRetryCount     | `integer` |
| testRunType              | String    |
| screenShotType           | String    |
| videoEnabled             | boolean   |
| uninstallApp             | boolean   |
| clearAppData             | boolean   |
| selectedIosMobileApp     | Object    |
| selectedAndroidMobileApp | Object    |
| testFileType             | String    |
| testRunnerTool           | String    |
| gridType                 | String    |

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location --globoff '<your-gateway-url>/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
