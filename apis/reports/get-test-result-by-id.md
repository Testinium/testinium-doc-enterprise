# Get Test Result by ID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Test Result by ID

The endpoint retrieves a test result based on the provided result ID and the user's associated company.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/testResults/{resultId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Parameter

| Parameter  | Type   | Required | Description                                |
| ---------- | ------ | -------- | ------------------------------------------ |
| `resultId` | `Long` | Yes      | The unique ID of the test result to fetch. |

***

### Response Body

The response will contain a `TestResultDTO` object if a test result is found for the specified ID and company associated with the authenticated user.

{\`{ "id": 102, "sessionId": "unique-session-id", "user": { "id": 34, "username": "testUser" }, "company": { "id": 56, "name": "TestCompany" }, "nodeLogPath": "/logs/testResult.log", "videoPath": "/videos/testResult.mp4", "status": "SUCCESS", "runtime": 78000, "start\_date": 1450890157000, "end\_date": 1450890235000 }\`}

| Field         | Type     | Description                                                     |
| ------------- | -------- | --------------------------------------------------------------- |
| `id`          | `Long`   | The unique ID of the test result.                               |
| `sessionId`   | `String` | The session identifier of the test result.                      |
| `user`        | `Object` | Information about the user who created the test result.         |
| `company`     | `Object` | Information about the company associated with this test result. |
| `nodeLogPath` | `String` | Path to the log file.                                           |
| `videoPath`   | `String` | Path to the video file.                                         |
| `status`      | `String` | The status of the test result (e.g., `SUCCESS`).                |
| `runtime`     | `Long`   | Execution time of the test in milliseconds.                     |
| `start_date`  | `Long`   | Start timestamp of the test execution.                          |
| `end_date`    | `Long`   | End timestamp of the test execution.                            |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `Invalid Request`       | The request was malformed or contained errors.   |
| `401`     | `Unauthorized`          | User authentication failed.                      |
| `403`     | `Access denied`         | User does not have access to this test result.   |
| `404`     | `Test Result Not Found` | No test result was found for the given ID.       |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/testResults/{resultId}" \
-H "Authorization: Bearer <your_access_token>"
```
