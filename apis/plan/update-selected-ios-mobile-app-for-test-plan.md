# Update Selected iOS Mobile App for Test Plan

The endpoint allows users to update the selected iOS mobile app for a specific test plan. The user must provide the test plan ID and the mobile app ID to be set.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/plans/{id}/setIosMobileApp/{mobileAppId}`
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

Upon a successful request, the API returns the updated `PlanDTO` object representing the test plan with the selected iOS mobile app.

```json
{
  "id": 123,
  "plan_name": "Sample Test Plan",
  "selectedIosMobileApp": {
    "id": 456,
    "mobileAppName": "Sample iOS App"
  }
}
```

| Field                  | Type        | Description                                        |
| ---------------------- | ----------- | -------------------------------------------------- |
| `id`                   | `Long`      | The unique identifier of the test plan.            |
| `plan_name`            | `String`    | The name of the test plan.                         |
| `selectedIosMobileApp` | `MobileApp` | The mobile app that is selected for the test plan. |

***

### Error Codes

| HTTP Code | Error Message                           | Description                                                          |
| --------- | --------------------------------------- | -------------------------------------------------------------------- |
| `404`     | `Mobile app not found`                  | The specified mobile app was not found.                              |
| `404`     | `Plan not found`                        | The specified test plan was not found.                               |
| `400`     | `Mobile app not iOS`                    | The specified mobile app is not an iOS app.                          |
| `400`     | `Mobile app does not belong to project` | The specified mobile app does not belong to the test plan's project. |
| `500`     | `Internal Server Error`                 | An unexpected error occurred on the server side.                     |

***

### Example Request

```bash
curl -X PUT "<custom-env-url>/Testinium.RestApi/api/plans/{id}/setIosMobileApp/{mobileAppId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Content-Type: application/json"
```
