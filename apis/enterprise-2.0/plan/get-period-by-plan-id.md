# Get Period By Plan Id

### Endpoint Information

* **URL**: \<your-gateway-url>/plan/period/{planId}
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

### Response Body

```
{
    "data": {
        "id": 628,
        "periodType": "MANUAL",
        "startDate": null,
        "endDate": null,
        "onceDate": null,
        "daysOfWeek": "2,3,4,5,6,7,1",
        "repeatPeriod": 60
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

| Parameter      | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in. |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side. |

### Example Request

```
curl --location '<your-gateway-url>/plan/period/{planId}' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>' \
--header 'X-Company-Id: <company_id>' \
--header 'content-type: application/json'
```
