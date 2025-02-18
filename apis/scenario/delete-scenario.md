# Delete Scenario

The endpoint is used to delete an existing scenario within a specific project. However, it currently returns an error message indicating that the service method is unsupported.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}`
* **Method**: `DELETE`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter          | Type     | Required | Description                                   |
| ------------------ | -------- | -------- | --------------------------------------------- |
| `projectNameOrId`  | `Object` | Yes      | The name or ID of the project.                |
| `scenarioNameOrId` | `Object` | Yes      | The name or ID of the scenario to be deleted. |

***

### Response Body

Since this API is currently unsupported, it will always return an error. The API will respond with an unsupported service method error.

```json
{
  "error": "UNSUPPORTED_SERVICE_METHOD",
  "message": "This service method is not supported."
}
```

| Field     | Type     | Description        |
| --------- | -------- | ------------------ |
| `error`   | `String` | The error code.    |
| `message` | `String` | The error message. |

***

### Error Codes

Possible error codes during the operation:

| HTTP Code | Error Message                | Description                                              |
| --------- | ---------------------------- | -------------------------------------------------------- |
| `400`     | `Unsupported Service Method` | Error indicating that the service method is unsupported. |

***

### Example Request

```bash
curl -X DELETE "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/scenarios/{scenarioNameOrId}" \
--header 'Authorization: Bearer <your_access_token>'
```
