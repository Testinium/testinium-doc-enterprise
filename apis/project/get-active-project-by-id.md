# Get Active Project By ID

The endpoint retrieves the active project by its ID. It ensures that the project belongs to a company accessible to the user.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/active`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter   | Type   | Required | Description                            |
| ----------- | ------ | -------- | -------------------------------------- |
| `projectId` | `Long` | Yes      | The ID of the project to be retrieved. |

***

### Response Body

Upon a successful request, the API returns a `ProjectDTO` object containing details of the active project.

```json
{
  "id": 351,
  "project_name": "project1",
  "description": "",
  "enabled": true,
  "repository_path": "https://github.com/user/project1",
  "test_framework": "SERVICE",
  "test_file_type": "SERVICE_KARATE",
  "test_runner_tool": "MAVEN"
}
```

| Field              | Type      | Description                                         |
| ------------------ | --------- | --------------------------------------------------- |
| `id`               | `Long`    | The ID of the project.                              |
| `project_name`     | `String`  | The name of the project.                            |
| `description`      | `String`  | The description of the project.                     |
| `enabled`          | `Boolean` | Whether the project is active or not.               |
| `repository_path`  | `String`  | The Git repository URL associated with the project. |
| `test_framework`   | `String`  | The testing framework used in the project.          |
| `test_file_type`   | `String`  | The type of test files in the project.              |
| `test_runner_tool` | `String`  | The tool used to run the tests.                     |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                              |
| --------- | ----------------------- | -------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.         |
| `403`     | `Forbidden`             | The user does not have permission to access the project. |
| `404`     | `Project not found`     | The specified project was not found or is not active.    |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.         |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/active" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
