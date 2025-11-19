# Testinium-Enterprise 2.0.2 Release Notes

#### **Release Date: 25.09.2025**

#### **Bug Fixes**

* Fixed an issue where tests were getting stuck in the Reporting status by improving XML parsing fallback handling and ensuring executor logs remain accessible even when XML content is unreadable.
* Resolved a stability problem where the system required frequent restarts and tests could not be stopped.
* Fixed an issue where service tests displayed execution runtimes as 1 second, despite longer actual execution times.
