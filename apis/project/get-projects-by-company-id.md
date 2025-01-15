# Get Projects by Company ID

This endpoint retrieves a list of projects associated with a specific company. It ensures that the authenticated user has access to the company before returning the project list.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/projectsByCompany/{companyId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter   | Type   | Required | Description                          |
| ----------- | ------ | -------- | ------------------------------------ |
| `companyId` | `Long` | Yes      | The unique identifier of the company |

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

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message       | Description                                                                |
| --------- | ------------------- | -------------------------------------------------------------------------- |
| `204`     | `No Content`        | The user does not have access to any projects associated with the company. |
| `401`     | `Unauthorized`      | Authorization failed. The user is not logged in.                           |
| `403`     | `Forbidden`         | The user does not have permission to access the company.                   |
| `404`     | `Company not found` | The specified company was not found.                                       |

***

### Example Requests

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/projectsByCompany/{companyId}" \
-H "Authorization: Bearer <token>"
```
