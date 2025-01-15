# Get Plan By Project And NameOrId

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Plan By Project And NameOrId

The endpoint retrieves a test plan associated with a specific project based on the project's name or ID, and the plan's name or ID. The test plan is returned as a `PlanDTO` object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                      |
| ----------------- | -------- | -------- | -------------------------------- |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project.   |
| `planNameOrId`    | `Object` | Yes      | The name or ID of the test plan. |

***

### Response Body

Upon a successful request, the API returns a list of active test plans in JSON format.

{\`\[ { "id": 376, "plan\_name": "plan1", "group\_plan": false, "description": "", "enabled": true, "plan\_parallel\_test\_limit": 8, "scenarios": \[], "period": { "period\_type": "MANUAL", "days\_of\_week": "2,3,4,5,6,7,1", "repeat\_period": 60 }, "alerts": \[], "alerts\_enabled": false, "failed\_test\_retry\_count": 0 } ]\`}

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

| HTTP Code | Error Message           | Description                                           |
| --------- | ----------------------- | ----------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.      |
| `403`     | `Forbidden`             | The user does not have permission to access the plan. |
| `404`     | `Plan not found`        | The specified plan was not found.                     |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.      |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```