# BaseSteps

## BaseSteps (Gauge Step Definitions)

<br>

The BaseSteps class contains reusable Gauge step implementations that interact with the web application through Selenium.

<br>

It extends BaseTest and uses the shared WebDriver instance initialized at the suite level.

All step definitions are designed to be generic, readable, and reusable across different scenarios.

***

### Responsibilities

<br>

The BaseSteps class is responsible for:

* Providing common navigation and interaction steps
* Resolving element locators dynamically using element keys
* Handling synchronization using explicit waits
* Encapsulating low-level Selenium interactions
* Exposing readable, business-oriented step definitions for Gauge scenarios
