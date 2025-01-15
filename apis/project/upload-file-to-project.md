# Upload File to Project

The endpoint allows users to upload files to a specific project. The request must include a list of files, and the user must have appropriate permissions to access the project.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/file/project/{projectId}`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `multipart/form-data`

***

### Path Variables

| Parameter   | Type   | Required | Description                                            |
| ----------- | ------ | -------- | ------------------------------------------------------ |
| `projectId` | `Long` | Yes      | The ID of the project where the file will be uploaded. |

***

### Request Body

The request body must include one or more files to upload. The files should be sent as a multipart form-data request.

| Parameter | Type                  | Required | Description                |
| --------- | --------------------- | -------- | -------------------------- |
| `files`   | `List<MultipartFile>` | Yes      | A list of files to upload. |

***

### Response Body

Upon a successful request, the API returns an HTTP status of 200 OK.

| Field    | Type     | Description                            |
| -------- | -------- | -------------------------------------- |
| `status` | `string` | The status of the file upload request. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                       |
| --------- | ----------------------- | ----------------------------------------------------------------- |
| `400`     | `Invalid file`          | The file is empty or invalid.                                     |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                  |
| `403`     | `Forbidden`             | The user does not have permission to upload files to the project. |
| `404`     | `Project not found`     | The specified project was not found.                              |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                  |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/file/project/{projectId}" \
-H "Authorization: Bearer <your_access_token>" \
-F "files=@path_to_file1"
```
