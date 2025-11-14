# Run Test Plan

The endpoint starts the execution of a specific test plan. The user must have the `PLAN_RUN` authority to access this endpoint.

### Endpoint Information

* **URL**: \<your-gateway-url>[/queue](https://gateway.testinium.io/queue)
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "planId": 12345,
  "userId": 67890
}
```

#### Request Body Parameters <a href="#request-body-parameters" id="request-body-parameters"></a>

| Field          | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Application Error Codes

|        |                     |
| ------ | ------------------- |
| `1000` | `"Plan not found!"` |
| `1002` | `"User not found!"` |

### Example Request

```
curl '<your-gateway-url>/queue' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'authorization: Bearer <your_access_token>' \
  -H 'content-type: application/json' \
  --data-raw '{"planId":<plan_id>,"userId":<user_id>}'
```
