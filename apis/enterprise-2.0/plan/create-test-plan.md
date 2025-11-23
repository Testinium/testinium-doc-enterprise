# Create Test Plan

The endpoint creates a new test plan for a specific project. The user must provide project details and plan specifications in the request body. The API validates the input and returns the created plan as a ProjectDTO object.



Note: After executing the Create Plan API, the Create Period API must be called as the next step

***

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
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

| Parameter             | Type      |
| --------------------- | --------- |
| planName              | `string`  |
| groupPlan             | `boolean` |
| description           | `string`  |
| enabled               | `boolean` |
| deleted               | `boolean` |
| planParallelTestLimit | `integer` |
| projectId             | `integer` |
| userId                | `integer` |
| companyId             | `integer` |
| failedTestRetryCount  | `integer` |
| maxExecutionTime      | `integer` |
| testRunType           | `string`  |
| screenShotType        | `string`  |
| videoEnabled          | `boolean` |
| uninstallApp          | `boolean` |
| clearAppData          | `boolean` |
| androidMobileApp      | `integer` |
| iosMobileApp          | `integer` |
| isSigned              | `boolean` |
| alertsEnabled         | `boolean` |

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
            "mobileAppName": "3.2.15_1720_-82c49ca8-c5b6a33c-7453723443815496548.ipa",
            "mobileAppHash": "df6abb29c3bee1fa9b4b90a0299b1b36",
            "mobileAppMetadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.2.15\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\",\"bundleIdentifier\":\"com.pharos.Gratis\",\"teamName\":\"Gratis ic ve Dis Ticaret Anonim Sirketi\"}",
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
                "bundleName": "Gratis",
                "bundleDisplayName": "Gratis",
                "bundleVersion": "3.2.15",
                "bundleMinOsVersion": "12.0",
                "bundleDevelopmentRegion": "tr",
                "bundleExecutable": "Gratis",
                "bundleIconFiles": "",
                "bundleInfoDictVersion": "6.0",
                "bundlePackageType": "APPL",
                "bundleMainStoryBoardFile": "Main",
                "bundleIdentifier": "com.pharos.Gratis",
                "teamName": "Gratis ic ve Dis Ticaret Anonim Sirketi"
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

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                         |
| --------- | ----------------------- | ------------------------------------------------------------------- |
| `400`     | `Invalid input data`    | There are missing or incorrect details in the request body.         |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                    |
| `403`     | `Forbidden`             | The user does not have permission to create a plan for the project. |
| `404`     | `Project not found`     | The specified project was not found.                                |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                    |

***

### Example Request

```bash
curl --location 'http://localhost:8089/plan' \
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
