# Create Scenario

The endpoint creates a new scenario for a specific project. A new scenario is saved based on the project information and scenario details provided by the user.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                    |
| ----------------- | -------- | -------- | ------------------------------ |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project. |

***

### Request Body

The request body must be a JSON object containing the details of the scenario.

```json
{
  "scenarioName": "Login Test",
  "description": "Test if the user can login successfully",
  "expectedResult": "User should be redirected to the dashboard",
  "enabled": true,
  "parentScenarioId": null,
  "executeMode": "AUTOMATED",
  "sourceFile": "loginTest.feature",
  "projectId": 1,
  "type": "SELENIUM"
}
```

| Field              | Type      | Required | Description                                                  |
| ------------------ | --------- | -------- | ------------------------------------------------------------ |
| `scenarioName`     | `String`  | Yes      | The name of the scenario.                                    |
| `description`      | `String`  | No       | A description of the scenario.                               |
| `expectedResult`   | `String`  | Yes      | The expected result of the scenario test.                    |
| `enabled`          | `Boolean` | Yes      | Indicates whether the scenario is enabled or not.            |
| `parentScenarioId` | `Long`    | No       | The ID of the parent scenario, if applicable.                |
| `executeMode`      | `String`  | Yes      | The execution mode (`AUTOMATED` or `MANUAL`).                |
| `sourceFile`       | `String`  | Yes      | The source file of the scenario (e.g., `loginTest.feature`). |
| `projectId`        | `Long`    | Yes      | The ID of the project to which the scenario belongs.         |
| `type`             | `String`  | Yes      | The type of the test (e.g., `SELENIUM`).                     |

***

### Response Body

Upon a successful request, the API returns a `ScenarioDTO` object containing the created scenario.

```json
{
  "id": 1,
  "scenario_name": "Login Test",
  "description": "Test if the user can login successfully",
  "expectedResult": "User should be redirected to the dashboard",
  "enabled": true,
  "parentScenarioId": null,
  "executeMode": "AUTOMATED",
  "sourceFile": "loginTest.feature",
  "projectId": 1,
  "type": "SELENIUM"
}
```

| Field              | Type      | Description                                                  |
| ------------------ | --------- | ------------------------------------------------------------ |
| `id`               | `Long`    | The unique identifier of the created scenario.               |
| `scenario_name`    | `String`  | The name of the scenario.                                    |
| `description`      | `String`  | The description of the scenario.                             |
| `expectedResult`   | `String`  | The expected result of the scenario test.                    |
| `enabled`          | `Boolean` | Indicates whether the scenario is enabled or not.            |
| `parentScenarioId` | `Long`    | The ID of the parent scenario, if applicable.                |
| `executeMode`      | `String`  | The execution mode (`AUTOMATED` or `MANUAL`).                |
| `sourceFile`       | `String`  | The source file of the scenario (e.g., `loginTest.feature`). |
| `projectId`        | `Long`    | The ID of the project to which the scenario belongs.         |
| `type`             | `String`  | The type of the test (e.g., `SELENIUM`).                     |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                   |
| --------- | ----------------------- | ------------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.              |
| `403`     | `Forbidden`             | The user does not have permission to access the project.      |
| `400`     | `Invalid Character`     | Invalid characters found in the source file.                  |
| `422`     | `Validation Failed`     | Required fields for scenario creation are missing or invalid. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.              |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
  "scenarioName": "Login Test",
  "description": "Test if the user can login successfully",
  "expectedResult": "User should be redirected to the dashboard",
  "enabled": true,
  "parentScenarioId": null,
  "executeMode": "AUTOMATED",
  "sourceFile": "loginTest.feature",
  "projectId": 1,
  "type": "SELENIUM"
}'
```