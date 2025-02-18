# Get Test Parameters

The endpoint retrieves the test parameters associated with a specific scenario in a project. The response contains a list of test parameters for scenarios of type `AbstractSeleniumScenario`.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/testParameters`
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

Upon a successful request, the API returns a `TestParameterListDTO` object containing the test parameters.

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

| Field            | Type                     | Description                                           |
| ---------------- | ------------------------ | ----------------------------------------------------- |
| `testParameters` | `List<TestParameterDTO>` | List of test parameters associated with the scenario. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`             | The user does not have permission to access the scenario. |
| `404`     | `Scenario not found`    | The specified scenario was not found.                     |
| `400`     | `Invalid scenario type` | The scenario type is not valid for this operation.        |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl -X GET "<your-api-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}/testParameters" \
--header 'Authorization: Bearer <your_access_token>' \
-H "Accept: application/json"
```
