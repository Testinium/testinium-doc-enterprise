# Create Plan Environment( Appium2)

### Endpoint Information

* **URL**: \<your-gateway-url>/devicepark/environment/plan/{planId}
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

### Request Body

```
[
  {
    "platform": "iOS",
    "manufacturer": "Apple",
    "model": "iPhone13,2",
    "platformVersion": "18.6.2",
    "marketName": "iPhone 12",
    "privateDevice": false
  }
]
```

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
            "testFrameworkType": null,
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

| HTTP Code | Error Message           | Description                                                                  |
| --------- | ----------------------- | ---------------------------------------------------------------------------- |
| 401       | `UNAUTHORIZED`          | The request lacks valid authentication credentials. Check your Bearer token. |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                             |

### Example Request

```
curl --location '<your-gateway-url>/devicepark/environment/plan/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json' \
--data '[
  {
    "platform": "iOS",
    "manufacturer": "Apple",
    "model": "iPhone13,2",
    "platformVersion": "18.6.2",
    "marketName": "iPhone 12",
    "privateDevice": false
  }
]'
```
