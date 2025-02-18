# Update Scenario

The endpoint is used to update an existing scenario within a specific project. The scenario details are updated based on the project and scenario information provided by the user.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter          | Type     | Required | Description                                   |
| ------------------ | -------- | -------- | --------------------------------------------- |
| `projectNameOrId`  | `Object` | Yes      | The name or ID of the project.                |
| `scenarioNameOrId` | `Object` | Yes      | The name or ID of the scenario to be updated. |

***

### Request Body

The request body must be a JSON object containing the details of the scenario to be updated.

```json
{
  "scenario_name": "DenemeSenaryo13",
  "description": "",
  "expected_result": "",
  "enabled": true,
  "execute_mode": "AUTOMATED",
  "source_file": "Android/MainPage.spec",
  "project_id": 580,
  "java_test_class": "Android/MainPage",
  "java_test_methods": "@Swipeeee"
}
```

| Field         | Type     | Required | Description                               |
| ------------- | -------- | -------- | ----------------------------------------- |
| `name`        | `String` | Yes      | The new name of the scenario.             |
| `description` | `String` | No       | The new description of the scenario.      |
| `sourceFile`  | `String` | Yes      | The new source file path of the scenario. |

***

### Response Body

Upon a successful request, the API returns a `ScenarioDTO` object containing the updated scenario.

```json
{
    "id": 3132,
    "scenario_name": "DenemeSenaryo",
    "description": "",
    "expected_result": "",
    "enabled": true,
    "execute_mode": "AUTOMATED",
    "source_file": "Android/MainPage.spec",
    "project_id": 580,
    "java_test_class": "Android/MainPage",
    "java_test_methods": "@Swipeeee"
}
```

| Field         | Type     | Description                               |
| ------------- | -------- | ----------------------------------------- |
| `id`          | `Long`   | The unique identifier of the scenario.    |
| `name`        | `String` | The new name of the scenario.             |
| `description` | `String` | The new description of the scenario.      |
| `sourceFile`  | `String` | The new source file path of the scenario. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.            |
| `403`     | `Forbidden`             | The user does not have permission to access the project.    |
| `404`     | `Scenario Not Found`    | The specified scenario could not be found.                  |
| `400`     | `Invalid Character`     | Invalid characters found in the source file.                |
| `422`     | `Validation Failed`     | Required fields for scenario update are missing or invalid. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.            |

***

### Example Request

```bash
curl --location --request PUT '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
        "scenario_name": "DenemeSenaryo",
        "description": "",
        "expected_result": "",
        "enabled": true,
        "execute_mode": "AUTOMATED",
        "source_file": "Android/MainPage.spec",
        "project_id": 580,
        "java_test_class": "Android/MainPage",
        "java_test_methods": "@Swipeeee"
    }'
```
