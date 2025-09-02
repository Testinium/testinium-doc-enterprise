# Hooks

### Purpose

Set up the driver and waits **before each scenario**, and quit the driver **after each scenario**.

### What it does

* **@Before:** Detects Android vs iOS, then starts `TestiniumAndroidDriver` or `TestiniumIOSDriver` accordingly.
* **Hub URL:** Default is `http://192.168.1.89:4723/`. Can be switched to a Testinium hub when needed.
* **Android capabilities:** `platformName`, `udid`, `automationName`, `appPackage`, `appActivity`, `autoGrantPermissions`, `newCommandTimeout`.
* **iOS capabilities:** `platformName`, `udid`, `automationName`, `bundleId`, `autoAcceptAlerts`.
* Configures `implicitlyWait` and a `FluentWait` strategy.
* **@After:** Closes the driver via `quit()` and clears references.

### Main Objects and Their Usage

#### Logger

**Purpose:** Provide info/debug logs during test execution.\
**Usage:** Helps diagnose setup errors and failures.

#### AppiumDriver

**Purpose:** Core driver for interacting with the mobile device.\
**Usage:** Accessed as `Hooks.driver` in step definitions.

#### hubUrl

**Purpose:** Stores the Appium server URL.\
**Usage:** Passed when instantiating the Testinium driver.

#### appiumFluentWait

**Purpose:** Robust wait strategy (polling + timeout).\
**Usage:** Used to wait for elements dynamically without failing fast.



```java
public class Hooks {
  private Logger logger = LoggerFactory.getLogger(getClass());
  public static AppiumDriver driver;
  public static FluentWait<AppiumDriver> appiumFluentWait;

  @Before
  public void setUp() {
    URL hubUrl = new URL("http://192.168.1.89:4723/");

    if (TestiniumEnvironment.isPlatformAndroid()) {
      DesiredCapabilities caps = new DesiredCapabilities();
      caps.setCapability(Constants.PLATFORM_NAME, Platform.ANDROID);
      caps.setCapability(UDID, "YOUR_UDID");
      caps.setCapability(APPIUM_AUTOMATION_NAME, "YOUR_AUTOMATION_NAME");
      caps.setCapability(APPIUM_APP_PACKAGE, "YOUR_APP_PACKAGE");
      caps.setCapability(APPIUM_APP_ACTIVITY, "YOUR_APP_ACTIVITY");
      caps.setCapability(APPIUM_AUTO_GRANT_PERMISSIONS, true);
      caps.setCapability(APPIUM_NEW_COMMAND_TIMEOUT, 60000);
      driver = new TestiniumAndroidDriver(hubUrl, caps);
    } else {
      DesiredCapabilities caps = new DesiredCapabilities();
      caps.setCapability(Constants.PLATFORM_NAME, Platform.IOS);
      caps.setCapability(UDID, "YOUR_UDID");
      caps.setCapability(APPIUM_AUTOMATION_NAME, "YOUR_AUTOMATION_NAME");
      caps.setCapability(APPIUM_BUNDLE_ID, "YOUR_BUNDLE_ID");
      caps.setCapability(APPIUM_AUTO_ACCEPT_ALERTS, true);
      driver = new TestiniumIOSDriver(hubUrl, caps);
    }

    driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
    appiumFluentWait = new FluentWait<>(driver)
       .withTimeout(Duration.ofSeconds(8))
       .pollingEvery(Duration.ofMillis(350))
       .ignoring(NoSuchElementException.class);
  }

  @After
  public void tearDown() {
    if (driver != null) { driver.quit(); driver = null; }
  }
}
```

### Before vs After (Quick Reference)

* **@Before:** Detect platform → set capabilities → start driver → configure waits.
* **@After:** Quit driver → cleanup resources.
