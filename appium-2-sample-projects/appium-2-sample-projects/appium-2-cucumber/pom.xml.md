# pom.xml

This page explains the exact pom.xml used in your Appium 2 + Cucumber project and what each section does.

pom.xml is the core configuration file for Maven. It defines project coordinates, Java version, dependencies, and build plugins.

#### Properties

* **`java.version`**: Java release used to compile sources (`23` here).
* **`cucumber.junit.version`**: Cucumber-JUnit version (`4.8.0`) used across dependencies.

#### distributionManagement & repositories

Both point at `https://mvn.testinium.com/repository/public/`. This allows Maven to resolve (and publish, if needed) artifacts such as `testinium-appium2-driver`.

#### Dependencies

* **Cucumber (JUnit 4):** `cucumber-junit` and `cucumber-java` provide the runner and step APIs.
* **Appium Java Client (8.6.0):** Enables communication with Appium Server and devices.
* **testinium-appium2-driver:** Provides `TestiniumAndroidDriver` and `TestiniumIOSDriver` for running on the Testinium platform.

#### Build Plugins

* **maven-compiler-plugin 3.14.0**: Compiles sources using `source`/`target` `23`.
* **maven-surefire-plugin 3.2.5**: Executes tests; your Cucumber runner integrates with JUnit 4 so scenarios run in the Maven test phase.
