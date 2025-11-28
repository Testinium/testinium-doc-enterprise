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

#### Response Body <a href="#error-codes" id="error-codes"></a>

```
{
    "data": null,
    "errors": null
}
```

| Parameter | Type   | Description                                                                       |
| --------- | ------ | --------------------------------------------------------------------------------- |
| data      | Object | The payload of the response. In this case `null` since no extra data is returned. |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/stop/execution' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer *****' \
--data '{
  "plans": [613]
}'
```
