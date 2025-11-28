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
            "scenarioName": "Deneme",
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

| Parameter       | Type   | Description                                                                                        |
| --------------- | ------ | -------------------------------------------------------------------------------------------------- |
| id              | Long   | Unique identifier of the test scenario.                                                            |
| scenarioName    | String | Name of the test scenario as displayed in the UI.                                                  |
| description     | String | Optional description or notes for the scenario.                                                    |
| projectId       | Long   | ID of the project this scenario belongs to.                                                        |
| parentId        | Long   | ID of the parent scenario when this scenario is part of a hierarchy; null for top-level scenarios. |
| sourceFile      | String | Path of the source file where the scenario is defined (e.g. spec/feature/test file).               |
| javaTestMethods | String | Name or annotation selector of the Java test method(s) associated with this scenario.              |
| userId          | Long   | ID of the user who created or last modified the scenario.                                          |
| orderNo         | Long   | Display or execution order of the scenario within the project/plan.                                |
| testRailCaseId  | String | External TestRail test case identifier mapped to this scenario, if configured.                     |
| xrayIssueKey    | String | External Xray/Jira issue key linked to this scenario, if configured.                               |
| subScenarios    | List   | List of child scenarios nested under this scenario.                                                |

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

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
