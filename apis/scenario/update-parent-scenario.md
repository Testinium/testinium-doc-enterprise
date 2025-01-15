# Update Parent Scenario

The endpoint updates the parent scenario for a specific scenario within a project. It associates a parent scenario based on the provided project and scenario information.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/parent`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter          | Type     | Required | Description                     |
| ------------------ | -------- | -------- | ------------------------------- |
| `projectNameOrId`  | `Object` | Yes      | The name or ID of the project.  |
| `scenarioNameOrId` | `Object` | Yes      | The name or ID of the scenario. |

***

### Request Body

The request body must contain a `ParentScenarioDTO` object that specifies the ID of the parent scenario.

```
{
  "parentScenarioId": 2
}
```

| Field              | Type   | Description                                     |
| ------------------ | ------ | ----------------------------------------------- |
| `parentScenarioId` | `Long` | The unique ID of the parent scenario to be set. |

***

### Response Body

Upon a successful request, the API returns the updated parent scenario as a `ScenarioDTO` object.

```json
{
  "id": 2,
  "name": "Parent Scenario",
  "description": "Description of the parent scenario"
}
```

| Field         | Type     | Description                          |
| ------------- | -------- | ------------------------------------ |
| `id`          | `Long`   | The unique ID of the scenario.       |
| `name`        | `String` | The name of the scenario.            |
| `description` | `String` | A brief description of the scenario. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`             | The user does not have permission to access the scenario. |
| `404`     | `Scenario not found`    | The specified scenario or parent scenario was not found.  |
| `400`     | `Invalid character`     | The source file contains invalid characters.              |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl -X PUT "<your-api-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/parent" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
  "parentScenarioId": 2
}'
```
