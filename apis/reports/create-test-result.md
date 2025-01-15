# Create Test Result

The endpoint allows users to create a new test result by submitting necessary test information, including optional log and video files.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/testResults/`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required

***

### Request Body

The request body must contain a JSON object representing the test result details. The following fields can be provided:

```json
{
  "logFileToken": "abc123",
  "videoFileToken": "xyz789",
  "sessionId": "unique-session-id"
}
```

| Parameter        | Type     | Required | Description                                                                                       |
| ---------------- | -------- | -------- | ------------------------------------------------------------------------------------------------- |
| `logFileToken`   | `String` | No       | A token representing the log file for the test result.                                            |
| `videoFileToken` | `String` | No       | A token representing the video file for the test result.                                          |
| `sessionId`      | `String` | No       | A unique identifier for the test session. If not provided, a random session ID will be generated. |

***

### Response Body

Upon a successful request, the API returns a `TestResultDTO` object containing details of the newly created test result.

```json
{
  "id": 102,
  "logFileToken": "abc123",
  "videoFileToken": "xyz789",
  "sessionId": "unique-session-id",
  "user": {
    "id": 34,
    "username": "testUser"
  },
  "company": {
    "id": 56,
    "name": "TestCompany"
  },
  "nodeLogPath": "/logs/testResult.log",
  "videoPath": "/videos/testResult.mp4"
}
```

| Field            | Type     | Description                                                     |
| ---------------- | -------- | --------------------------------------------------------------- |
| `id`             | `Long`   | The unique ID of the created test result.                       |
| `logFileToken`   | `String` | The token of the log file associated with this test result.     |
| `videoFileToken` | `String` | The token of the video file associated with this test result.   |
| `sessionId`      | `String` | Unique session identifier.                                      |
| `user`           | `Object` | Information about the user who created the test result.         |
| `company`        | `Object` | Information about the company associated with this test result. |
| `nodeLogPath`    | `String` | Path where the log file is stored.                              |
| `videoPath`      | `String` | Path where the video file is stored.                            |

***

### Error Codes

| HTTP Code | Error Message           | Description                                        |
| --------- | ----------------------- | -------------------------------------------------- |
| `400`     | `Invalid Request`       | The request body is missing required fields.       |
| `401`     | `Unauthorized`          | User authentication failed.                        |
| `403`     | `Access denied`         | User is not authorized to create this test result. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.   |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/testResults/" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
      "logFileToken": "abc123",
      "videoFileToken": "xyz789",
      "sessionId": "unique-session-id"
    }'
```
