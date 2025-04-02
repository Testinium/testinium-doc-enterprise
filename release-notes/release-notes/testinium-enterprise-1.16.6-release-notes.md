---
hidden: true
---

# Testinium-Enterprise 1.16.6 Release Notes

#### Release Date: 30.10.2024

#### New Features

* Azure DevOps Board integration has been added.
* The XML Report generated after the run has been added to the result reports.
* A setting has been added to allow video recording, screenshot, and parallel settings for plans to be changed with a single project-based configuration. (System Settings-General Test Plan Settings)
* A setting has been added to allow multiple selected scheduled plans to be set as unscheduled from the Company's Scheduled Plans Detail page.
* The viewing experience of video recordings from test results has been updated, allowing users to jump to specific timestamps, adjust playback speed, and move the video forward or backward.
* The processes of node reservation and status updates have been updated.
* The data update frequency for cards on the Dashboard has been improved.
* Users can now clone multiple projects to a chosen company.
* The total number of connected nodes can now be viewed on the Test Environment Status page.
* Permissions for the Role Admin, Role Company Admin, and Role Run Test roles have been updated.
* A scroll has been added to the scenario selection area on the Plan Create/Edit page.
* The pie chart reports on the Dashboard can now be filtered based on the selected project type.
* Scenarios are now displayed with their group names in test result emails.
* Group scenarios without any child scenarios are now excluded from the scenario selection screen on the plan selection page.
* A scroll has been added to the project selection area on the Pass Rate Reports page.

#### Bug Fixes

* Runner Class selection has been added to the scenario creation page for Karate and Cucumber projects with multiple Runner Classes to prevent potential errors during execution.
* Fixed an error where system parameters in scenarios could not be cloned to the selected company during the project cloning process.
* Performance errors in Azure Devops Board integration have been fixed.
* Fixed an issue where service projects could not be displayed on the BDD Editor page.
* Fixed an error where files could not be saved when uploaded with multiple selection using the File Upload to Node feature.
* Fixed an error in the display of the Piechart on the Dashboard for different screen sizes.
* Navigation errors on the Plan page have been fixed, and the breadcrumb structure has been improved.
* Fixed an issue where users were directed to the project update page after clicking the Cancel button on Jira and Azure Settings pages.
* Fixed an issue where the plan name could not be displayed when Selenium Grid was changed on the Plan Create page.
