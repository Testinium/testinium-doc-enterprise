# Get Scenario by Name or ID

The endpoint retrieves a specific test scenario by its name or ID for the authenticated user. It returns a `ScenarioDTO` object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/scenarios/{scenarioNameOrId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter          | Type     | Required | Description                                 |
| ------------------ | -------- | -------- | ------------------------------------------- |
| `scenarioNameOrId` | `Object` | Yes      | The name or ID of the scenario to retrieve. |

***

### Response Body

Upon a successful request, the API returns a test scenario in JSON format.

```json
{
    "id": 406,
    "scenario_name": "scenario1",
    "description": "",
    "expected_result": "",
    "enabled": true,
    "execute_mode": "AUTOMATED",
    "source_file": "com/example/ScenarioTests.java",
    "project_id": 61,
    "java_test_class": "com.example.ScenarioTests",
    "java_test_methods": "sendBigVideo"
}
```

| Field               | Type      | Description                                                  |
| ------------------- | --------- | ------------------------------------------------------------ |
| `id`                | `integer` | The unique ID of the test scenario                           |
| `scenario_name`     | `string`  | The name of the test scenario                                |
| `description`       | `string`  | A brief description of the test scenario                     |
| `expected_result`   | `string`  | The expected outcome of the test scenario                    |
| `enabled`           | `boolean` | Indicates if the scenario is active                          |
| `execute_mode`      | `string`  | Defines whether the scenario is `AUTOMATED` or `MANUAL`      |
| `source_file`       | `string`  | The file path containing the test scenario                   |
| `project_id`        | `integer` | The ID of the project associated with the test scenario      |
| `java_test_class`   | `string`  | The fully qualified name of the Java test class              |
| `java_test_methods` | `string`  | The specific Java method(s) within the test class to execute |
| `createdBy`         | `string`  | The user who created the scenario                            |

***

### Error Codes

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`             | The user does not have permission to access the scenario. |
| `404`     | `Scenario not found`    | The specified scenario was not found.                     |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/scenarios/{scenarioNameOrId}" \
--header 'Authorization: Bearer <your_access_token>' \
-H "Accept: application/json"
```
