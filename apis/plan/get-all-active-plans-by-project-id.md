# Get All Active Plans by Project ID

The endpoint retrieves all active test plans associated with a specific project identified by its ID. The authenticated user must belong to a company that is authorized to access the project. The response includes a list of active test plans in the form of `PlanDTO` objects.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/plans/active`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter   | Type   | Required | Description                                               |
| ----------- | ------ | -------- | --------------------------------------------------------- |
| `projectId` | `Long` | Yes      | The ID of the project for which to retrieve active plans. |

***

### Response Body

Upon a successful request, the API returns a list of active test plans in JSON format.

```json
[
  {
    "id": 376,
    "plan_name": "plan1",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 8,
    "scenarios": [],
    "period": {
      "period_type": "MANUAL",
      "days_of_week": "2,3,4,5,6,7,1",
      "repeat_period": 60
    },
    "alerts": [],
    "alerts_enabled": false,
    "failed_test_retry_count": 0
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

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                             |
| `403`     | `Forbidden`             | The user does not have permission to access plans for the specified project. |
| `404`     | `Project not found`     | The specified project was not found.                                         |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                             |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/plans/active" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
