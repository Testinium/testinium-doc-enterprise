# Get Plan By ID

import CodeBlock from '@theme/CodeBlock';

## Get Plan By ID

The endpoint retrieves a test plan based on the plan's name or ID. The test plan is returned as a `PlanDTO` object.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{planNameOrId}`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`

***

### Path Variables

| Parameter      | Type     | Required | Description                      |
| -------------- | -------- | -------- | -------------------------------- |
| `planNameOrId` | `Object` | Yes      | The name or ID of the test plan. |

***

### Response Body

Upon a successful request, the API returns the test plan in JSON format.

{\`{ "id": 29, "project\_id": 20, "company\_id": 8, "plan\_name": "Grup Bilgi Güncelleme", "group\_plan": false, "description": "", "enabled": true, "plan\_parallel\_test\_limit": 0, "scenarios": \[ 124 ], "period": { "period\_type": "ONCE", "once\_date": 1420616640000, "days\_of\_week": "", "repeat\_period": 60 }, "alerts": \[], "alerts\_enabled": true, "video\_enabled": false, "environments": \[ { "id": 74 } ], "clear\_app\_data": false, "fetch\_app\_files": \[] }\`}

| Field             | Type      | Description                                      |
| ----------------- | --------- | ------------------------------------------------ |
| `id`              | `integer` | The unique ID of the test plan.                  |
| `plan_name`       | `string`  | The name of the test plan.                       |
| `description`     | `string`  | A brief description of the test plan.            |
| `project_id`      | `integer` | The ID of the associated project.                |
| `company_id`      | `integer` | The ID of the associated company.                |
| `enabled`         | `boolean` | Whether the plan is enabled or not.              |
| `scenarios`       | `array`   | A list of scenario IDs associated with the plan. |
| `period`          | `object`  | The period configuration for the plan.           |
| `alerts`          | `array`   | A list of alerts associated with the plan.       |
| `video_enabled`   | `boolean` | Whether video recording is enabled for the plan. |
| `environments`    | `array`   | A list of environments related to the plan.      |
| `clear_app_data`  | `boolean` | Whether app data should be cleared.              |
| `fetch_app_files` | `array`   | A list of files to be fetched for the plan.      |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. User is not logged in.                |
| `403`     | `Forbidden`             | User does not have permission to access the specified plan. |
| `404`     | `Plan not found`        | The specified plan was not found.                           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.                 |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{planNameOrId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
