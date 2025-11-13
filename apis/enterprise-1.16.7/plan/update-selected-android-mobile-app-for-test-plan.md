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
    "id": 261,
    "project_id": 580,
    "company_id": 1,
    "plan_name": "Android",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 36,
    "scenarios": [
        3076,
        3077,
        3078,
        3079,
        3080,
        3056,
        3087,
        3086,
        3100
    ],
    "period": {
        "period_type": "MANUAL",
        "days_of_week": "2,3,4,5,6,7,1",
        "repeat_period": 60
    },
    "alerts": [],
    "alerts_enabled": false,
    "failed_test_retry_count": 3,
    "screen_shot_type": "YES",
    "video_enabled": false,
    "environments": [
        {
            "id": 9
        },
        {
            "id": 13
        }
    ],
    "clear_app_data": false,
    "fetch_app_files": [],
    "selected_android_mobile_app": {
        "id": 51,
        "mobile_app_name": "3.2.39__130_-83f575df-b7266d12-2359313112333632572.apk",
        "mobile_app_hash": "177f1b975b8f99e8006dd8bf88686f6e",
        "operating_system": "ANDROID",
        "mobile_app_metadata": "{\"packageName\":\"com.gratis.android\",\"label\":\"Gratis\",\"icon\":\"res/d2.webp\",\"versionName\":\"3.2.39\",\"versionCode\":130,\"minSdkVersion\":\"24\",\"targetSdkVersion\":\"34\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
        "created_at": "2024-10-18 09:34:30"
    },
    "selected_ios_mobile_app": {
        "id": 53,
        "mobile_app_name": "Gratis-b250541b__2_-8988176051238453961.ipa",
        "mobile_app_hash": "556372e35d7f2b6fa4b7ceb4c0af8b58",
        "operating_system": "IOS",
        "mobile_app_metadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.2.12\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\"}",
        "created_at": "2024-10-18 09:34:30"
    }
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
curl --location --request PUT '<custom-env-url>/Testinium.RestApi/api/plans/{id}/setAndroidMobileApp/{mobileAppId}' \
--header 'Accept: application/json' \
--header 'Authorization: Bearer <token>'

```
