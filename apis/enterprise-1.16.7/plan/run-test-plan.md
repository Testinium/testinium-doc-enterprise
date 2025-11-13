# Run Test Plan

The endpoint triggers the execution of a specific test plan for the authenticated user. It checks the availability of required environments before starting the test and allows tracking execution status via an optional callback URL.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/run`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter | Type     | Required | Description                             |
| --------- | -------- | -------- | --------------------------------------- |
| `id`      | `Object` | Yes      | The ID of the test plan to be executed. |

***

### Response Body

The API returns the result of the test plan execution in the `RunTestPlanResponse` object.

Service and WEB:

```json
{
  {
    "execution_id": 3742,
    "unavailable_env_list": [],
    "successful": true,
    "already_running": false
}
```

Appium:

```json
{
    "unavailable_env_list": [
        {
            "id": 15
        }
    ],
    "successful": false,
    "already_running": false
}
```



### Response Fields

| Field                  | Type      | Description                                                |
| ---------------------- | --------- | ---------------------------------------------------------- |
| `execution_id`         | `boolean` | Indicates if the test plan is already running.             |
| `successful`           | `boolean` | Indicates whether the test plan execution was successful.  |
| `unavailable_env_list` | `Array`   | List of unavailable environments needed for the test plan. |
| `already_running`      | `boolean` | Indicates if the test plan is already running.             |

***

### Error Codes

| HTTP Code | Error Message           | Description                                             |
| --------- | ----------------------- | ------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.        |
| `403`     | `Forbidden`             | The user does not have permission to run the test plan. |
| `404`     | `Test Plan not found`   | The specified test plan was not found.                  |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.        |

***

### Example Request

#### Using `curl`

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/plans/{id}/run' \
--header 'Authorization: Bearer <your_access_token>'
```
