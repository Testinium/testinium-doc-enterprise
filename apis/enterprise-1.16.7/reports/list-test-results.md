# List Test Results

The endpoint retrieves a paginated list of test results for a specific test execution ID, starting from the first page (default page 1) for the authenticated user's company.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/testResults/executionId/{execId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Parameters

| Parameter | Type   | Required | Description                          |
| --------- | ------ | -------- | ------------------------------------ |
| `execId`  | `Long` | Yes      | The unique ID of the test execution. |

***

### Response Body

The response contains a `PaginatedTestResultList` object with details on pagination and a list of `TestResultDTO` objects for the requested page.

```json
{
    "pagination": {
        "current_page": 1,
        "total_count": 1,
        "page_limit": 50
    },
    "test_result_list": [
        {
            "id": 435,
            "level": "ERROR",
            "start_date": 1722511864000,
            "end_date": 1722511864000,
            "runtime": 42,
            "session_id": "dummy-38824800783936853956",
            "message": "Test report could not be found. Please check your executor log.",
            "screen_shot_type": "YES",
            "video_enabled": false,
            "performance_data_enabled": false,
            "test_key": "TEST-C1-P5-E102-S6-ENV:WIN10-Chrome-LATEST",
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
                "id": 102
            },
            "node_log_path": "https://dev.testinium.com//storage?key=1/2024/08/01/dummy-38824800783936853956/node.log",
            "executor_log_path": "https://dev.testinium.com//storage?key=1/2024/08/01/dummy-38824800783936853956/testResult.log"
        }
    ]
}
```

#### Pagination Object

| Field          | Type  | Description                                    |
| -------------- | ----- | ---------------------------------------------- |
| `current_page` | `int` | The current page number.                       |
| `total_count`  | `int` | Total count of items available for pagination. |
| `page_limit`   | `int` | Number of items displayed per page.            |

#### Test Result Object

| Field                      | Type      | Description                                            |
| -------------------------- | --------- | ------------------------------------------------------ |
| `id`                       | `Long`    | The unique ID of the test result.                      |
| `level`                    | `String`  | Status of the test result (e.g., `SUCCESS`).           |
| `start_date`               | `Long`    | Start timestamp of the test execution in milliseconds. |
| `end_date`                 | `Long`    | End timestamp of the test execution in milliseconds.   |
| `runtime`                  | `int`     | Execution time of the test in milliseconds.            |
| `session_id`               | `String`  | The session identifier of the test result.             |
| `video_enabled`            | `Boolean` | Indicates if video recording is enabled.               |
| `performance_data_enabled` | `Boolean` | Indicates if performance data is available.            |
| `test_scenario.id`         | `Long`    | ID of the test scenario.                               |
| `test_plan.id`             | `Long`    | ID of the test plan.                                   |
| `project.id`               | `Long`    | ID of the associated project.                          |
| `video_format`             | `String`  | Format of the video, if recorded (e.g., `FLV`).        |
| `test_execution.id`        | `Long`    | ID of the test execution associated with the result.   |
| `node_log_path`            | `String`  | URL path to the node log file.                         |
| `executor_log_path`        | `String`  | URL path to the executor log file.                     |

***

### Error Codes

| HTTP Code | Error Message              | Description                                       |
| --------- | -------------------------- | ------------------------------------------------- |
| `400`     | `Invalid Request`          | The request was malformed or contained errors.    |
| `401`     | `Unauthorized`             | User authentication failed.                       |
| `403`     | `Access Denied`            | User does not have access to this test execution. |
| `404`     | `Test Execution Not Found` | No test execution was found for the given ID.     |
| `500`     | `Internal Server Error`    | An unexpected error occurred on the server side.  |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/testResults/executionId/{execId}' \
--header 'Authorization: Bearer <your_access_token>'
```
