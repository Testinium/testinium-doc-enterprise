# Create Plan Scenarios (Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/{planId}/scenario
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "scenarioIds": [101, 204, 305]
}
```

| Parameter   | Type   | Required | Description                         |
| ----------- | ------ | -------- | ----------------------------------- |
| scenarioIds | `List` | Yes      | The unique ID of the test scenario. |

### Response

```
{
    "data": [
        {
            "id": 3224,
            "scenarioName": "GratisAndroid",
            "description": "",
            "projectId": 913,
            "parentId": null,
            "sourceFile": "Android/android.spec",
            "javaTestMethods": "@Deneme",
            "userId": 13,
            "orderNo": 1,
            "testRailCaseId": null,
            "xrayIssueKey": null,
            "subScenarios": []
        }
    ],
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/plan/{planId}/scenario' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data '
{
  "scenarioIds": [{scenariıoId}]
}'
```
