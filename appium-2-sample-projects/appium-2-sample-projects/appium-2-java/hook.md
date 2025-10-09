# pom.xml

This `pom.xml` file defines a Java project configured with Maven. The project is designed for mobile test automation using **Appium 2**. Below is a detailed explanation of each section:

* **`project.build.sourceEncoding`**: Sets the character encoding to UTF-8.
* **`java.version`**: Specifies that the project uses Java 21.
* **`appium.version`**: Defines the version of the Appium Java client.
* **`junit.version`**: Defines the version of JUnit 5 used for testing.
* **`distributionManagement`**: Defines where Maven should deploy built artifacts (for publishing).
* **`repositories`**: Declares an external repository (Testinium’s) from which Maven can download project dependencies.

```java
<distributionManagement>
        <repository>
            <id>testinium-mvn</id>
            <url><https://mvn.testinium.com/repository/public/></url>
        </repository>
    </distributionManagement>

    <repositories>
        <repository>
            <id>testinium-mvn</id>
            <url><https://mvn.testinium.com/repository/public/></url>
        </repository>
    </repositories>
```

* **JUnit Jupiter Engine**
  * Provides support for writing and executing tests using **JUnit 5**.
  * Used for unit and integration testing within the project.
* **Appium Java Client**
  * Enables mobile automation by allowing the project to communicate with Android and iOS devices.
  * Compatible with Appium 2 and used to write test scripts for mobile apps.
* **Log4j 2 (API and Core)**
  * Adds logging capabilities to the project.
  * `log4j-api` provides the interface for logging, while `log4j-core` contains the actual implementation.
  * Helps with tracking test execution, errors, and debugging information.
* **Testinium Appium 2 Driver**
  * A custom Appium 2 driver developed by **Testinium**.
  * May include enhancements or features specific to Testinium’s automation framework.
  * Packaged as a `0.0.14-SNAPSHOT` version, indicating it may still be under development or testing.
