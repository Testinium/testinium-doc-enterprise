# Update Test Plan

The endpoint updates an existing test plan for a specific project. The user must provide the project and plan identifiers in the path, along with the updated plan specifications in the request body. The API validates the input and returns the updated plan as a ProjectDTO object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

<table><thead><tr><th width="205">Parameter</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>projectNameOrId</code></td><td><code>Object</code></td><td>Yes</td><td>The name or ID of the project containing the plan.</td></tr><tr><td><code>planNameOrId</code></td><td><code>Object</code></td><td>Yes</td><td>The name or ID of the plan to be updated.</td></tr></tbody></table>

***

### Request Body Table

The JSON format request data that needs to be sent for updating a test plan is as follows:

```json
    {
        "id": 13,
        "project_id": 15,
        "company_id": 1,
        "plan_name": "UpdatedPlan",
        "group_plan": false,
        "description": "",
        "enabled": true,
        "plan_parallel_test_limit": 1,
        "scenarios": [
            16
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
                "id": 15
            }
        ],
        "clear_app_data": false,
        "fetch_app_files": []
    }
```

| Parameter     | Type     | Required | Description                                                                            |
| ------------- | -------- | -------- | -------------------------------------------------------------------------------------- |
| `name`        | `string` | No       | The updated name of the test plan                                                      |
| `description` | `string` | No       | The updated description of the test plan                                               |
| `period`      | `object` | Yes      | The updated timing details for the test plan, including period type and repeat period. |

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

```json
{
    "id": 13,
    "project_id": 15,
    "company_id": 1,
    "plan_name": "UpdatedPlan",
    "group_plan": false,
    "description": "",
    "enabled": true,
    "plan_parallel_test_limit": 1,
    "scenarios": [
        16
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
            "id": 15
        }
    ],
    "clear_app_data": false,
    "fetch_app_files": []
}
```

| Field         | Type      | Description                                     |
| ------------- | --------- | ----------------------------------------------- |
| `id`          | `integer` | The unique ID of the updated test plan          |
| `name`        | `string`  | The updated name of the test plan               |
| `description` | `string`  | The updated description of the test plan        |
| `period`      | `object`  | The updated timing details of the test plan     |
| `projectId`   | `integer` | The ID of the project associated with the plan  |
| `user`        | `object`  | Information about the user who updated the plan |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                           |
| --------- | ----------------------- | --------------------------------------------------------------------- |
| `400`     | `Invalid input data`    | There are missing or incorrect details in the request body.           |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                      |
| `403`     | `Forbidden`             | The user does not have permission to update the plan for the project. |
| `404`     | `Plan not found`        | The specified plan was not found.                                     |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                      |

***

### Example Request

```bash
curl --location --request PUT '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <your_access_token>' \
--data '{
        "id": 13,
        "project_id": 15,
        "company_id": 1,
        "plan_name": "UpdatedPlan",
        "group_plan": false,
        "description": "",
        "enabled": true,
        "plan_parallel_test_limit": 1,
        "scenarios": [
            16
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
                "id": 15
            }
        ],
        "clear_app_data": false,
        "fetch_app_files": []
    }'
```
