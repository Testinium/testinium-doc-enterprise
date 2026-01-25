# Run Test Plan

### Endpoint Information

* **URL**:\<your-gateway-url>/queue
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "planId": 681,
  "userId": 1
}
```

### Request Body Parameters

| Parameter | Type   | Required | Description                                |
| --------- | ------ | -------- | ------------------------------------------ |
| `planId`  | `Long` | Yes      | The unique ID of the test plan to execute. |
| userId    | `Long` | Yes      | The unique ID of the user who runs plan.   |

### Response

This response indicates that the operation was completed successfully, with no additional data returned.

```
{
    "data": null,
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

#### Response Fields

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

### Error Codes

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Application Error Codes

| Code    | Error Message                                             |
| ------- | --------------------------------------------------------- |
| `1000`  | `Full authentication is required to access this resource` |
| `10000` | `Plan with id {planId} not found!`                        |
| `10002` | `User with id {userId} not found!`                        |

### Example Request

<pre><code>curl --location '{gateway-url}/queue' \
<strong>--header 'Content-Type: application/json' \
</strong>--header 'Authorization: Bearer &#x3C;your_access_token>\
--data '{"planId":&#x3C;plan_id>,"userId":&#x3C;user_id>}'
</code></pre>
