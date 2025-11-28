---
hidden: true
---

# Rerun Test Plan

The endpoint allows the user to rerun specific scenarios from the last executed results of a test plan. The user must provide the test plan ID and a list of scenario IDs to rerun.

***

### Endpoint Information

* **URL**: \<your-gateway-url>/queue
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
{
  "planId": 123,
  "userId": 45,
  "frameworkType": "APPIUM",
  "scenarioEnvironmentPairs": [
    {
      "scenarioId": 111,
      "environmentId": 222
    },
    {
      "scenarioId": 112,
      "environmentId": 223
    }
  ]
}
```

**Request Body Parameters**

| Field                      | Type          | Description                                                                                                                       |
| -------------------------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `planId`                   | Long          | The unique ID of the test plan to be executed. This field is required.                                                            |
| `userId`                   | Long          | The ID of the user who triggers the execution. Required for logging and authorization.                                            |
| `frameworkType`            | String        | The test framework type used for execution (e.g., GAUGE, JUNIT, TESTNG). Required.                                                |
| `scenarioEnvironmentPairs` | List\<Object> | A list of scenario–environment mapping objects. At least one item is required. Each object contains scenarioId and environmentId. |
| `scenarioId`               | Long          | The ID of a single scenario to be executed. Required when scenarioEnvironmentPairs is not used.                                   |
| `environmentId`            | Long          | The environment ID where the scenario will run. Optional; may be provided through the mapping list instead.                       |

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| 400       | INVALID\_REQUEST        | The request was malformed or contained errors.   |
| 500       | INTERNAL\_SERVER\_ERROR | An unexpected error occurred on the server side. |

### Application Error Codes

| Code   | Description                                          |
| ------ | ---------------------------------------------------- |
| `1000` | `"Plan not found!"`                                  |
| `1002` | `"User not found!"`                                  |
| `1006` | `"frameworkType is mandatory"`                       |
| `1006` | `"At least one scenarioEnvironmentPair is required"` |

### Example Request

```
curl --location '<your-gateway-url>/queue/rerun' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data '{
  "planId": 614,
  "userId": 13,
  "frameworkType": "APPIUM",
  "scenarioEnvironmentPairs": [
    {
      "scenarioId": 111,
      "environmentId": 222
     
    }
  ]
}'
```
