# Check If Test Plan Is Running

#### `⚠️ This API will be available after 1.16.6 release.`

The endpoint allows users to check if a specific test plan is currently running. The user must provide the test plan ID to retrieve its running status.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/checkIsRunning`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter | Type     | Required | Description                             |
| --------- | -------- | -------- | --------------------------------------- |
| `id`      | `Object` | Yes      | The unique identifier of the test plan. |

***

### Response Body

Upon a successful request, the API returns a `CheckIsRunningResponse` object indicating whether the test plan is currently running.

```json
{
  "status": "SUCCESS",
  "running": true
}
```

| Field     | Type      | Description                                     |
| --------- | --------- | ----------------------------------------------- |
| `status`  | `String`  | The status of the request (`SUCCESS` or other). |
| `running` | `boolean` | Indicates whether the test plan is running.     |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `404`     | `Plan not found`        | The specified test plan was not found.           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{id}/checkIsRunning" \
-H "Authorization: Bearer <your_access_token>"
```
