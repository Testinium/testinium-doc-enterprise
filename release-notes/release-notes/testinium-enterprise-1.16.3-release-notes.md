# Testinium-Enterprise 1.16.3 Release Notes

#### Release Date: 15.02.2024

#### New Features

* If an error related to the path of the storage occurs (if the result cannot be found), the report deletion process will now be completed without errors.
* On the Dashboard page, the ability to select multiple projects for the pie chart has been implemented.
* User Roles can now be managed with permissions.
* A "terminating" status has been added for stopping tests on the Active Test page.
* The part causing a 2-minute delay in the Appium jar for mobile runs has been removed.
* Created at and created by information has been added to the Scenario page.
* The "testinium.cron.active.storage.cleaner" setting has been added to the System properties page to enable the shutdown of storage clean processes and prevent data from being deleted based on user requests.
* In the Device Manager installation process, the ability to add the hub address parametrically has been enabled.

#### Bug Fixes

* TestNG tests now support scenarios containing Background and Rule sections.
* The bug preventing the deletion of Test Environments has been fixed.
* A confirmation message has been added for stopping runs on the Active Test page.
* The error encountered when connecting Android devices to Windows nodes has been fixed.
* During plan creation, the scenario names in the confirm step have been made responsive.
