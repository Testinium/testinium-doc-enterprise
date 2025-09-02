# Hooks

**Purpose:** Set up the driver and waits before each scenario; quit the driver after the scenario.

#### What it does

* @Before: Detects _Android_ vs _iOS_, then starts `TestiniumAndroidDriver` or `TestiniumIOSDriver` accordingly.
* Hub URL: `http://192.168.1.89:4723/` (as in your code). You can switch it to a Testinium hub when needed.
* Android sample capabilities: `platformName`, `udid`, `automationName`, `appPackage`, `appActivity`, `autoGrantPermissions`, `newCommandTimeout`.
* iOS sample capabilities: `platformName`, `udid`, `automationName`, `bundleId`, `autoAcceptAlerts`.
* Configures implicitlyWait and a FluentWait strategy.
* @After: Closes the driver via `quit()`.

```java
public class Hooks {
  private Logger logger = LoggerFactory.getLogger(getClass());
  public static AppiumDriver driver;
  public static FluentWait<AppiumDriver> appiumFluentWait;

  @Before
  public void setUp() {
    URL hubUrl = new URL("<http://192.168.1.89:4723/>");

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
