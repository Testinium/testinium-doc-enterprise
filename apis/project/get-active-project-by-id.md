# Get Active Project By ID

The endpoint retrieves the active project by its ID. It ensures that the project belongs to a company accessible to the user.

***

### Endpoint Information

* **URL**: `<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/active`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`

***

### Path Parameters

| Parameter   | Type   | Required | Description                            |
| ----------- | ------ | -------- | -------------------------------------- |
| `projectId` | `Long` | Yes      | The ID of the project to be retrieved. |

***

### Response Body

Upon a successful request, the API returns a `ProjectDTO` object containing details of the active project.

Appium Project:

```json
{
    "id": 580,
    "project_name": "APPFile",
    "description": "",
    "enabled": true,
    "repository_path": "appfile",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_GAUGE",
    "test_runner_tool": "MAVEN",
    "mobile_apps": [
        {
            "id": 54,
            "mobile_app_name": "pegasus-pilot-release-2.39.0.38__2_-ee15733f-2799725523214323595.apk",
            "mobile_app_hash": "57e487d42eaa459b1713df8c1dd691a8",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.pozitron.pegasus.pilotRelease\",\"label\":\"PGS Pilot\",\"icon\":\"res/u3.png\",\"versionName\":\"2.39.0.38\",\"versionCode\":119,\"minSdkVersion\":\"23\",\"targetSdkVersion\":\"33\"}",
            "created_at": "2024-10-18 09:34:30"
        },
        {
            "id": 53,
            "mobile_app_name": "Gratis-b250541b__2_-8988176051238453961.ipa",
            "mobile_app_hash": "556372e35d7f2b6fa4b7ceb4c0af8b58",
            "operating_system": "IOS",
            "mobile_app_metadata": "{\"bundleName\":\"Gratis\",\"bundleDisplayName\":\"Gratis\",\"bundleVersion\":\"3.2.12\",\"bundleMinOsVersion\":\"12.0\",\"bundleDevelopmentRegion\":\"tr\",\"bundleExecutable\":\"Gratis\",\"bundleIconFiles\":\"\",\"bundleInfoDictVersion\":\"6.0\",\"bundlePackageType\":\"APPL\",\"bundleMainStoryBoardFile\":\"Main\"}",
            "created_at": "2024-10-18 09:34:30"
        },
        {
            "id": 52,
            "mobile_app_name": "FLO_v4.1.35_apkpure.com-8805574610750679613.apk",
            "mobile_app_hash": "65300b98fc9bfa19c7d6a5e2415dbfba",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.flo.ayakkabi\",\"label\":\"FLO\",\"icon\":\"res/mipmap-mdpi-v4/ic_launcher.png\",\"versionName\":\"4.1.35\",\"versionCode\":41035,\"minSdkVersion\":\"19\",\"targetSdkVersion\":\"30\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
            "created_at": "2024-10-18 09:34:30"
        },
        {
            "id": 51,
            "mobile_app_name": "3.2.39__130_-83f575df-b7266d12-2359313112333632572.apk",
            "mobile_app_hash": "177f1b975b8f99e8006dd8bf88686f6e",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.gratis.android\",\"label\":\"Gratis\",\"icon\":\"res/d2.webp\",\"versionName\":\"3.2.39\",\"versionCode\":130,\"minSdkVersion\":\"24\",\"targetSdkVersion\":\"34\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
            "created_at": "2024-10-18 09:34:30"
        },
        {
            "id": 50,
            "mobile_app_name": "FLO_v4.1.35_apkpure.com-5251573303048927998.apk",
            "mobile_app_hash": "65300b98fc9bfa19c7d6a5e2415dbfba",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.flo.ayakkabi\",\"label\":\"FLO\",\"icon\":\"res/mipmap-mdpi-v4/ic_launcher.png\",\"versionName\":\"4.1.35\",\"versionCode\":41035,\"minSdkVersion\":\"19\",\"targetSdkVersion\":\"30\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
            "created_at": "2024-10-18 09:29:59"
        },
        {
            "id": 49,
            "mobile_app_name": "3.2.39__130_-83f575df-8eb62344-6628958833235309567.apk",
            "mobile_app_hash": "177f1b975b8f99e8006dd8bf88686f6e",
            "operating_system": "ANDROID",
            "mobile_app_metadata": "{\"packageName\":\"com.gratis.android\",\"label\":\"Gratis\",\"icon\":\"res/d2.webp\",\"versionName\":\"3.2.39\",\"versionCode\":130,\"minSdkVersion\":\"24\",\"targetSdkVersion\":\"34\",\"glEsVersion\":{\"major\":2,\"minor\":0,\"required\":false}}",
            "created_at": "2024-10-18 09:29:59"
        }
    ]
}
```

Service Project:

```json
  {
    "id": 89,
    "project_name": "KarateService",
    "description": "",
    "enabled": true,
    "repository_path": "karateservice",
    "test_framework": "SERVICE",
    "test_file_type": "SERVICE_KARATE",
    "test_runner_tool": "MAVEN",
    "mobile_apps": []
  }
```

### Response Fields

| Field              | Type      | Description                                         |
| ------------------ | --------- | --------------------------------------------------- |
| `id`               | `Long`    | The ID of the project.                              |
| `project_name`     | `String`  | The name of the project.                            |
| `description`      | `String`  | The description of the project.                     |
| `enabled`          | `Boolean` | Whether the project is active or not.               |
| `repository_path`  | `String`  | The Git repository URL associated with the project. |
| `test_framework`   | `String`  | The testing framework used in the project.          |
| `test_file_type`   | `String`  | The type of test files in the project.              |
| `test_runner_tool` | `String`  | The tool used to run the tests.                     |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                              |
| --------- | ----------------------- | -------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. The user is not logged in.         |
| `403`     | `Forbidden`             | The user does not have permission to access the project. |
| `404`     | `Project not found`     | The specified project was not found or is not active.    |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server side.         |

***

### Example Request

```bash
curl --location '<custom-env-url>/Testinium.RestApi/api/projects/{projectId}/active' \
--header 'Authorization: Bearer <your_access_token>'
```
