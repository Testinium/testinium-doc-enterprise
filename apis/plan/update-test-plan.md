# Update Test Plan

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Update Test Plan

The endpoint updates an existing test plan for a specific project. The user must provide the project and plan identifiers in the path, along with the updated plan specifications in the request body. The API validates the input and returns the updated plan as a ProjectDTO object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                                        |
| ----------------- | -------- | -------- | -------------------------------------------------- |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project containing the plan. |
| `planNameOrId`    | `Object` | Yes      | The name or ID of the plan to be updated.          |

***

### Request Body Table

The JSON format request data that needs to be sent for updating a test plan is as follows:

{\`{ "name": "Updated Test Plan", "description": "Updated description of the test plan", "period": { "periodType": "REPETITIVE", "repeatPeriod": 3 }, // Other plan data... }\`}

| Parameter     | Type     | Required | Description                                                                            |
| ------------- | -------- | -------- | -------------------------------------------------------------------------------------- |
| `name`        | `string` | No       | The updated name of the test plan                                                      |
| `description` | `string` | No       | The updated description of the test plan                                               |
| `period`      | `object` | Yes      | The updated timing details for the test plan, including period type and repeat period. |

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

{\`{ "id": 123, "name": "Updated Test Plan", "description": "Updated description of the test plan", "period": { "periodType": "REPETITIVE", "repeatPeriod": 3 }, "projectId": 10, "user": { "id": 1, "username": "john\_doe", "email": "john@example.com" } }\`}

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
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
  "name": "Updated Test Plan",
  "description": "Updated description of the test plan",
  "period": {
    "periodType": "REPETITIVE",
    "repeatPeriod": 3
  }
}'
```
