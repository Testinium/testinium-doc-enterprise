# List Test Results by Execution ID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## List Test Results by Execution ID

The endpoint retrieves a paginated list of test results for a specific test execution ID, limited to results accessible by the authenticated user's company.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/testResults/executionId/{execId}/pages/{page}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Parameters

| Parameter | Type   | Required | Description                            |
| --------- | ------ | -------- | -------------------------------------- |
| `execId`  | `Long` | Yes      | The unique ID of the test execution.   |
| `page`    | `int`  | Yes      | The page number for paginated results. |

***

### Response Body

The response contains a `PaginatedTestResultList` object with details on pagination and a list of `TestResultDTO` objects for the requested page.

{\`{ "pagination": { "current\_page": 1, "total\_count": 1, "page\_limit": 50 }, "test\_result\_list": \[ { "id": 150912, "level": "SUCCESS", "start\_date": 1428833706000, "end\_date": 1428833706000, "runtime": 0, "session\_id": "dummy-47359440135365756567", "video\_enabled": false, "performance\_data\_enabled": false, "test\_scenario": { "id": 152 }, "test\_plan": { "id": 35 }, "project": { "id": 28 }, "video\_format": "FLV", "test\_execution": { "id": 8786 }, "node\_log\_path": "http://127.0.0.1:8080//storage?key=1/2015/04/12/dummy-47359440135365756567/node.log", "executor\_log\_path": "http://127.0.0.1:8080//storage?key=1/2015/04/12/dummy-47359440135365756567/testResult.log" } ] }\`}

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
curl -X GET "<custom-env-url>/Testinium.RestApi/api/testResults/executionId/{execId}/pages/{page}" \
-H "Authorization: Bearer <your_access_token>"
```
