# Testinium-Enterprise 1.16.4 Release Notes

#### Release Date: 19.03.2024

#### New Features

* An endpoint has been created to allow the assignment of a company during user creation via the API.
* To obtain information about the node where the test ran for mobile runs, a "node info" field has been added to the Excel file downloaded from the report page.
* A new system property has been created for the active/inactive setting of the job running for plan deletion.
* A system property has been created for the SMTP server to specify the allowed versions of TLS.
* On the Dashboard page, the ability to navigate to the detailed report page when clicking on piecharts has been added.

#### Bug Fixes

* The bug encountered in service tests when calling tables in the test code has been fixed.
* The bug where the Assigned User and Reporter fields were not retrieved in Enterprise Jira integration has been fixed.
* The bug occurring between page transitions on the report page for customers using different types of databases has been fixed.
* The bug encountered when switching between report pages while the HTML report is open in web tests has been fixed.
