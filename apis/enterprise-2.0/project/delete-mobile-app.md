# Delete Mobile App

This endpoint is used to delete a mobile application from the database and storage. Below are the details related to the API usage.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/mobileapp/{mobileAppId}`
* **Method**: `DELETE`
* **Authentication**: `Bearer Token` is required
* **Authorization**: Yes

***

### Request

#### Path Parameters

| Parameter     | Type   | Required | Description                                       |
| ------------- | ------ | -------- | ------------------------------------------------- |
| `mobileAppId` | `long` | Yes      | The unique ID of the mobile application to delete |

***

### Response

On successful deletion, the API returns an HTTP status code:

| HTTP Code | Status                  | Description                                        |
| --------- | ----------------------- | -------------------------------------------------- |
| `200`     | `OK`                    | The mobile application was deleted successfully.   |
| `404`     | `Not Found`             | The specified mobile application ID was not found. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.        |

***

### Example Request

```bash
curl --location --request DELETE '<custom-env-url>/Testinium.RestApi/api/projects/mobileapp/{mobileAppId}' \
--header 'Authorization: Bearer <your_access_token>'
```
