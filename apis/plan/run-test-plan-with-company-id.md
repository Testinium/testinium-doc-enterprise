# Run Test Plan with Company ID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Run Test Plan with Company ID

The endpoint triggers a test plan execution for a specific company. The user must provide the test plan ID and company ID in the path. It returns a `RunTestPlanResponse` object, indicating the success or failure of the operation.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/run/company/{companyId}`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required

***

### Path Variables

| Parameter   | Type   | Required | Description                                                |
| ----------- | ------ | -------- | ---------------------------------------------------------- |
| `id`        | `Long` | Yes      | The ID of the test plan to be executed.                    |
| `companyId` | `Long` | Yes      | The ID of the company for which the test plan is executed. |

***

### Response Body

Upon a successful request, the API returns a `RunTestPlanResponse` object with a boolean field `successful`.

{\`{ "successful": true }\`}

| Field        | Type      | Description                                                |
| ------------ | --------- | ---------------------------------------------------------- |
| `successful` | `boolean` | Indicates whether the test plan run was successful or not. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                             |
| --------- | ----------------------- | ------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.        |
| `403`     | `Forbidden`             | The user does not have permission to run the test plan. |
| `404`     | `Company not found`     | The specified company was not found.                    |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.        |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/plans/{id}/run/company/{companyId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
