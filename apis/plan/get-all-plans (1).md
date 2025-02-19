# Get All Plans By Project Name or ID

The endpoint retrieves all test plans associated with a specific project. The user must provide the project identifier in the path. It returns a list of test plans in the form of `PlanDTO` objects.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter         | Type     | Required | Description                                                |
| ----------------- | -------- | -------- | ---------------------------------------------------------- |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project for which to retrieve plans. |

***

### Response Body

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
    "scenarios": [3076, 3077, 3078, 3079, 3080, 3056, 3087, 3086, 3100],
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
      { "id": 9 },
      { "id": 13 }
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
  },
  {
    "id": 262,
    "project_id": 580,
    "company_id": 1,
    "plan_name": "IOS",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 36,
    "scenarios": [],
    "period": {
      "period_type": "MANUAL",
      "days_of_week": "2,3,4,5,6,7,1",
      "repeat_period": 60
    },
    "alerts": [],
    "alerts_enabled": false,
    "failed_test_retry_count": 0,
    "screen_shot_type": "YES",
    "video_enabled": false,
    "environments": [
      { "id": 11 }
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
  },
  {
    "id": 263,
    "project_id": 580,
    "company_id": 1,
    "plan_name": "AndroidIOS",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 36,
    "scenarios": [],
    "period": {
      "period_type": "MANUAL",
      "days_of_week": "2,3,4,5,6,7,1",
      "repeat_period": 60
    },
    "alerts": [],
    "alerts_enabled": false,
    "failed_test_retry_count": 0,
    "screen_shot_type": "YES",
    "video_enabled": false,
    "environments": [
      { "id": 13 },
      { "id": 11 }
    ],
    "clear_app_data": false,
    "fetch_app_files": [],
    "selected_android_mobile_app": {
      "id": 52,
      "mobile_app_name": "FLO_v4.1.35_apkpure.com-8805574610750679613.apk",
      "mobile_app_hash": "..."
    }
  }
]

```

| Field                      | Type      | Description                                     |
| -------------------------- | --------- | ----------------------------------------------- |
| `id`                       | `Long`    | The unique ID of the test plan.                 |
| `plan_name`                | `String`  | The name of the test plan.                      |
| `group_plan`               | `Boolean` | Indicates if the plan is a group plan.          |
| `description`              | `String`  | The description of the test plan.               |
| `enabled`                  | `Boolean` | Whether the test plan is active or not.         |
| `plan_parallel_test_limit` | `Integer` | The maximum number of parallel tests allowed.   |
| `scenarios`                | `Array`   | List of scenarios associated with the plan.     |
| `period`                   | `Object`  | Information about the test period.              |
| `period_type`              | `String`  | The type of period (e.g., MANUAL).              |
| `days_of_week`             | `String`  | Days of the week when the plan can run.         |
| `repeat_period`            | `Integer` | The repeat period in minutes.                   |
| `alerts`                   | `Array`   | List of alerts configured for the plan.         |
| `alerts_enabled`           | `Boolean` | Whether alerts are enabled for the plan.        |
| `failed_test_retry_count`  | `Integer` | The number of retries allowed for failed tests. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                              |
| --------- | ----------------------- | -------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.         |
| `403`     | `Forbidden`             | The user does not have permission to access the project. |
| `404`     | `Project not found`     | The specified project was not found.                     |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.         |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans' \
--header 'Authorization: Bearer <your_access_token>' 
```
