---
hidden: true
---

# Add Scenarios To Plan

The endpoint adds scenarios to a specific plan. A request containing the IDs of the scenarios to be added is sent along with the relevant project and plan information.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}/scenarios`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                      |
| ----------------- | -------- | -------- | -------------------------------- |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project.   |
| `planNameOrId`    | `Object` | Yes      | The name or ID of the test plan. |

***

### Request Body

The request body must contain a `ScenarioIdsOfPlanDTO` object that includes the IDs of the scenarios to be added.

```json
{
   "scenarios": [13, 16]
}
```

| Field | Type         | Description                                  |
| ----- | ------------ | -------------------------------------------- |
| `id`  | `List<Long>` | The unique IDs of the scenarios to be added. |

***

### Response Body

Upon a successful request, the API returns a `StatusResponse` object indicating the status of the operation.

```json
{
  "status": "success"
}
```

| Field    | Type     | Description                                    |
| -------- | -------- | ---------------------------------------------- |
| `status` | `string` | The status of the operation (e.g., "success"). |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message                  | Description                                            |
| --------- | ------------------------------ | ------------------------------------------------------ |
| `401`     | `Unauthorized`                 | Authorization failed. The user is not logged in.       |
| `403`     | `Forbidden`                    | The user does not have permission to access the plan.  |
| `404`     | `Scenario not found`           | The specified scenario was not found.                  |
| `400`     | `Invalid scenario for project` | The specified scenario does not belong to the project. |
| `409`     | `Scenario already exists`      | The plan already contains the specified scenario.      |
| `500`     | `Internal Server Error`        | An unexpected error occurred on the server side.       |

***

### Example Request

```bash
curl --location --request PUT '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}/scenarios' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <your_access_token>' \
--data '{"scenarios": [13, 16]}'
```
