# Get Test Execution by ID and Company ID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Test Execution by ID and Company ID

The endpoint allows users to retrieve detailed information about a specific test execution by its ID and associated Company ID.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/testExecutions/{execId}/company/{companyId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter   | Type   | Required | Description                                                         |
| ----------- | ------ | -------- | ------------------------------------------------------------------- |
| `execId`    | `Long` | Yes      | The unique identifier of the test execution.                        |
| `companyId` | `Long` | Yes      | The unique identifier of the company associated with the execution. |

***

#### Response Body

Upon a successful request, the API returns a `TestExecutionDTO` object containing the details of the requested test execution.

```json
{
  "id": 3742,
  "plan": {
    "id": 227
  },
  "start_date": 1732797830000,
  "end_date": 1732797854000,
  "test_results": [
    {
      "id": 15227,
      "level": "FAILURE",
      "start_date": 1732797845000,
      "end_date": 1732797848000,
      "runtime": 3000,
      "session_id": "15879933334363832172",
      "message": "15:44:04.112 request: 1 > GET https://yesno.wtf/api 1 > Host: yesno.wtf 1 > Connection: Keep-Alive 1 > User-Agent: Apache-HttpClient/4.5.13 (Java/11.0.25) 1 > Accept-Encoding: gzip,deflate 15:44:04.752 response time in milliseconds: 593 1 < 200 1 < Content-Type: application/json; charset=utf-8 1 < Transfer-Encoding: chunked 1 < Connection: keep-alive 1 < Status: 200 OK 1 < Cache-Control: max-age=0, private, must-revalidate 1 < Access-Control-Allow-Origin: * 1 < X-XSS-Protection: 1; mode=block 1 < X-Request-Id: f0a3c0cf-f1fb-44bf-9e2c-9f5f9d2c74f3 1 < ETag: "370a7d197e34c7bedd782d73b01526b8" 1 < X-Frame-Options: SAMEORIGIN 1 < X-Runtime: 0.002104 1 < X-Content-Type-Options: nosniff 1 < Access-Control-Request-Method: * 1 < Date: Thu, 28 Nov 2024 11:34:25 GMT 1 < X-Powered-By: Phusion Passenger 6.0.4 1 < Server: nginx/1.17.3 + Phusion Passenger 6.0.4 {"image":"https://yesno.wtf/assets/no/17-829284e9dd894ce9fb65fbe86d2e382c.gif","answer":"no","forced":false} 15:44:04.773 retry condition not satisfied: response.answer == 'yes1' 15:44:04.774 sleeping before retry #1 15:44:05.776 request: 2 > GET https://yesno.wtf/api 2 > Host: yesno.wtf 2 > Connection: Keep-Alive 2 > User-Agent: Apache-HttpClient/4.5.13 (Java/11.0.25) 2 > Accept-Encoding: gzip,deflate 15:44:05.913 response time in milliseconds: 136 2 < 200 2 < Content-Type: application/json; charset=utf-8 2 < Transfer-Encoding: chunked 2 < Connection: keep-alive 2 < Status: 200 OK 2 < Cache-Control: max-age=0, private, must-revalidate 2 < Access-Control-Allow-Origin: * 2 < X-XSS-Protection: 1; mode=block 2 < X-Request-Id: b168a91c-552f-4759-95f2-729c2bd01223 2 < ETag: "8946c2cbd4f744b0abf9b8ae654a182c" 2 < X-Frame-Options: SAMEORIGIN 2 < X-Runtime: 0.002276 2 < X-Content-Type-Options: nosniff 2 < Access-Control-Request-Method: * 2 < Date: Thu, 28 Nov 2024 11:34:26 GMT 2 < X-Powered-By: Phusion Passenger 6.0.4 2 < Server: nginx/1.17.3 + Phusion Passenger 6.0.4 {"image":"https://yesno.wtf/assets/yes/5-64c2804cc480",
      "screen_shot_type": "NO",
      "video_enabled": false,
      "performance_data_enabled": false,
      "test_key": "TEST-C2-P227-E3742-S3018",
      "test_scenario": {
        "id": 3018
      },
      "test_plan": {
        "id": 227
      },
      "project": {
        "id": 761
      },
      "video_format": "FLV",
      "test_execution": {
        "id": 3742
      },
      "node_log_path": "https://dev.testinium.com//storage?key=2/2024/11/28/15879933334363832172/node.log",
      "executor_log_path": "https://dev.testinium.com//storage?key=2/2024/11/28/15879933334363832172/testResult.log"
    }
  ],
  "result_summary": {
    "FAILURE": 1
  },
  "test_result_status_counts": "[FAILURE, 1]"
}
```

| Field                      | Type      | Description                                           |
| -------------------------- | --------- | ----------------------------------------------------- |
| `id`                       | `Long`    | The unique ID of the test execution.                  |
| `level`                    | `String`  | The status of the test execution (e.g., `FAILURE`).   |
| `start_date`               | `Long`    | Start time of the test execution in epoch format.     |
| `end_date`                 | `Long`    | End time of the test execution in epoch format.       |
| `runtime`                  | `int`     | Total runtime in milliseconds.                        |
| `session_id`               | `String`  | Unique session identifier for this execution.         |
| `message`                  | `String`  | Execution message detailing any errors or warnings.   |
| `video_enabled`            | `Boolean` | Indicates if video recording was enabled.             |
| `performance_data_enabled` | `Boolean` | Indicates if performance data collection was enabled. |
| `test_scenario.id`         | `Long`    | The ID of the associated test scenario.               |
| `test_plan.id`             | `Long`    | The ID of the associated test plan.                   |
| `project.id`               | `Long`    | The ID of the project related to the execution.       |
| `video_format`             | `String`  | The format of the recorded video, if available.       |
| `environment.id`           | `Long`    | The ID of the environment used in this execution.     |
| `test_execution.id`        | `Long`    | Reference ID of the test execution.                   |
| `node_log_path`            | `String`  | URL to the node log file for the execution.           |
| `executor_log_path`        | `String`  | URL to the test result log file for the execution.    |

***

### Error Codes

| HTTP Code | Error Message              | Description                                       |
| --------- | -------------------------- | ------------------------------------------------- |
| `404`     | `Test Execution not found` | The specified test execution was not found.       |
| `403`     | `Access denied`            | User is not authorized for the requested company. |
| `500`     | `Internal Server Error`    | An unexpected error occurred on the server side.  |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/testExecutions/{execId}/company/{companyId}" \
-H "Authorization: Bearer <your_access_token>"
```
