---
hidden: true
---

# Delete Project

This endpoint allows a user to delete an existing project. Below are the details regarding the usage of this API.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}`
* **Method**: `DELETE`

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message        | Description                                                 |
| --------- | -------------------- | ----------------------------------------------------------- |
| `400`     | `Invalid input data` | There are missing or incorrect details in the request data. |

### Request

To delete a project, the project name or ID must be specified in the URL path.

#### Parameters

<table><thead><tr><th width="208">Parameter</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>projectNameOrId</code></td><td><code>string</code></td><td>Yes</td><td>The name or ID of the project to delete.</td></tr></tbody></table>

***

### Response

This endpoint currently throws an exception indicating that the service method is unsupported.

***

### Example Request

```bash
curl --location --request DELETE '<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}' \
--header 'Authorization: <your_access_token>'
```
