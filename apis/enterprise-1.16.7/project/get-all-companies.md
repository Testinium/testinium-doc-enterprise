# Get All Companies

The endpoint retrieves a list of all companies. The user must have the `ROLE_ADMIN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/companies`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Response Body

The response contains a list of companies

```json
[
  {
    "id": 1,
    "company_name": "TESTINIUM",
    "short_name": "Testinium"
  },
  {
    "id": 2,
    "company_name": "Deneme",
    "short_name": "Company"
  },
  {
    "id": 3,
    "company_name": "KARTAL",
    "short_name": "KARTAL"
  },
  {
    "id": 4,
    "company_name": "yeni",
    "short_name": "yeni"
  },
  {
    "id": 5,
    "company_name": "senaeroglu",
    "short_name": "senaeroglu"
  },
  {
    "id": 6,
    "company_name": "dotnetTest",
    "short_name": "dotnetTest"
  },
  {
    "id": 7,
    "company_name": "dotnetWin2016",
    "short_name": "dotnetWin2016"
  }
]
```

### Response Fields

| Field          | Type     | Description                    |
| -------------- | -------- | ------------------------------ |
| `id`           | `Long`   | The unique ID of the company.  |
| `company_name` | `String` | The full name of the company.  |
| `short_name`   | `String` | The short name of the company. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `403`     | `ACCESS_DENIED`         | User lacks `ROLE_ADMIN` authority.               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/companies' \
--header 'Authorization: Bearer <your_access_token>'
```

2/2
