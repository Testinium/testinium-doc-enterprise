# Get All Plans by User's Companies

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get All Plans by User's Companies

The endpoint retrieves all test plans associated with a specific project that belong to the companies that the authenticated user is associated with. The user must provide the project identifier in the path. It returns a list of test plans in the form of `PlanDTO` objects.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/plans/byUserCompanies`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter   | Type   | Required | Description                                        |
| ----------- | ------ | -------- | -------------------------------------------------- |
| `projectId` | `Long` | Yes      | The ID of the project for which to retrieve plans. |

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

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                             |
| `403`     | `Forbidden`             | The user does not have permission to access plans for the specified project. |
| `404`     | `Project not found`     | The specified project was not found.                                         |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                             |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/plans/byUserCompanies" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
