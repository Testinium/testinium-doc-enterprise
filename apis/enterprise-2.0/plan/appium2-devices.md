# Appium2 Devices

### Endpoint Information

* **URL**: \<your-gateway-url>/devicepark/devices
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

#### Headers

| Header Name     | Required | Description                          |
| --------------- | -------- | ------------------------------------ |
| Authorization   | Yes      | Bearer token used for authentication |
| X-Company-Id    | Yes      | Your CompanyId                       |
| Accept-Language | No       | Your language(tr or en)              |
| content-type    | Yes      | application/json                     |

### Response Body

```
{
  "data": [
    {
      "id": 23,
      "serial": "***MASKED***",
      "marketName": "iPhone 12",
      "model": "***MASKED***",
      "manufacturer": "Apple",
      "platform": "iOS",
      "platformVersion": "18.x",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "IDLE",
      "isEnabled": true,
      "isAvailable": true
    },
    {
      "id": 25,
      "serial": "***MASKED***",
      "marketName": "Galaxy A30",
      "model": "***MASKED***",
      "manufacturer": "Samsung",
      "platform": "Android",
      "platformVersion": "9",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "SESSION_ACTIVE",
      "isEnabled": true,
      "isAvailable": false
    },
    {
      "id": 87,
      "serial": "***MASKED***",
      "marketName": "S21 FE 5G",
      "model": "***MASKED***",
      "manufacturer": "Samsung",
      "platform": "Android",
      "platformVersion": "14",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "SESSION_ACTIVE",
      "isEnabled": true,
      "isAvailable": false
    },
    {
      "id": 88,
      "serial": "***MASKED***",
      "marketName": "r0q",
      "model": "***MASKED***",
      "manufacturer": "Samsung",
      "platform": "Android",
      "platformVersion": "13",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "IDLE",
      "isEnabled": true,
      "isAvailable": true
    },
    {
      "id": 90,
      "serial": "***MASKED***",
      "marketName": "iPhone X",
      "model": "***MASKED***",
      "manufacturer": "Apple",
      "platform": "iOS",
      "platformVersion": "16.x",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "IDLE",
      "isEnabled": true,
      "isAvailable": true
    },
    {
      "id": 95,
      "serial": "***MASKED***",
      "marketName": "iPad Pro 12.9 inch 5th Gen",
      "model": "***MASKED***",
      "manufacturer": "Apple",
      "platform": "iOS",
      "platformVersion": "18.x",
      "hubIp": "***.***.***.***",
      "operationalState": "HEALTHY",
      "sessionState": "IDLE",
      "isEnabled": true,
      "isAvailable": true
    }
  ],
  "result": {
    "code": 0,
    "message": "success"
  }
}
```

| Parameter        | Type    | Description                                                                      |
| ---------------- | ------- | -------------------------------------------------------------------------------- |
| id               | long    | Unique identifier of the device in the system.                                   |
| serial           | string  | Device serial number or UDID identifying the physical device.                    |
| marketName       | string  | The commercial name of the device (e.g., “iPhone 12”, “Galaxy A30”).             |
| model            | string  | Hardware model identifier assigned by the manufacturer.                          |
| manufacturer     | string  | Device manufacturer (e.g., Apple, Samsung, Xiaomi).                              |
| platform         | string  | Device operating system (e.g., Android, iOS).                                    |
| platformVersion  | string  | Version of the operating system installed on the device.                         |
| hubIp            | string  | IP address of the device hub where the device is connected.                      |
| operationalState | string  | Current operational health of the device (e.g., HEALTHY, UNHEALTHY).             |
| sessionState     | string  | Current session status of the device                                             |
| isEnabled        | boolean | Indicates whether the device is enabled and allowed to be used.                  |
| isAvailable      | boolean | Indicates whether the device is currently free and available for test execution. |

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

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
--header 'X-Company-Id: <company_id>' \
--header 'content-type: application/json'
```
