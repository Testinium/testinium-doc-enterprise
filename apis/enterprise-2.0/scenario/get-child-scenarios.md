---
hidden: true
---

# Get Child Scenarios

The endpoint retrieves the child scenarios associated with a specific scenario within a project. It provides a list of child scenarios based on the given project and scenario information.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/childScenarios`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter          | Type     | Required | Description                     |
| ------------------ | -------- | -------- | ------------------------------- |
| `projectNameOrId`  | `Object` | Yes      | The name or ID of the project.  |
| `scenarioNameOrId` | `Object` | Yes      | The name or ID of the scenario. |

***

### Response Body

Upon a successful request, the API returns a list of child scenarios as a `List<ScenarioDTO>` object.

```json
[
  {
    "id": 3,
    "name": "Child Scenario 1",
    "description": "Description of Child Scenario 1"
  },
  {
    "id": 4,
    "name": "Child Scenario 2",
    "description": "Description of Child Scenario 2"
  }
]
```

| Field         | Type     | Description                                |
| ------------- | -------- | ------------------------------------------ |
| `id`          | `Long`   | The unique ID of the child scenario.       |
| `name`        | `String` | The name of the child scenario.            |
| `description` | `String` | A brief description of the child scenario. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`             | The user does not have permission to access the scenario. |
| `404`     | `Scenario not found`    | The specified scenario was not found.                     |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/childScenarios" \
--header 'Authorization: Bearer <your_access_token>' \
-H "Accept: application/json"
```
