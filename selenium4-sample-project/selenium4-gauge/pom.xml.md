# Pom.xml

### Maven Configuration (pom.xml)

<br>

This project uses Maven to manage dependencies and build configuration for Gauge-based Selenium tests running on the Testinium platform.

<br>

The pom.xml includes:

* Gauge Java runner for executing .spec files
* Selenium 4 for browser automation
* Testinium Selenium 4 driver for Testinium Grid integration
* Supporting libraries (Lombok, SLF4J)

***

#### Testinium Maven Repository

<br>

The Testinium Maven repository is required to resolve Testinium-specific artifacts:

* https://mvn.testinium.com/repository/public/

<br>

This repository is defined under both repositories and distributionManagement.

#### Key Dependencies

<br>

**Gauge (Java Runner)**

```
<dependency>
  <groupId>com.thoughtworks.gauge</groupId>
  <artifactId>gauge-java</artifactId>
  <version>${gauge.version}</version>
  <scope>test</scope>
</dependency>
```

Provides the Gauge Java runtime and step-definition support required to execute Gauge specifications.

***

**Selenium 4**

```
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>${selenium.version}</version>
  <scope>test</scope>
</dependency>
```

Provides Selenium WebDriver APIs used by step implementations to automate the browser.

<br>

> Note: Ensure only one Selenium version is used in the project to avoid dependency conflicts.

**Testinium Selenium 4 Driver (Required)**

```
<dependency>
  <groupId>com.testinium</groupId>
  <artifactId>testinium-selenium4-driver</artifactId>
  <version>0.0.0.31-SNAPSHOT</version>
</dependency>
```

This dependency is mandatory when executing Selenium tests on the Testinium platform.

<br>

It enables:

* Integration with the Testinium Selenium Grid
* Platform-specific capabilities (e.g., testinium:key)
* Execution tracking and reporting compatibility

<br>

> Note: When tests are executed on Testinium, TestiniumSeleniumDriver must be used instead of the standard RemoteWebDriver.



#### Logging & Utilities



**Lombok**

Used to reduce boilerplate code (e.g., @Slf4j).<br>

**SLF4J API**

Provides a standard logging facade used in step implementations and hooks.

***

### Build Plugins

#### Maven Compiler Plugin

Compiles the project using Java 21.



#### Gauge Maven Plugin



Enables running Gauge specifications via Maven, typically through:

* mvn test
* or mvn gauge:execute (depending on your setup)



