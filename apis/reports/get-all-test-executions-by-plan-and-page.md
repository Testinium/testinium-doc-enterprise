# Get All Test Executions by Plan and Page

The endpoint allows users to retrieve a paginated list of all test executions for a specific test plan.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/testExecutions/pages/{page}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter | Type   | Required | Description                                |
| --------- | ------ | -------- | ------------------------------------------ |
| `id`      | `Long` | Yes      | The unique identifier of the test plan.    |
| `page`    | `int`  | Yes      | The page number for the paginated results. |

***

### Response Body

Upon a successful request, the API returns a `PaginatedTestExecutionList` object containing the paginated list of test executions.

```json
{
  "pagination": {
    "current_page": 2,
    "total_count": 0,
    "page_limit": 50,
    "previous_page": "http://127.0.0.1:8080/Testinium.RestApi/api/plans/80/testExecutions/pages/1"
  },
  "execution_list": []
}
```

| Field            | Type               | Description                       |
| ---------------- | ------------------ | --------------------------------- |
| `pagination`     | `PaginationObject` | Contains pagination details.      |
| `execution_list` | `Array`            | A list of test execution details. |

#### PaginationObject

| Field           | Type     | Description                                  |
| --------------- | -------- | -------------------------------------------- |
| `current_page`  | `int`    | The current page number.                     |
| `total_count`   | `int`    | The total number of test executions.         |
| `page_limit`    | `int`    | The maximum number of results per page.      |
| `previous_page` | `String` | The URL for the previous page, if available. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `404`     | `Plan not found`        | The specified test plan was not found.           |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{id}/testExecutions/pages/{page}" \
-H "Authorization: Bearer <your_access_token>"
```
