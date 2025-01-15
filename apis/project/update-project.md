# Update Project

This endpoint is used to update an existing project. A user can update project details using the project name or ID. Below are the details of the API.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Request Body Table

The JSON format request data that needs to be sent for updating a project is as follows:

```json
{
  "name": "Updated Project Name",
  "description": "Updated project description"
}
```

| Parameter       | Type     | Required | Description                                           |
| --------------- | -------- | -------- | ----------------------------------------------------- |
| `name`          | `string` | No       | The updated name of the project                       |
| `description`   | `string` | No       | The updated description of the project                |
| `startDate`     | `string` | No       | The updated start date of the project                 |
| `endDate`       | `string` | No       | The updated end date of the project                   |
| `testFramework` | `string` | No       | The test framework used in the project (e.g., Karate) |

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

```json
{
  "id": 123,
  "name": "Updated Project Name",
  "description": "Updated project description",
  "startDate": "2024-10-15",
  "endDate": "2024-12-31",
  "testFramework": "Karate",
  "user": {
    "id": 1,
    "username": "john_doe",
    "email": "john@example.com"
  },
  "company": {
    "id": 10,
    "name": "Example Corp"
  }
}
```

| Field           | Type      | Description                                               |
| --------------- | --------- | --------------------------------------------------------- |
| `id`            | `integer` | The unique ID of the updated project                      |
| `name`          | `string`  | The updated name of the project                           |
| `description`   | `string`  | The updated description of the project                    |
| `startDate`     | `string`  | The updated start date of the project                     |
| `endDate`       | `string`  | The updated end date of the project                       |
| `testFramework` | `string`  | The test framework used in the project                    |
| `user`          | `object`  | Information about the user who updated the project        |
| `company`       | `object`  | Information about the company associated with the project |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `400`     | `Invalid input data`    | There are missing or incorrect details in the request data. |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.            |
| `403`     | `Forbidden`             | The user does not have permission to perform this action.   |
| `404`     | `Project not found`     | The project intended to be updated was not found.           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.            |

***

### Example Requests

```bash
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId} \
-H "Authorization: Bearer <token>" \
-H "Content-Type: application/json" \
-d '{
  "name": "Updated Project Name",
  "description": "Updated project description"
}'
```
