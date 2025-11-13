# Get All Plans

The endpoint retrieves all test plans associated with the user's company. The response contains a list of test plans.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Response Body

Upon a successful request, the API returns a list of `PlanDTO` objects representing the test plans.

```json
[
    {
        "id": 1,
        "project_id": 1,
        "company_id": 1,
        "plan_name": "TestPlan(Selenium)",
        "group_plan": false,
        "description": "",
        "enabled": true,
        "plan_parallel_test_limit": 1,
        "scenarios": [],
        "period": {
            "period_type": "MANUAL",
            "start_date": 1506807000000,
            "end_date": 1509399000000,
            "once_date": 1428662940000,
            "days_of_week": "2,3,4,5,6",
            "repeat_period": 60
        },
        "alerts": [],
        "alerts_enabled": false,
        "failed_test_retry_count": 0,
        "screen_shot_type": "YES",
        "video_enabled": true,
        "environments": [
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            },
            {
                "id": 7
            }
        ],
        "performance_data_enabled": false,
        "resolutions": {
            "WIN8": "1024x768",
            "WIN10": "1024x768",
            "LINUX": "1440x900",
            "WIN8_1": "1024x768",
            "XP": "1024x768",
            "MAC": "1920x1080",
            "VISTA": "1024x768"
        }
    },
    {
        "id": 7,
        "project_id": 11,
        "company_id": 1,
        "plan_name": "Calisan Mobil Allianz Plan",
        "group_plan": false,
        "description": "",
        "enabled": true,
        "plan_parallel_test_limit": 5,
        "scenarios": [
            7
        ],
        "period": {
            "period_type": "MANUAL",
            "days_of_week": "2,3,4,5,6,7,1",
            "repeat_period": 60
        },
        "alerts": [],
        "alerts_enabled": false,
        "failed_test_retry_count": 0,
        "screen_shot_type": "YES",
        "video_enabled": true,
        "environments": [
            {
                "id": 34
            }
        ],
        "clear_app_data": false,
        "fetch_app_files": [],
        "selected_android_mobile_app": {
            "id": 60,
            "mobile_app_name": "oneapp-prep-release-4469200244660687888-5839120655280934206--5902101721559638469.apk",
            "mobile_app_hash": "93e1ee6391ec361479996d7ea96ac4ae",
            "operating_system": "ANDROID",
            "mobile_app_metadata":"{\"packageName\":\"com.accenture.oneapp.prep\",\"label\":\"Allianz\'ım PREP\",\"icon\":\"res/8X.png\",\"versionName\":\"6.11.0prep\",\"versionCode\":390,\"minSdkVersion\":\"21\",\"targetSdkVersion\":\"31\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
            "created_at": "2023-12-06 16:03:28"
        },
        "selected_ios_mobile_app": {
            "id": 57,
            "mobile_app_name": "ALoneapp-5170617211746898658-2770453221549930031.ipa",
            "mobile_app_hash": "11c6587d50d175d27409d2410b037138",
            "operating_system": "IOS",
            "mobile_app_metadata":"{\"bundleName\":\"oneapp\",\"bundleDisplayName\":\"Allianz\'ım PREP\",\"bundleVersion\":\"6.12.4\",\"bundleMinOsVersion\":\"11.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"oneapp\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"\"}",
            "created_at": "2023-11-06 18:15:06"
        }
    }
]       
```

| Field                      | Type      | Description                                                                      |
| -------------------------- | --------- | -------------------------------------------------------------------------------- |
| `id`                       | `integer` | The unique ID of the test plan.                                                  |
| `project_id`               | `integer` | The ID of the project associated with the test plan.                             |
| `company_id`               | `integer` | The ID of the user's company associated with the test plan.                      |
| `plan_name`                | `string`  | The name of the test plan.                                                       |
| `group_plan`               | `boolean` | Whether the plan is a group plan.                                                |
| `description`              | `string`  | A brief description of the test plan.                                            |
| `enabled`                  | `boolean` | Indicates if the plan is enabled.                                                |
| `plan_parallel_test_limit` | `integer` | The maximum number of parallel tests allowed for the plan.                       |
| `scenarios`                | `array`   | A list of scenario IDs associated with the plan.                                 |
| `period.period_type`       | `string`  | The type of period (e.g., MANUAL).                                               |
| `period.days_of_week`      | `string`  | Days of the week for the plan's schedule, represented as comma-separated values. |
| `period.repeat_period`     | `integer` | The repetition interval for the plan, in minutes.                                |
| `alerts`                   | `array`   | A list of alert configurations for the plan.                                     |
| `alerts_enabled`           | `boolean` | Indicates if alerts are enabled for the plan.                                    |
| `failed_test_retry_count`  | `integer` | The number of retries allowed for failed tests.                                  |
| `screen_shot_type`         | `string`  | The type of screenshot capturing (e.g., YES, NO).                                |
| `video_enabled`            | `boolean` | Indicates if video recording is enabled for the plan.                            |
| `environments`             | `array`   | A list of environment IDs associated with the plan.                              |
| `performance_data_enabled` | `boolean` | Indicates if performance data tracking is enabled.                               |
| `resolutions`              | `object`  | Key-value pairs of operating system resolutions.                                 |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/plans' \
--header 'Authorization: Bearer <your_access_token>' 
```
