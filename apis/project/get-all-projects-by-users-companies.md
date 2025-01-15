# Get All Projects by User's Companies

The endpoint retrieves all projects associated with the companies that the authenticated user belongs to. It returns a list of projects in the form of ProjectDTO objects.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/byUserCompanies`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Request Headers

| Header          | Value                   | Description                                   |
| --------------- | ----------------------- | --------------------------------------------- |
| `Authorization` | `Bearer {access_token}` | The access token obtained after login.        |
| `Accept`        | `application/json`      | The type of content expected in the response. |

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

```json
[
  {
     "id": 335,
     "project_name": "project1",
     "description": "",
     "enabled": true,
     "repository_path": "project1",
     "test_framework": "APPIUM",
     "test_file_type": "APPIUM_GAUGE",
     "test_runner_tool": "MAVEN"
  }
]
```

| Field              | Type      | Description                                      |
| ------------------ | --------- | ------------------------------------------------ |
| `id`               | `integer` | The unique ID of the project.                    |
| `project_name`     | `string`  | The name of the project.                         |
| `description`      | `string`  | The description of the project.                  |
| `enabled`          | `boolean` | Indicates if the project is enabled or not.      |
| `repository_path`  | `string`  | The repository path associated with the project. |
| `test_framework`   | `string`  | The test framework used for the project.         |
| `test_file_type`   | `string`  | The type of test files used in the project.      |
| `test_runner_tool` | `string`  | The tool used to run the tests.                  |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message  | Description                                                                    |
| --------- | -------------- | ------------------------------------------------------------------------------ |
| `204`     | `No Content`   | The user does not have access to any projects associated with their companies. |
| `401`     | `Unauthorized` | Authorization failed. The user is not logged in.                               |
| `403`     | `Forbidden`    | The user does not have permission to access the projects.                      |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/byUserCompanies" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
