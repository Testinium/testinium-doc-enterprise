# Testinium-Enterprise 2.0.1 Release Notes

#### Release Date: 30.07.2025

#### New Features

* Stop action support has been added to the Enterprise UI, enabling tests to be stopped directly from the Active Plans and Active Scenarios pages.
* A “Show Deleted” checkbox has been added to the Scenarios page, allowing users to view deleted scenarios for audit and history tracking.
* A warning and manual-stop guidance mechanism has been added for environments switched to Free while an active test is still running.
* Dynamic resource allocation has been added, allowing executor containers to be configured with custom CPU and memory limits.
* A manual “Release Node” button has been added for devices stuck in Reserved status, enabling admins to free them instantly.
* Test stopping is now fully supported in the new execution architecture.

#### Bug Fixes

* Fixed an issue where status labels appeared merged on the Plan page in Enterprise 2.0.
* Resolved incorrect duration display for Cloud Plugin executions on Enterprise results.
* Fixed PDF and Excel export issues on Test Reports > Test Execution List (Auto) for Appium 2 project types.

