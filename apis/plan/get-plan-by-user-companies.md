# Get Plan By User Companies

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Plan By User Companies

The endpoint retrieves all test plans associated with the user's company. The response contains a list of test plans.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Response Body

Upon a successful request, the API returns a list of `PlanDTO` objects representing the test plans.

{\`\[ { "id": 163, "project\_id": 3, "company\_id": 1, "plan\_name": "planCreation", "group\_plan": false, "description": "planCreation desc", "enabled": true, "plan\_parallel\_test\_limit": 8, "scenarios": \[887], "period": { "period\_type": "MANUAL", "days\_of\_week": "2,3,4,5,6,7,1", "repeat\_period": 60 }, "alerts": \[], "alerts\_enabled": false, "failed\_test\_retry\_count": 0, "screen\_shot\_type": "YES", "video\_enabled": false, "environments": \[{"id": 189}], "performance\_data\_enabled": false, "resolutions": { "WIN8\_1": "1024x768", "LINUX": "1024x768", "MAC": "1024x768", "XP": "1024x768", "WIN8": "1024x768", "VISTA": "1024x768", "WIN10": "1024x768" } }, { "id": 59, "project\_id": 61, "company\_id": 1, "plan\_name": "Multi-Single-Regression\_Testleri", "group\_plan": true, "description": "Multi/Regression - OneToOne Single - Settings", "enabled": true, "plan\_parallel\_test\_limit": 2, "scenarios": \[388], "period": { "period\_type": "MANUAL", "days\_of\_week": "2,3,4,5,6,7,1", "repeat\_period": 60 }, "alerts": \[], "alerts\_enabled": true, "video\_enabled": false, "environments": \[{"id": 249}, {"id": 233}], "clear\_app\_data": false, "fetch\_app\_files": \[] } ]\`}

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
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
