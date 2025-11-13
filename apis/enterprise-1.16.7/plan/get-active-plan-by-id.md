# Get Active Plan By ID

The endpoint retrieves an active test plan based on its ID. The response will return the plan as a `PlanDTO` object if the user has permission to access it.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{planId}/active`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`

***

### Path Variables

| Parameter | Type   | Required | Description              |
| --------- | ------ | -------- | ------------------------ |
| `planId`  | `Long` | Yes      | The ID of the test plan. |

***

### Response Body

Upon a successful request, the API returns the active test plan in JSON format.

```json
{
    "id": 77,
    "project_id": 66,
    "company_id": 1,
    "plan_name": "wakeup",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 8,
    "scenarios": [
        666
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
    "video_enabled": false,
    "environments": [
        {
            "id": 21
        }
    ],
    "clear_app_data": false,
    "fetch_app_files": [],
    "selected_android_mobile_app": {
        "id": 83,
        "mobile_app_name": "3.2.16__106_-4a968996-4595859751696432436.apk",
        "mobile_app_hash": "b4bf52f6eb3bc531f19de9537792cfdf",
        "operating_system": "ANDROID",
        "mobile_app_metadata": "{\"packageName\":\"com.gratis.android\",\"label\":\"Gratis\",\"icon\":\"res/mipmap-mdpi-v4/ic_launcher.webp\",\"versionName\":\"3.2.16\",\"versionCode\":106,\"minSdkVersion\":\"24\",\"targetSdkVersion\":\"34\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
        "created_at": "2024-08-15 08:55:22"
    },
    "selected_ios_mobile_app": {
        "id": 82,
        "mobile_app_name": "Gratis-2a14af4e-1391709825629909183.ipa",
        "mobile_app_hash": "5e14f1af8f3053dbf6a4d97a63422617",
        "operating_system": "IOS",
        "mobile_app_metadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.2.11\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\"}",
        "created_at": "2024-08-08 08:24:17"
    }
}
```

| Field                      | Type      | Description                                              |
| -------------------------- | --------- | -------------------------------------------------------- |
| `id`                       | `integer` | The unique ID of the test plan.                          |
| `plan_name`                | `string`  | The name of the test plan.                               |
| `description`              | `string`  | A brief description of the test plan.                    |
| `project_id`               | `integer` | The ID of the associated project.                        |
| `company_id`               | `integer` | The ID of the company associated with the test plan.     |
| `group_plan`               | `boolean` | Indicates if the test plan is a group plan.              |
| `enabled`                  | `boolean` | Whether the test plan is enabled.                        |
| `plan_parallel_test_limit` | `integer` | The maximum limit of parallel tests allowed in the plan. |
| `scenarios`                | `array`   | List of scenario IDs associated with the plan.           |
| `period`                   | `object`  | The schedule and recurrence details of the plan.         |
| `alerts`                   | `array`   | List of alert details.                                   |
| `alerts_enabled`           | `boolean` | Indicates if alerts are enabled for this plan.           |
| `video_enabled`            | `boolean` | Whether video recording is enabled for the plan.         |
| `environments`             | `array`   | List of environment IDs associated with the plan.        |
| `clear_app_data`           | `boolean` | Whether to clear app data for the test.                  |
| `fetch_app_files`          | `array`   | List of app files to be fetched for the test.            |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. User is not logged in.                |
| `403`     | `Forbidden`             | User does not have permission to access the specified plan. |
| `404`     | `Plan not found`        | The specified active plan was not found.                    |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.                 |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/plans/{planId}/active' \
--header 'Authorization: Bearer <your_access_token>'
```
