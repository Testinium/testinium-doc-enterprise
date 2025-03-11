# Testinium-Enterprise 1.16.7 Release Notes

#### Release Date: 19.02.2025

#### New Features

* API documentation has been updated for automating the mobile application file upload process via pipelines. [Click for Testinium Enterprise API documentation.](../../apis/auth/)
* Added an "Export Excel" button to the Plan page, allowing users to download listed plans in a table format.
* Added an "Export Excel" button to the Test Result Details page for Service plans, enabling users to download service execution reports.
* Added a warning message for Java file selection for Karate and Cucumber projects in scenario creation.
* Added a warning message for mobile application file type selection in Appium projects. If an IPA file is selected, only iOS devices can be chosen; if an APK file is selected, only Android devices can be chosen. This prevents errors due to mismatched file and device selection.
* Added an "All Projects" selection in the project dropdown on the Plan page, enabling users to list plans from all projects.
* Created a user guide for Azure DevOps Board integration. [Click for Azure DevOps Board Integration user guide.](../../plugins/plugins/azure-devops-board.md)

#### Bug Fixes

* Fixed an issue where search functionality in dropdown menus was not working correctly.
* Resolved a responsiveness issue on the System Settings - Notification page that occurred after sorting column headers.
* Fixed a DLL selection issue in SpecFlow projects. The DLL file selected during project creation can now also be selected during plan creation.
* Fixed a layout issue on the Detailed Reports and Test Execution Auto pages that occurred when selecting a project.

