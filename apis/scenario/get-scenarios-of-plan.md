# Get Scenarios Of Plan

The endpoint returns the scenarios belonging to a specific plan. It provides a list of relevant scenarios based on the project and plan information obtained from the user.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}/scenarios`
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

Upon a successful request, the API returns a list of scenarios for the specified project.

```json
[
  {
    "id": 2353,
    "scenario_name": "scenario1",
    "description": "",
    "expected_result": "",
    "enabled": true,
    "execute_mode": "AUTOMATED"
  },
  {
    "id": 2354,
    "scenario_name": "@regression",
    "description": "",
    "expected_result": "",
    "enabled": true,
    "execute_mode": "AUTOMATED",
    "source_file": "denemeSc2.feature"
  },
  {
    "id": 2355,
    "scenario_name": "@smoke",
    "description": "",
    "expected_result": "",
    "enabled": true,
    "execute_mode": "AUTOMATED",
    "source_file": "denemeSc2.feature"
  }
]
```

| Field             | Type      | Description                                                 |
| ----------------- | --------- | ----------------------------------------------------------- |
| `id`              | `integer` | The unique ID of the scenario.                              |
| `scenario_name`   | `string`  | The name of the scenario.                                   |
| `description`     | `string`  | A brief description of the scenario.                        |
| `expected_result` | `string`  | The expected outcome of the scenario.                       |
| `enabled`         | `boolean` | Indicates if the scenario is active or not.                 |
| `execute_mode`    | `string`  | The execution mode (e.g., `AUTOMATED`).                     |
| `source_file`     | `string`  | The path to the source file of the scenario (if available). |

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
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}/scenarios" \
-H "Authorization: Bearer <your_access_token>"
```
