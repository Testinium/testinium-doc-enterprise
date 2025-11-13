# Get All Scenarios

The endpoint retrieves all scenarios associated with a specific project. It returns a list of scenarios, including details such as their names, descriptions, and source files.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                    |
| ----------------- | -------- | -------- | ------------------------------ |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project. |

***

### Request Headers

| Header          | Value                   | Description                                   |
| --------------- | ----------------------- | --------------------------------------------- |
| `Authorization` | `Bearer {access_token}` | The access token obtained after login.        |
| `Accept`        | `application/json`      | The type of content expected in the response. |

***

### Response Body

Upon a successful request, the API returns a list of scenarios for the specified project.

```json
[
    {
        "id": 3085,
        "scenario_name": "sevgitest12345",
        "enabled": true,
        "execute_mode": "AUTOMATED",
        "project_id": 580
    },
    {
        "id": 3086,
        "scenario_name": "Sevgi Test12345",
        "description": "12345",
        "expected_result": "12345",
        "enabled": true,
        "execute_mode": "AUTOMATED",
        "source_file": "Ios/IOSMainnPage.spec",
        "project_id": 580,
        "java_test_class": "Ios/IOSMainnPage",
        "java_test_methods": "@Gratissss"
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

| HTTP Code | Description                                               |
| --------- | --------------------------------------------------------- |
| `404`     | The specified project was not found.                      |
| `403`     | The user does not have permission to access this project. |
| `401`     | Invalid or missing authentication credentials.            |
| `500`     | Internal server error; something went wrong.              |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios' \
--header 'Authorization: Bearer <your_access_token>'
```
