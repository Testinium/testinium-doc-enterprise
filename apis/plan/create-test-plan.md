# Create Test Plan

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Create Test Plan

The endpoint creates a new test plan for a specific project. The user must provide project details and plan specifications in the request body. The API validates the input and returns the created plan as a ProjectDTO object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter         | Type     | Required | Description                                                  |
| ----------------- | -------- | -------- | ------------------------------------------------------------ |
| `projectNameOrId` | `Object` | Yes      | The name or ID of the project for which the plan is created. |

***

### Request Body Table

The JSON format request data that needs to be sent for creating a test plan is as follows:

{\`{ "type": "SELENIUM", "planName": "Test Plan", "projectId": 123, "companyId": 456, "description": "Plan description", "enabled": true, "planParallelTestLimit": 10, "scenarios": \[1, 2, 3], "period": { "periodType": "REPETITIVE", "repeatPeriod": 2 }, "alerts": \[ { "alertId": 789 } ], "alertsEnabled": true, "failedTestRetryCount": 3 }\`}

| Parameter               | Type            | Required | Description                                                               |
| ----------------------- | --------------- | -------- | ------------------------------------------------------------------------- |
| `type`                  | `string`        | Yes      | The type of the plan (TestFramework: SELENIUM, APPIUM, SERVICE, SOAPUI)   |
| `planName`              | `string`        | Yes      | The name of the plan                                                      |
| `projectId`             | `long`          | Yes      | The ID of the project                                                     |
| `companyId`             | `long`          | Yes      | The ID of the company                                                     |
| `description`           | `string`        | No       | A description of the plan                                                 |
| `enabled`               | `boolean`       | Yes      | Indicates if the plan is enabled                                          |
| `planParallelTestLimit` | `integer`       | No       | The maximum number of parallel tests                                      |
| `scenarios`             | `array[long]`   | No       | A list of scenario IDs to associate with the plan                         |
| `period`                | `object`        | No       | The test period details (contains `periodType` and `repeatPeriod` fields) |
| `alerts`                | `array[object]` | No       | A list of alerts associated with the plan (contains `alertId` field)      |
| `alertsEnabled`         | `boolean`       | No       | Indicates if alerts are enabled                                           |
| `failedTestRetryCount`  | `integer`       | No       | The number of retries for failed tests                                    |

***

### Response Body Table

Upon a successful request, the API returns the following JSON structure:

{\`{ "id": 1, "type": "SELENIUM", "projectId": 123, "companyId": 456, "planName": "Test Plan", "description": "Plan description", "enabled": true, "planParallelTestLimit": 10, "scenarios": \[1, 2, 3], "period": { "periodType": "REPETITIVE", "repeatPeriod": 2 }, "alerts": \[ { "alertId": 789 } ], "alertsEnabled": true, "failedTestRetryCount": 3, "lastExecution": null } \`}

| Parameter               | Type            | Description                                                               |
| ----------------------- | --------------- | ------------------------------------------------------------------------- |
| `id`                    | `long`          | The unique ID of the plan                                                 |
| `type`                  | `string`        | The type of the plan (TestFramework: SELENIUM, APPIUM, SERVICE, SOAPUI)   |
| `projectId`             | `long`          | The ID of the project                                                     |
| `companyId`             | `long`          | The ID of the company                                                     |
| `planName`              | `string`        | The name of the plan                                                      |
| `description`           | `string`        | A description of the plan                                                 |
| `enabled`               | `boolean`       | Indicates if the plan is enabled                                          |
| `planParallelTestLimit` | `integer`       | The maximum number of parallel tests                                      |
| `scenarios`             | `array[long]`   | A list of scenario IDs associated with the plan                           |
| `period`                | `object`        | The test period details (contains `periodType` and `repeatPeriod` fields) |
| `alerts`                | `array[object]` | A list of alerts associated with the plan (contains `alertId` field)      |
| `alertsEnabled`         | `boolean`       | Indicates if alerts are enabled                                           |
| `failedTestRetryCount`  | `integer`       | The number of retries for failed tests                                    |
| `lastExecution`         | `datetime/null` | The last execution timestamp (initially null)                             |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                         |
| --------- | ----------------------- | ------------------------------------------------------------------- |
| `400`     | `Invalid input data`    | There are missing or incorrect details in the request body.         |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.                    |
| `403`     | `Forbidden`             | The user does not have permission to create a plan for the project. |
| `404`     | `Project not found`     | The specified project was not found.                                |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.                    |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/projects/{projectNameOrId}/plans" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '{
  "name": "New Test Plan",
  "description": "Description of the new test plan",
  "period": {
    "period_type": "REPETITIVE",
    "repeatPeriod": 2
  }
}'
```
