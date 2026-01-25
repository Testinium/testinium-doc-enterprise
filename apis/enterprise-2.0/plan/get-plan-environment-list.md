# Get Plan Environment List

### Endpoint Information

* **URL**: \<your-gateway-url>/environment/plan/{planId}
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

### Response Body

```
{
    "data": [
        {
            "id": 753,
            "platform": "iOS",
            "platformName": null,
            "platformVersion": "18.6.2",
            "model": "iPhone13,2",
            "modelName": null,
            "manufacturer": "Apple",
            "marketName": "iPhone 12",
            "testFrameworkType": "APPIUM2",
            "udid": null,
            "licenceId": null,
            "enabled": null,
            "privateDevice": false
        }
    ],
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| Parameter         | Type     | Description                                                                                           |
| ----------------- | -------- | ----------------------------------------------------------------------------------------------------- |
| id                | Long     | Unique identifier of the device in the system.                                                        |
| platform          | `String` | Operating system of the device                                                                        |
| platformName      | `String` | Human-readable name of the operating system (e.g., “iOS”, “Android OS”).                              |
| platformVersion   | `String` | Version of the operating system running on the device.                                                |
| model             | `String` | Device model identifier assigned by the manufacturer (e.g., “iPhone13,2”, “SM-A305F”).                |
| modelName         |          |                                                                                                       |
| manufacturer      | `String` | Name of the device manufacturer (e.g., “Apple”, “Samsung”).                                           |
| marketName        | `String` | Commercial or user-friendly name of the device (e.g., “iPhone 12”, “Galaxy A30”).                     |
| testFrameworkType | `String` | The supported test automation framework for this device (e.g., “APPIUM”, “SELENIUM”).                 |
| udid              | `String` | Unique device identifier used by the debugging/test framework. _(Sensitive — mask in public docs.)_   |
| licenceId         | `String` | Identifier for the license associated with the device (if licensing is required).                     |
| enabled           | boolean  | Indicates whether the device is enabled and available for scheduling.                                 |
| privateDevice     | boolean  | Indicates whether the device is private to a specific company/user or part of the shared device pool. |

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

### Error Codes

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/environment/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
