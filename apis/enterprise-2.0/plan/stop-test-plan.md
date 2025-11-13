# Stop Test Plan

The endpoint stops a running test plan. The user must provide the test plan ID in the path. If the plan is not running, the response will indicate that the action is not available.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/stop`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter | Type     | Required | Description                            |
| --------- | -------- | -------- | -------------------------------------- |
| `id`      | `Object` | Yes      | The ID of the test plan to be stopped. |

***

### Response Body

Upon a successful request, the API returns a `StopTestPlanResponse` object. If the test plan is running, it stops the plan; otherwise, it returns a message indicating the plan is not running.

```json
{
  "status": "SUCCESS",
  "message": "Plan Id 123 has been stopped"
}
```

| Field     | Type     | Description                                                     |
| --------- | -------- | --------------------------------------------------------------- |
| `status`  | `string` | The status of the stop request (e.g., SUCCESS, NOT\_AVAILABLE). |
| `message` | `string` | A message indicating the result of the operation.               |

***

### Error Codes

| HTTP Code | Error Message           | Description                                              |
| --------- | ----------------------- | -------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.         |
| `403`     | `Forbidden`             | The user does not have permission to stop the test plan. |
| `404`     | `Test plan not found`   | The specified test plan was not found.                   |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.         |

***

### Example Request

```bash
curl -X GET '<custom-env-url>/Testinium.RestApi/api/plans/{id}/stop' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json'
```
