# Update Test Parameters

The endpoint updates the test parameters associated with a specific scenario in a project. The request contains the new test parameters that will replace the existing ones.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/testParameters`
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

The request body must contain a `TestParameterListDTO` object that includes the updated test parameters.

```json
{
  "testParameters": [
    {
      "name": "parameter1",
      "value": "value1",
      "description": "Description"
    },
    {
      "name": "parameter2",
      "value": "value2",
      "description": "Description"
    }
  ]
}
```

| Field            | Type                     | Description                            |
| ---------------- | ------------------------ | -------------------------------------- |
| `testParameters` | `List<TestParameterDTO>` | List of test parameters to be updated. |

***

### Response Body

Upon a successful request, the API returns a `StatusResponse` object indicating the operation status.

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

| HTTP Code | Error Message           | Description                                                         |
| --------- | ----------------------- | ------------------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                    |
| `403`     | `Forbidden`             | The user does not have permission to access the scenario.           |
| `404`     | `Scenario not found`    | The specified scenario was not found.                               |
| `400`     | `Invalid character`     | The source file or Java test parameters contain invalid characters. |
| `409`     | `Invalid scenario type` | The scenario type is not valid for this operation.                  |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                    |

***

### Example Request

```bash
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/testParameters" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
  "testParameters": [
    {
      "name": "parameter1",
      "value": "value1",
      "description": "Description"
    },
    {
      "name": "parameter2",
      "value": "value2",
      "description": "Description"
    }
  ]
}'
```
