# Get Test Result by ID

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

```json
{
    "id": 102,
    "level": "ERROR",
    "start_date": 1720765136000,
    "end_date": 1720765136000,
    "runtime": 21,
    "session_id": "dummy-57996406855270899217",
    "message": "Test report could not be found. Please check your executor log.",
    "screen_shot_type": "YES",
    "video_enabled": false,
    "performance_data_enabled": false,
    "test_key": "TEST-C1-P5-E47-S6-ENV:WIN10-Chrome-LATEST",
    "test_scenario": {
        "id": 6
    },
    "test_plan": {
        "id": 5
    },
    "project": {
        "id": 5
    },
    "video_format": "FLV",
    "environment": {
        "id": 8
    },
    "test_execution": {
        "id": 47
    },
    "node_log_path": "https://dev.testinium.com//storage?key=1/2024/07/12/dummy-57996406855270899217/node.log",
    "executor_log_path": "https://dev.testinium.com//storage?key=1/2024/07/12/dummy-57996406855270899217/testResult.log"
}
```

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
curl --location 'custom-env-url>/Testinium.RestApi/api/testResults/{resultId}' \
--header 'Authorization: Bearer <your_access_token>'
```
