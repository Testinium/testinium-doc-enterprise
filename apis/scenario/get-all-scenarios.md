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

| HTTP Code | Description                                               |
| --------- | --------------------------------------------------------- |
| `404`     | The specified project was not found.                      |
| `403`     | The user does not have permission to access this project. |
| `401`     | Invalid or missing authentication credentials.            |
| `500`     | Internal server error; something went wrong.              |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
