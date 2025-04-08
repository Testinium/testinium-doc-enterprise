# HookImp

When writing tests with Appium 2, it’s important to create a **Hook** class to perform the necessary setup and teardown operations at the beginning and end of the test scenarios. This class ensures that the proper test environment is prepared and maintained. The Hook class primarily serves the following purposes:

1. **Device and Driver Initialization:**
   * Initializes the required Appium drivers for both Android and iOS platforms.
   * Applies platform-specific configurations to prepare the correct environment.
2. **Driver Teardown After Test Scenarios:**
   * Terminates the driver once the test is completed and releases the resources.

#### ✨ **@BeforeScenario and @AfterScenario Annotations**

* **`@BeforeScenario`:**
  * Executed before the start of each test scenario.
  * This method detects the device platform (Android or iOS), starts the appropriate Appium driver, and sets up the necessary configurations such as wait strategies.
* **`@AfterScenario`:**
  * Executed after the test scenario is finished.
  * This method stops the driver used during the test and ensures proper cleanup of resources and logs any errors if encountered.

#### 🧩 **Main Objects and Their Usage**

#### **Logger Object**

* **Purpose:** Used for providing information and debugging during test execution. The logs indicate whether the test passed successfully or failed due to an error.
* **Usage:** The `Logger` instance logs all events during the test, which helps in tracking and analyzing the test outcome.

#### **AppiumDriver Object**

* **Purpose:** The Appium driver used in the test scenarios to interact with the mobile device.
* **Usage:** The `driver` object represents the Appium driver that performs actions on Android or iOS devices during the test.

#### **hubUrl**

* **Purpose:** Holds the URL used to connect to the Appium server.
* **Usage:** `hubUrl` is used to establish a connection with the Appium server where the test will be executed.

#### **appiumFluentWait**

* **Purpose:** Strategy used to wait for UI elements during tests. `FluentWait` keeps polling for the element for a defined duration before throwing an exception.
* **Usage:** Used when an element is expected to appear on the screen but might take a few seconds to load.

📋 **Explanation of the beforeScenario Method**

* The **`@BeforeScenario`** method checks whether the device is Android or iOS.
* It applies the required `DesiredCapabilities` for the platform and initializes the correct driver.
* Also sets up timeout configurations and fluent wait strategies needed for stable test execution.

📋 **Explanation of the afterScenario Method**

* The **`@AfterScenario`** method terminates the driver once the test is complete.
* Any potential errors are logged, and resources are properly released to ensure clean execution.

#### **TestiniumIOSDriver and TestiniumAndroidDriver**

* Thanks to the added library, we can define `TestiniumIOSDriver` and `TestiniumAndroidDriver`, which allow us to run the tests on the Testinium platform by creating appropriate drivers.
