# Get Project by ID or Name

The endpoint enables authenticated users to retrieve detailed information about a project by specifying either its unique ID or name.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### URL Parameters

| Parameter         | Type     | Required | Description                                               |
| ----------------- | -------- | -------- | --------------------------------------------------------- |
| `projectNameOrId` | `String` | Yes      | The unique **ID** or **name** of the project to retrieve. |

***

### Request Headers

| Header          | Value                   | Description                                   |
| --------------- | ----------------------- | --------------------------------------------- |
| `Authorization` | `Bearer {access_token}` | The access token obtained after login.        |
| `Accept`        | `application/json`      | The type of content expected in the response. |

***

### Response Body

On success, the API returns the following JSON structure:

```json
{
  "id": 89,
  "project_name": "project1",
  "description": "",
  "enabled": true,
  "repository_path": "deneme",
  "test_framework": "APPIUM",
  "test_file_type": "APPIUM_JAVA",
  "test_runner_tool": "MAVEN"
}
```

| Field              | Type      | Description                                                 |
| ------------------ | --------- | ----------------------------------------------------------- |
| `id`               | `integer` | The unique identifier of the project.                       |
| `project_name`     | `string`  | The name of the project.                                    |
| `description`      | `string`  | A brief description of the project.                         |
| `enabled`          | `boolean` | Indicates if the project is active or inactive.             |
| `repository_path`  | `string`  | The path to the repository where the project is stored.     |
| `test_framework`   | `string`  | The testing framework used in the project (e.g., APPIUM).   |
| `test_file_type`   | `string`  | The type of test files in the project (e.g., APPIUM\_JAVA). |
| `test_runner_tool` | `string`  | The tool used to execute tests (e.g., MAVEN).               |

***

### Error Codes

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `404`     | `Project Not Found`     | No project with the given ID or name exists.              |
| `403`     | `Access Denied`         | The user does not have permission to access this project. |
| `401`     | `Unauthorized`          | Invalid or missing authentication credentials.            |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.               |

***

### Example Request

**Using Project ID**

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
