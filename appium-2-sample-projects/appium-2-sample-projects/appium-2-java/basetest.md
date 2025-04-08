# BaseTest

This class is responsible for initializing and managing the test environment based on the platform (Android or iOS). Its main tasks include:

* Initializing the **Appium driver** depending on whether the platform is Android or iOS.
* Setting up a **FluentWait** mechanism to handle dynamic elements during the test flow.
* Performing all necessary **pre-test configurations** before any test execution begins.
* **Tearing down** the Appium driver after all tests are completed to free up system resources.

All of these operations are managed using **JUnit 5** annotations: `@BeforeAll` and `@AfterAll`.

***

#### `@BeforeAll setup()`

This static method runs **once before all tests** in the test class.

* It determines the test platform based on:
  * Whether the `DeviceAndroid` flag is set to `true`, in which case Android is selected.
  * If not, it checks `TestiniumEnvironment.isPlatformAndroid()` to infer the platform.
* Based on the platform, appropriate `DesiredCapabilities` are configured.
* Then, it launches the platform-specific driver:
  * `TestiniumAndroidDriver` for Android.
  * `TestiniumIOSDriver` for iOS.
* A **FluentWait** object is also initialized, allowing the test to wait dynamically for UI elements to become available.

***

#### `@AfterAll teardown()`

This method runs **once after all tests** have been executed.

* If the Appium drivers were initialized, they are gracefully terminated using `quit()`.
* This ensures proper cleanup and **releases system resources** efficiently.
