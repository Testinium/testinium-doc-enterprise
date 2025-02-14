# Get All Projects

The endpoint retrieves all projects associated with the company of the authenticated user. It returns a list of projects in JSON format with detailed information about each project.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/`
* **Method**: `GET`
* **Authentication**: `Bearer Token` is required
* **Content-Type**: `application/json`

***

### Request Headers

| Header          | Value                   | Description                                   |
| --------------- | ----------------------- | --------------------------------------------- |
| `Authorization` | `Bearer {access_token}` | The access token obtained after login.        |
| `Accept`        | `application/json`      | The type of content expected in the response. |

***

### Response Body

Upon a successful request, the API returns the following JSON structure:

```json
[
  {
    "id": 77,
    "project_name": "AppiumJava",
    "description": "",
    "enabled": true,
    "repository_path": "appiumjava",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_JAVA",
    "test_runner_tool": "MAVEN",
    "mobile_apps": [
      {
        "id": 58,
        "mobile_app_name": "Gratis-68c16a02-8181239309953606241.ipa",
        "mobile_app_hash": "046696ec4d2e7443f348fee4b49b4a2c",
        "operating_system": "IOS",
        "mobile_app_metadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.3.0\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\"}",
        "created_at": "2024-11-28 10:59:00"
      },
      {
        "id": 57,
        "mobile_app_name": "3.2.39__130_-83f575df-b7266d12-ae6c7c43-401562538376308185.apk",
        "mobile_app_hash": "177f1b975b8f99e8006dd8bf88686f6e",
        "operating_system": "ANDROID",
        "mobile_app_metadata": "{\"packageName\":\"com.gratis.android\",\"label\":\"Gratis\",\"icon\":\"res/d2.webp\",\"versionName\":\"3.2.39\",\"versionCode\":130,\"minSdkVersion\":\"24\",\"targetSdkVersion\":\"34\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
        "created_at": "2024-11-28 10:58:07"
      }
    ]
  },
  {
    "id": 89,
    "project_name": "project1",
    "description": "",
    "enabled": true,
    "repository_path": "",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_JAVA",
    "test_runner_tool": "MAVEN"
  },
  {
    "id": 90,
    "project_name": "KarateService",
    "description": "",
    "enabled": true,
    "repository_path": "karateservice",
    "test_framework": "SERVICE",
    "test_file_type": "SERVICE_KARATE",
    "test_runner_tool": "MAVEN",
    "mobile_apps": []
  },
  {
    "id": 91,
    "project_name": "otomasyon",
    "description": "",
    "enabled": true,
    "repository_path": "otomasyon",
    "test_framework": "SELENIUM",
    "test_file_type": "SELENIUM_GAUGE",
    "test_runner_tool": "MAVEN",
    "mobile_apps": []
  }
]

```

| Field              | Type      | Description                                                              |
| ------------------ | --------- | ------------------------------------------------------------------------ |
| `id`               | `integer` | The unique ID of the project.                                            |
| `project_name`     | `string`  | The name of the project.                                                 |
| `description`      | `string`  | A brief description of the project.                                      |
| `enabled`          | `boolean` | Indicates whether the project is active or not.                          |
| `repository_path`  | `string`  | The path to the project's repository.                                    |
| `test_framework`   | `string`  | The testing framework used (e.g., APPIUM).                               |
| `test_file_type`   | `string`  | The type of test files associated with the project (e.g., APPIUM\_JAVA). |
| `test_runner_tool` | `string`  | The tool used to run the tests (e.g., MAVEN).                            |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message  | Description                                               |
| --------- | -------------- | --------------------------------------------------------- |
| `204`     | `No Content`   | No projects are available for the user's company.         |
| `401`     | `Unauthorized` | Authorization failed. The user is not logged in.          |
| `403`     | `Forbidden`    | The user does not have permission to access the projects. |

***

### Example Request

```bash
curl -X GET "<custom-env-url>/Testinium.RestApi/api/projects/" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"
```
