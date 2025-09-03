# Rerun Test Plan(v2.0)

The endpoint allows the user to rerun specific scenarios from the last executed results of a test plan.

### Endpoint Information

* **URL**: [https://{gateway-url}/queue/rerun](https://{gateway-url}/queue/rerun)
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "planId": 681,
  "userId": 1,
  "scenarioEnvironmentPairs": [
    {
      "scenarioId": 1001,
      "environmentId": 2001
    }
  ]
}
```

#### Request Body Parameters <a href="#request-body-parameters" id="request-body-parameters"></a>

| Parameter     | Type   | Required | Description                                |
| ------------- | ------ | -------- | ------------------------------------------ |
| `planId`      | `Long` | Yes      | The unique ID of the test plan to execute. |
| userId        | `Long` | Yes      | The unique ID of the user who runs plan.   |
| scenarioId    | `Long` | No       |                                            |
| environmentId | `Long` | No       |                                            |

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

**Response Fields**

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Application Error Codes

| Code    |                                                           |
| ------- | --------------------------------------------------------- |
| `1000`  | `Full authentication is required to access this resource` |
| `10000` | `Plan with id {planId} not found!`                        |
| `10002` | `User with id {userId} not found!`                        |

#### Example Request <a href="#example-request" id="example-request"></a>

```
curl --location '{gateway-url}/queue/rerun' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer <your_access_token>\
--data '{
  "planId": {planId},
  "userId": {userId},
  "scenarioEnvironmentPairs": [
    {
      "scenarioId": {scenarioId},
      "environmentId": {environmentId}
    }
  ]
}'
```
