# Update Selected Android Mobile App for Test Plan

The endpoint allows users to update the selected Android mobile app for a specific test plan. The user must provide the test plan ID and the mobile app ID to be set.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/setAndroidMobileApp/{mobileAppId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter     | Type   | Required | Description                                     |
| ------------- | ------ | -------- | ----------------------------------------------- |
| `id`          | `Long` | Yes      | The unique identifier of the test plan.         |
| `mobileAppId` | `Long` | Yes      | The unique identifier of the mobile app to set. |

***

### Response Body

Upon a successful request, the API returns the updated `PlanDTO` object representing the test plan with the selected Android mobile app.

```json

    {
        "id": 580,
        "project_name": "APPFile",
        "description": "",
        "enabled": true,
        "repository_path": "appfile",
        "test_framework": "APPIUM",
        "test_file_type": "APPIUM_GAUGE",
        "test_runner_tool": "MAVEN",
        "mobile_apps": [
            {
                "id": 54,
                "mobile_app_name": "pegasus-pilot-release-2.39.0.38__2_-ee15733f-2799725523214323595.apk",
                "mobile_app_hash": "57e487d42eaa459b1713df8c1dd691a8",
                "operating_system": "ANDROID",
                "mobile_app_metadata": "{\"packageName\":\"com.pozitron.pegasus.pilotRelease\",\"label\":\"PGS Pilot\",\"icon\":\"res/u3.png\",\"versionName\":\"2.39.0.38\",\"versionCode\":119,\"minSdkVersion\":\"23\",\"targetSdkVersion\":\"33\"}",
                "created_at": "2024-10-18 09:34:30"
            },
            {
                "id": 53,
                "mobile_app_name": "Gratis-b250541b__2_-8988176051238453961.ipa",
                "mobile_app_hash": "556372e35d7f2b6fa4b7ceb4c0af8b58",
                "operating_system": "IOS",
                "mobile_app_metadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.2.12\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\"}",
                "created_at": "2024-10-18 09:34:30"
            }
        ]
    }
```

| Field                      | Type        | Description                                        |
| -------------------------- | ----------- | -------------------------------------------------- |
| `id`                       | `Long`      | The unique identifier of the test plan.            |
| `name`                     | `String`    | The name of the test plan.                         |
| `selectedAndroidMobileApp` | `MobileApp` | The mobile app that is selected for the test plan. |

***

### Error Codes

| HTTP Code | Error Message                           | Description                                                          |
| --------- | --------------------------------------- | -------------------------------------------------------------------- |
| `404`     | `Mobile app not found`                  | The specified mobile app was not found.                              |
| `404`     | `Plan not found`                        | The specified test plan was not found.                               |
| `400`     | `Mobile app not Android`                | The specified mobile app is not an Android app.                      |
| `400`     | `Mobile app does not belong to project` | The specified mobile app does not belong to the test plan's project. |
| `500`     | `Internal Server Error`                 | An unexpected error occurred on the server side.                     |

***

### Example Request

```bash
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/plans/{id}/setAndroidMobileApp/{mobileAppId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json"
```
