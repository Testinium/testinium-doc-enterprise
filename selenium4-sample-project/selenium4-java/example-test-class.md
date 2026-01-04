# Example Test Class

This test class demonstrates how Selenium test scenarios are implemented by extending the shared BaseTest class.

<br>

By inheriting from BaseTest, the test class automatically gains access to the initialized WebDriver instance and does not need to handle driver setup or teardown logic.



#### Test Scenarios

The following test cases are included:

* searchSelenium
  * Navigates to Google
  * Handles the cookie consent dialog if present
  * Performs a search for the keyword _“Selenium”_
  * Verifies that the search results section is displayed
  * Asserts that the page title contains the expected keyword
* openAmazonAndPrintTitle
  * Navigates to Amazon
  * Prints the page title to the console
  * Verifies that the page title is not empty

#### Key Points

* Test classes focus solely on test steps and assertions.
* WebDriver lifecycle management is fully handled by BaseTest.
* Tests are executed using the shared driver instance provided by the framework.
* This structure improves readability, maintainability, and consistency across test classes.
