# Update Selected Android Mobile App for Test Plan

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Update Selected Android Mobile App for Test Plan

The endpoint allows users to update the selected Android mobile app for a specific test plan. The user must provide the test plan ID and the mobile app ID to be set.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/setAndroidMobileApp/{mobileAppId}`
* **Method**: `PUT`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Path Variables

| Parameter     | Type   | Required | Description                                     |
| ------------- | ------ | -------- | ----------------------------------------------- |
| `id`          | `Long` | Yes      | The unique identifier of the test plan.         |
| `mobileAppId` | `Long` | Yes      | The unique identifier of the mobile app to set. |

***

### Response Body

Upon a successful request, the API returns the updated `PlanDTO` object representing the test plan with the selected Android mobile app.

{\`{ "id": 123, "name": "Sample Test Plan", "selectedAndroidMobileApp": { "id": 456, "mobileAppName": "Sample Android App" } }\`}

| Field                      | Type        | Description                                        |
| -------------------------- | ----------- | -------------------------------------------------- |
| `id`                       | `Long`      | The unique identifier of the test plan.            |
| `name`                     | `String`    | The name of the test plan.                         |
| `selectedAndroidMobileApp` | `MobileApp` | The mobile app that is selected for the test plan. |

***

### Error Codes

| HTTP Code | Error Message                           | Description                                                          |
| --------- | --------------------------------------- | -------------------------------------------------------------------- |
| `404`     | `Mobile app not found`                  | The specified mobile app was not found.                              |
| `404`     | `Plan not found`                        | The specified test plan was not found.                               |
| `400`     | `Mobile app not Android`                | The specified mobile app is not an Android app.                      |
| `400`     | `Mobile app does not belong to project` | The specified mobile app does not belong to the test plan's project. |
| `500`     | `Internal Server Error`                 | An unexpected error occurred on the server side.                     |

***

### Example Request

```bash
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/plans/{id}/setAndroidMobileApp/{mobileAppId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json"
```
