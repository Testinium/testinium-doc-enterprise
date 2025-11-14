# Stop Test Plan

The endpoint stops a running test plan. The user must provide the test plan ID in the path. If the plan is not running, the response will indicate that the action is not available.

***

### Endpoint Information

* **URL**: \<your-gateway-url>/stop/execution
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "plans": [614,615,312]
}
```

#### Request Body Parameters <a href="#request-body-parameters" id="request-body-parameters"></a>

| Field | Type        | Description                                                                                                 |
| ----- | ----------- | ----------------------------------------------------------------------------------------------------------- |
| plans | List\<Long> | A non-empty list of plan IDs to be processed. This field is required and must contain at least one plan ID. |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | <p>The request was malformed or contained errors.<br></p> |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.          |

### Application Error Codes
