# Get All Projects

The endpoint retrieves all projects associated with the company of the authenticated user. It returns a list of projects in JSON format with detailed information about each project.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/`
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

### Response Body

Upon a successful request, the API returns the following JSON structure:

```json
[
  {
    "id": 89,
    "project_name": "project1",
    "description": "",
    "enabled": true,
    "repository_path": "",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_JAVA",
    "test_runner_tool": "MAVEN"
  }
]
```

| Field              | Type      | Description                                                              |
| ------------------ | --------- | ------------------------------------------------------------------------ |
| `id`               | `integer` | The unique ID of the project.                                            |
| `project_name`     | `string`  | The name of the project.                                                 |
| `description`      | `string`  | A brief description of the project.                                      |
| `enabled`          | `boolean` | Indicates whether the project is active or not.                          |
| `repository_path`  | `string`  | The path to the project's repository.                                    |
| `test_framework`   | `string`  | The testing framework used (e.g., APPIUM).                               |
| `test_file_type`   | `string`  | The type of test files associated with the project (e.g., APPIUM\_JAVA). |
| `test_runner_tool` | `string`  | The tool used to run the tests (e.g., MAVEN).                            |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message  | Description                                               |
| --------- | -------------- | --------------------------------------------------------- |
| `204`     | `No Content`   | No projects are available for the user's company.         |
| `401`     | `Unauthorized` | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`    | The user does not have permission to access the projects. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
