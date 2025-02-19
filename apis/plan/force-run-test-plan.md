---
hidden: true
---

# Force Run Test Plan

The endpoint is used to run a specific test plan. It provides options to forcefully run the plan or to check for environment availability and other preconditions before starting the execution.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/run/{forceRun}`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter  | Type      | Required | Description                                                  |
| ---------- | --------- | -------- | ------------------------------------------------------------ |
| `id`       | `Object`  | Yes      | The ID of the test plan to be executed.                      |
| `forceRun` | `Boolean` | Yes      | Indicates whether to force the execution or not.(true/false) |

***

### Query Parameters

| Parameter     | Type     | Required | Description                                             |
| ------------- | -------- | -------- | ------------------------------------------------------- |
| `callbackUrl` | `String` | No       | The URL to be called back when the execution completes. |

***

### Response Body

Upon successful request, the API returns a `RunTestPlanResponse` object that includes information about the status of the execution.

```json
{
  "unavailable_env_list": [
    {
      "id": 74
    }
  ],
  "already_running": false,
  "successful": false
}
```

#### Response Fields

| Field                  | Type      | Description                                                |
| ---------------------- | --------- | ---------------------------------------------------------- |
| `successful`           | `boolean` | Indicates whether the test plan execution was successful.  |
| `id`                   | `string`  | The ID of the environment started for the test plan.       |
| `unavailable_env_list` | `Array`   | List of unavailable environments needed for the test plan. |
| `already_running`      | `boolean` | Indicates if the test plan is already running.             |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message                  | Description                                                  |
| --------- | ------------------------------ | ------------------------------------------------------------ |
| `401`     | `Unauthorized`                 | Authorization failed. The user is not logged in.             |
| `403`     | `Forbidden`                    | The user does not have permission to execute this test plan. |
| `404`     | `Plan not found`               | The specified test plan was not found.                       |
| `409`     | `Test plan is already running` | The test plan is already being executed.                     |
| `500`     | `Internal Server Error`        | An unexpected error occurred on the server side.             |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{id}/run/{forceRun}" \
--header 'Authorization: Bearer <your_access_token>' \
-H "Accept: application/json"
```
