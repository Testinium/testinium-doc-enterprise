# Get Scenarios by User Company

The endpoint retrieves all test scenarios associated with the authenticated user's companies. It returns a list of `ScenarioDTO` objects.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/scenarios`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Response Body

Upon a successful request, the API returns a list of test scenarios in JSON format.

```json
    {
        "id": 29,
        "scenario_name": "Scenario1",
        "description": "",
        "enabled": true,
        "execute_mode": "AUTOMATED"
    }
```

| Field           | Type      | Description                                             |
| --------------- | --------- | ------------------------------------------------------- |
| `id`            | `integer` | The unique ID of the test scenario                      |
| `scenario_name` | `string`  | The name of the test scenario                           |
| `description`   | `string`  | A brief description of the test scenario                |
| `enabled`       | `boolean` | Indicates if the scenario is active                     |
| `execute_mode`  | `string`  | Defines whether the scenario is `AUTOMATED` or `MANUAL` |
| `createdBy`     | `string`  | The user who created the scenario                       |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.           |
| `403`     | `Forbidden`             | The user does not have permission to access the scenarios. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/scenarios" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
