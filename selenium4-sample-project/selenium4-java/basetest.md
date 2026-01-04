# BaseTest

### BaseTest (Selenium4Java)

<br>

This class is responsible for initializing and managing the Selenium test environment.

Tests are executed on a remote Selenium Grid / Testinium Grid using TestiniumSeleniumDriver.

<br>

Its main responsibilities include:

* Initializing the RemoteWebDriver for the test run
* Configuring browser-specific options (e.g., ChromeOptions)
* Providing a shared driver instance for test execution
* Handling test lifecycle operations
* Ensuring proper cleanup of resources after execution completes

<br>

All driver lifecycle operations are managed using JUnit 5 annotations.

***

### @BeforeAll setup()

<br>

This method runs once before all test methods in the test class.

<br>

Its responsibilities include:

*   Determining the remote Selenium Grid URL

    (e.g. http://host.docker.internal:4444/wd/hub or via environment variables)
* Creating and configuring browser options:
  * ChromeOptions for Chrome-based executions
  * Testinium-specific capabilities can be added if required
* Initializing the driver using TestiniumSeleniumDriver
* Performing optional driver-level configurations:
  * Maximizing the browser window
  * Setting implicit/explicit waits
  * Initializing WebDriverWait or FluentWait for dynamic elements

<br>

> Note: Since the driver is initialized using @BeforeAll, the same browser session is shared across all test methods in the class.

> Note: When tests are executed on the Testinium platform, TestiniumSeleniumDriver must be used instead of the standard RemoteWebDriver to ensure proper integration with Testinium infrastructure and reporting.

***

### @AfterAll teardown()

<br>

This method runs once after all test methods in the test class.

<br>

Its responsibilities include:

* Quitting the WebDriver session using driver.quit()
* Releasing Selenium Grid resources
* Preventing session leaks

***

### Test Execution (@Test)

<br>

Test methods use the shared driver instance to:

* Navigate to target web pages
* Interact with UI elements
* Handle dynamic components such as cookie consent dialogs
* Validate application behavior using JUnit assertions

<br>

Example test actions include:

* Searching for a keyword on a search engine
* Verifying the visibility of result containers
* Asserting page titles and expected content
