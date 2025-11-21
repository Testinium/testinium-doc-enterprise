# Get All Plans

The endpoint retrieves all test plans associated with the user's company. The response contains a list of test plans.

***

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***



### Response Body

Upon a successful request, the API returns a list of `PlanDTO` objects representing the test plans.

```json
{
    "data": {
        "id": 614,
        "planName": "Notification",
        "groupPlan": false,
        "description": "",
        "enabled": true,
        "deleted": false,
        "planParallelTestLimit": 30,
        "periodId": 618,
        "projectId": 953,
        "projectName": "ServiceJava",
        "projectTestFramework": "SERVICE",
        "userId": 13,
        "companyId": 11,
        "failedTestRetryCount": 0,
        "videoEnabled": false,
        "clearAppData": false,
        "testFileType": "SERVICE_JAVA",
        "testRunnerTool": "MAVEN",
        "testDispatchMethodType": "ONE_BY_ONE",
        "alertsEnabled": true,
        "gridType": "TESTINIUM_ENTERPRISE"
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| Field                  | Type      |
| ---------------------- | --------- |
| `id`                   | `integer` |
| planName               | `string`  |
| groupPlan              | `boolean` |
| `plan_name`            | `string`  |
| enabled                | `boolean` |
| deleted                | `boolean` |
| planParallelTestLimit  | `integer` |
| periodId               | `integer` |
| projectId              | `integer` |
| projectName            | `string`  |
| projectTestFramework   | `string`  |
| userId                 | `integer` |
| companyId              | `integer` |
| failedTestRetryCount   | `integer` |
| videoEnabled           | `boolean` |
| clearAppData           | `boolean` |
| testFileType           | `string`  |
| testRunnerTool         | `string`  |
| testDispatchMethodType | `string`  |
| alertsEnabled          | `boolean` |
| gridType               | `string`  |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
 curl  '<your-gateway-url>/plan/{planId}' \' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
