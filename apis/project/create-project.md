# Create Project

This endpoint is used to create a new project by a user. Below are the details regarding the usage of the API.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Request

The JSON format request data that needs to be sent for creating a project is as follows:

```json
{
  "projectName": "New Project",
  "description": "This is a new project description",
  "enabled": true,
  "repositoryPath": "/path/to/repository",
  "testFramework": "SELENIUM",
  "testFileType": "JAVA",
  "testRunnerTool": "MAVEN"
}
```

| Parameter        | Type      | Required | Description                                            |
| ---------------- | --------- | -------- | ------------------------------------------------------ |
| `projectName`    | `string`  | Yes      | The name of the project                                |
| `description`    | `string`  | No       | The description of the project                         |
| `enabled`        | `boolean` | Yes      | Whether the project is enabled or not                  |
| `repositoryPath` | `string`  | Yes      | The path to the repository associated with the project |
| `testFramework`  | `string`  | Yes      | The test framework to be used (e.g., `SELENIUM`)       |
| `testFileType`   | `string`  | Yes      | The type of test file used (e.g., `JAVA`)              |
| `testRunnerTool` | `string`  | Yes      | The test runner tool to be used (e.g., `MAVEN`)        |

***

### Response

Upon a successful request, the API returns the following JSON structure:

```json
{
  "id": 163,
  "project_name": "New Project",
  "description": "This is a new project description",
  "enabled": true,
  "repositoryPath": "/path/to/repository",
  "testFramework": "SELENIUM",
  "testFileType": "JAVA",
  "testRunnerTool": "MAVEN"
}
```

| Field            | Type      | Description                                            |
| ---------------- | --------- | ------------------------------------------------------ |
| `id`             | `integer` | The unique ID of the created project                   |
| `project_name`   | `string`  | The name of the project                                |
| `description`    | `string`  | The description of the project                         |
| `enabled`        | `boolean` | Whether the project is enabled or not                  |
| `repositoryPath` | `string`  | The path to the repository associated with the project |
| `testFramework`  | `string`  | The test framework used in the project                 |
| `testFileType`   | `string`  | The type of test file used                             |
| `testRunnerTool` | `string`  | The test runner tool used in the project               |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `400`     | `Invalid input data`    | Missing or incorrect details in the request data.         |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`             | The user does not have permission to perform this action. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/projects/" \
-H "Authorization: Bearer <token>" \
-H "Content-Type: application/json" \
-d '{
  "projectName": "New Project",
  "description": "This is a new project description",
  "enabled": true,
  "repositoryPath": "/path/to/repository",
  "testFramework": "SELENIUM",
  "testFileType": "JAVA",
  "testRunnerTool": "MAVEN"
}'
```
