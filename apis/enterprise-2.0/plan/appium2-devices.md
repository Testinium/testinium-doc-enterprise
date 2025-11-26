# Appium2 Devices

### Endpoint Information

* **URL**: \<your-gateway-url>/devicepark/devices
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

#### Error Codes <a href="#error-codes" id="error-codes"></a>

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/devicepark/devices' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'content-type: application/json'
```
