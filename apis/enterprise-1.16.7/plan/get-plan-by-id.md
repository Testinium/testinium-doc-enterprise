# Get Plan By ID

The endpoint retrieves a test plan based on the plan's name or ID. The test plan is returned as a `PlanDTO` object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{planNameOrId}`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`

***

### Path Variables

| Parameter      | Type     | Required | Description                      |
| -------------- | -------- | -------- | -------------------------------- |
| `planNameOrId` | `Object` | Yes      | The name or ID of the test plan. |

***

### Response Body

Upon a successful request, the API returns the test plan in JSON format.

```json
[
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
            "id": 54,
            "mobile_app_name": "pegasus-pilot-release-2.39.0.38__2_-ee15733f-2799725523214323595.apk",
            "mobile_app_hash": "57e487d42eaa459b1713df8c1dd691a8",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.pozitron.pegasus.pilotRelease\",\"label\":\"PGS Pilot\",\"icon\":\"res/u3.png\",\"versionName\":\"2.39.0.38\",\"versionCode\":119,\"minSdkVersion\":\"23\",\"targetSdkVersion\":\"33\"}",
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
]
```

| Field             | Type      | Description                                      |
| ----------------- | --------- | ------------------------------------------------ |
| `id`              | `integer` | The unique ID of the test plan.                  |
| `plan_name`       | `string`  | The name of the test plan.                       |
| `description`     | `string`  | A brief description of the test plan.            |
| `project_id`      | `integer` | The ID of the associated project.                |
| `company_id`      | `integer` | The ID of the associated company.                |
| `enabled`         | `boolean` | Whether the plan is enabled or not.              |
| `scenarios`       | `array`   | A list of scenario IDs associated with the plan. |
| `period`          | `object`  | The period configuration for the plan.           |
| `alerts`          | `array`   | A list of alerts associated with the plan.       |
| `video_enabled`   | `boolean` | Whether video recording is enabled for the plan. |
| `environments`    | `array`   | A list of environments related to the plan.      |
| `clear_app_data`  | `boolean` | Whether app data should be cleared.              |
| `fetch_app_files` | `array`   | A list of files to be fetched for the plan.      |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. User is not logged in.                |
| `403`     | `Forbidden`             | User does not have permission to access the specified plan. |
| `404`     | `Plan not found`        | The specified plan was not found.                           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.                 |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/plans/{planNameOrId}' \
--header 'Authorization: Bearer <your_access_token>'
```
