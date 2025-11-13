---
hidden: true
---

# Delete Test Plan

The endpoint deletes a specified test plan for a particular project. The user must provide the project and plan identifiers in the path. The API will return an appropriate response based on whether the deletion was successful or if there was an error.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}`
* **Method**: `DELETE`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

<table><thead><tr><th width="201">Parameter</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>projectNameOrId</code></td><td><code>Object</code></td><td>Yes</td><td>The name or ID of the project containing the plan.</td></tr><tr><td><code>planNameOrId</code></td><td><code>Object</code></td><td>Yes</td><td>The name or ID of the plan to be deleted.</td></tr></tbody></table>

***

### Response

Upon a successful request, the API will respond with an HTTP status code indicating the result of the deletion. If the deletion is not supported, a `BusinessException` will be thrown.

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message                | Description                                                           |
| --------- | ---------------------------- | --------------------------------------------------------------------- |
| `401`     | `Unauthorized`               | Authorization failed. The user is not logged in.                      |
| `403`     | `Forbidden`                  | The user does not have permission to delete the plan for the project. |
| `404`     | `Plan not found`             | The specified plan was not found.                                     |
| `500`     | `Internal Server Error`      | An unexpected error occurred on the server side.                      |
| `501`     | `Unsupported service method` | The delete operation is not supported for this endpoint.              |

***

### Example Request

```bash
curl -X DELETE "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans/{planNameOrId}" \
--header 'Authorization: Bearer <your_access_token>' \
-H "Accept: application/json"
```
