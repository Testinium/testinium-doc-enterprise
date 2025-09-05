---
hidden: true
---

# Profile

### Endpoint Information

* **URL**: [https://{gateway-url}/queue/user/profile](https://{gateway-url}/queue/user/profile)
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)



### Response

This response indicates that the operation was completed successfully, with no additional data returned.

```
{
    "id": 1,
    "name": null,
    "surname": null,
    "username": "demo",
    "email": "demo.testinium.com",
    "enabled": true,
    "accessToken": "demoToken",
    "timeZone": "Europe/Istanbul",
    "companyId": 1,
    "language": "ENGLISH",
    "userRoles": [
        {
            "id": 4,
            "name": "ROLE_RUN_TEST"
        },
        {
            "id": 1,
            "name": "ROLE_ADMIN"
        },
        {
            "id": 3,
            "name": "ROLE_COMPANY_ADMIN"
        },
        {
            "id": 2,
            "name": "ROLE_USER"
        },
        {
            "id": 5,
            "name": "ROLE_CHANGE_USER"
        }
    ]
}
```

#### Response Fields

| Parameter   | Type    |                                                                                                                          |
| ----------- | ------- | ------------------------------------------------------------------------------------------------------------------------ |
| id          | Long    | Unique identifier of the user (auto-generated number).                                                                   |
| name        | String  | User’s first name (nullable).                                                                                            |
| surname     | String  | User’s last name (nullable).                                                                                             |
| username    | String  | Username used for login.                                                                                                 |
| email       | String  | User’s email address.                                                                                                    |
| enabled     | Boolean | Indicates if the user account is active (true/false).                                                                    |
| accessToken | String  | Access token assigned when the user logs in.                                                                             |
| timeZone    | String  | User’s time zone (e.g., _Europe/Istanbul_).                                                                              |
| companyId   | Long    | Identifier of the company the user belongs to.                                                                           |
| language    | Object  | Preferred language of the user (e.g., _ENGLISH_).                                                                        |
| userRoles   | Object  | List of roles assigned to the user. Each role contains: • id: Role ID • name: Role name (e.g., ROLE\_ADMIN, ROLE\_USER). |

### Error Codes

| HTTP Code | Error Message                                             |
| --------- | --------------------------------------------------------- |
| `1000`    | `Full authentication is required to access this resource` |

### Example Request

```
curl --location 'http://127.0.0.1:8090/user/profile' \
--header 'Authorization: Bearer <your_access_token>\
```
