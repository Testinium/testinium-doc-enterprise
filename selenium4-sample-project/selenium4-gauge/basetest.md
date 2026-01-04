# BaseTest



This class is responsible for initializing and managing the Selenium test environment for Gauge-based tests.

All tests are executed on a remote Selenium Grid / Testinium Grid using TestiniumSeleniumDriver.

The WebDriver lifecycle is managed at the suite level, meaning a single browser session is shared across all scenarios in the test suite.

***

### Responsibilities

The BaseTest class provides the following core responsibilities:

* Initializing the Selenium WebDriver once per test suite
* Configuring browser-specific options (ChromeOptions)
* Integrating with the Testinium platform via TestiniumSeleniumDriver
* Managing the WebDriver lifecycle using Gauge hooks
* Loading and managing the Element Repository from JSON files
* Providing shared access to WebDriver and Actions instances

***

### Suite Lifecycle Management

#### @BeforeSuite

This method is executed once before all Gauge specifications and scenarios.

Its responsibilities include:

* Resolving the remote Selenium Grid URL from environment variables
  * SELENIUM\_REMOTE\_URL
* Resolving the Testinium authentication key
  * TESTINIUM\_KEY
* Creating and configuring ChromeOptions
* Initializing the TestiniumSeleniumDriver
* Creating a shared Actions instance
* Loading the element repository (elementValues) into memory

<br>

Because @BeforeSuite is used, all scenarios share the same WebDriver session, which aligns with an all-in-one execution model.

***

#### @AfterSuite

This method is executed once after all Gauge specifications and scenarios are completed.

Its responsibilities include:

* Gracefully terminating the WebDriver session
* Releasing Selenium Grid resources
* Preventing stale browser sessions and memory leaks

***

### Browser Configuration

Browser configuration is centralized in the buildChromeOptions method.<br>

Configured options include:

* Disabling browser translation prompts
* Disabling notifications
* Allowing cross-origin and insecure content (when required by test environments)



This approach ensures all browser-related configurations are managed in a single, reusable location.
