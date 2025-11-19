# Testinium-Enterprise 2.0.0 Release Notes

#### **Release Date: 16.05.2025**

#### New Features

* **A new executor model has been introduced to improve test run stability.**

Each test run now launches its own executor container via Docker Engine.&#x20;

Parallel execution capacity and overall system stability have been significantly improved.&#x20;

Hanging processes (e.g., SSH sessions) are eliminated. After this update, the Executor field under **Company List > Company Details** must be updated with the Docker Engine IP/Hostname.&#x20;

* **The test queue mechanism has been migrated from in-memory processing to RabbitMQ.**

Provides higher scalability and persistent queueing.&#x20;

Prevents data loss during restarts and improves overall performance for high-volume executions.&#x20;

* **Appium 2 is now fully supported on the platform, including dedicated libraries for Java and Gauge frameworks.**

Note: Appium 2 license registration is required. For licensing and library access: **support@testinium.com**

* **Node reservation has been moved from the hub layer to Redis.**

Faster reservation processing&#x20;

Better data consistency&#x20;

Eliminated concurrency issues during heavy load&#x20;

* **Users running tests via Testinium Cloud Plugin can now upload mobile applications directly from Testinium Enterprise during execution—no need to create upload plans from the Cloud interface.**
* **New Scenario Execution Statuses Added.**

New end-to-end execution statuses: **Waiting,** **Processing, Reporting, Terminating, Stopped, Unexecuted**

* **Failed Test Retry Count Reporting Added.**

Users can now view errors separately for each retry attempt in scenarios executed with Failed Test Retry Count.

#### Bug Fixes

* Fixed an issue where retry runs were incorrectly triggered even when the first test execution was successful.&#x20;
* Resolved a problem where the plan-level parallelism setting was not saved consistently.&#x20;
* Fixed the multiple project selection issue on the Dashboard.&#x20;
* Fixed search-related errors on the Plan page when “All Projects” was selected.&#x20;
* Resolved the project filter issue on the Test Result by Period report.&#x20;
* Fixed cloud plugin execution errors related to the Dynamic Executor & Queue migration.
* Resolved a DB connection concurrency error detected during Dynamic Executor integration.&#x20;
*   Fixed an issue where reports could not be displayed properly.

    \


