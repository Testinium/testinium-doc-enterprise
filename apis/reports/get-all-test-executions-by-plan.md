# Get All Test Executions by Plan

The endpoint allows users to retrieve all test executions for a specific test plan. The results are returned as a paginated list, starting from the first page.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/testExecutions`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter | Type   | Required | Description                             |
| --------- | ------ | -------- | --------------------------------------- |
| `id`      | `Long` | Yes      | The unique identifier of the test plan. |

***

### Response Body

Upon a successful request, the API returns a paginated list of test executions in the form of a `PaginatedTestExecutionList` object.

```json
{
  "pagination": {
    "current_page": 1,
    "total_count": 0,
    "page_limit": 50
  },
  "execution_list": []
}
```

| Field            | Type     | Description                                            |
| ---------------- | -------- | ------------------------------------------------------ |
| `pagination`     | `Object` | Contains pagination details.                           |
| `current_page`   | `int`    | The current page number.                               |
| `total_count`    | `int`    | The total number of test executions.                   |
| `page_limit`     | `int`    | The maximum number of results per page.                |
| `execution_list` | `Array`  | A list of test execution details (empty in this case). |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `404`     | `Plan not found`        | The specified test plan was not found.           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{id}/testExecutions" \
-H "Authorization: Bearer <your_access_token>"
```
