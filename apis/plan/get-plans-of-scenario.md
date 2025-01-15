# Get Plans Of Scenario

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Plans Of Scenario

The endpoint retrieves the plans associated with a specific scenario. It returns a list of plans based on the provided project and scenario information.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/plans`
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

Upon a successful request, the API returns a list of `PlanDTO` objects associated with the specified scenario.

{\`\[ { "id": 1, "name": "Test Plan A", "description": "Description for Test Plan A", "projectId": 123, "userId": 1 }, { "id": 2, "name": "Test Plan B", "description": "Description for Test Plan B", "projectId": 123, "userId": 1 } ]\`}

| Field         | Type      | Description                              |
| ------------- | --------- | ---------------------------------------- |
| `id`          | `integer` | The unique ID of the plan.               |
| `name`        | `string`  | The name of the plan.                    |
| `description` | `string`  | A brief description of the plan.         |
| `projectId`   | `integer` | The ID of the associated project.        |
| `userId`      | `integer` | The ID of the user who created the plan. |

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
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/plans" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
