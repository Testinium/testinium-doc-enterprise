# Get Active Plan By ID

The endpoint retrieves an active test plan based on its ID. The response will return the plan as a `PlanDTO` object if the user has permission to access it.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{planId}/active`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

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
    "id": 24,
    "project_id": 17,
    "company_id": 11,
    "plan_name": "plan1",
    "group_plan": false,
    "description": "plan1",
    "enabled": true,
    "plan_parallel_test_limit": 0,
    "scenarios": [
        104
    ],
    "period": {
        "period_type": "ONCE",
        "once_date": 1415824200000,
        "days_of_week": "",
        "repeat_period": 60
    },
    "alerts": [],
    "alerts_enabled": true,
    "video_enabled": true,
    "environments": [
        {
            "id": 74
        }
    ],
    "clear_app_data": false,
    "fetch_app_files": []
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
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{planId}/active" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
