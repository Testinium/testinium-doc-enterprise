# Get Plan Environment List

### Endpoint Information

* **URL**: \<your-gateway-url>/environment/plan/{planId}
* **Method**: `POST`
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

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/environment/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
