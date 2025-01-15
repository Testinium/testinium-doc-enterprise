# Rerun Test Plan

The endpoint allows the user to rerun specific scenarios from the last executed results of a test plan. The user must provide the test plan ID and a list of scenario IDs to rerun.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{planId}/rerun`
* **Method**: `POST`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter | Type   | Required | Description                                      |
| --------- | ------ | -------- | ------------------------------------------------ |
| `planId`  | `Long` | Yes      | The ID of the test plan to rerun scenarios from. |

***

### Request Body

The request body must contain a JSON array of scenario IDs to be rerun.

```json
[1, 2, 3]
```

| Field              | Type    | Description                                              |
| ------------------ | ------- | -------------------------------------------------------- |
| `scenariosToRerun` | `Array` | A list of scenario IDs to rerun from the last execution. |

***

### Response Body

Upon a successful request, the API returns a `RerunTestPlanResponse` object indicating the result of the rerun operation.

```json
{
  "successful": true,
  "message": "Scenarios rerun successfully."
}
```

| Field        | Type      | Description                                                           |
| ------------ | --------- | --------------------------------------------------------------------- |
| `successful` | `boolean` | Indicates whether the rerun operation was successful.                 |
| `message`    | `string`  | A message providing additional information about the rerun operation. |

***

### Error Codes

| HTTP Code | Error Message                    | Description                                              |
| --------- | -------------------------------- | -------------------------------------------------------- |
| `404`     | `User not found`                 | The specified user was not found.                        |
| `404`     | `Plan not found`                 | The specified test plan was not found.                   |
| `404`     | `Scenario list not found`        | The specified scenario list was not found.               |
| `404`     | `Company not found`              | The specified company for the user was not found.        |
| `404`     | `Execution not found`            | The last execution for the specified plan was not found. |
| `404`     | `Scenario not found`             | One of the specified scenarios was not found.            |
| `404`     | `Results plan not exists`        | The results for the specified plan do not exist.         |
| `404`     | `Results environment not exists` | The results for the specified environment do not exist.  |
| `500`     | `Internal Server Error`          | An unexpected error occurred on the server side.         |

***

### Example Request

```bash
curl -X POST "<custom-env-url>/Testinium.RestApi/api/plans/{planId}/rerun" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json" \
-d '[1, 2, 3]'
```
