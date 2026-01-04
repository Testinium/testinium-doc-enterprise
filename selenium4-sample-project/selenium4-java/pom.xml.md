# Pom.xml

### Maven Configuration (pom.xml)

<br>

This project uses Maven for dependency management and build configuration.

The pom.xml file defines all required dependencies for running Selenium 4 tests with JUnit 5 on the Testinium platform.



#### Key Dependencies

**Selenium**

```
<dependency>
    <groupId>org.seleniumhq.selenium</groupId>
    <artifactId>selenium-java</artifactId>
    <version>4.25.0</version>
    <scope>test</scope>
</dependency>
```

Provides the core Selenium 4 APIs required for browser automation.



**JUnit 5**

```
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>${junit.version}</version>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>${junit.version}</version>
    <scope>test</scope>
</dependency>
```

Used for test lifecycle management, annotations, and assertions.



**Testinium Selenium 4 Driver (Required)**

```
<dependency>
    <groupId>com.testinium</groupId>
    <artifactId>testinium-selenium4-driver</artifactId>
    <version>0.0.0.31-SNAPSHOT</version>
</dependency>
```

This dependency is mandatory when executing tests on the Testinium platform.

<br>

It provides:

* Integration with the Testinium Selenium Grid
* Execution lifecycle management
* Platform-specific capabilities and metadata handling
* Compatibility with Testinium reporting and execution tracking

<br>

> Note: When tests are executed on Testinium, TestiniumSeleniumDriver must be used instead of the standard RemoteWebDriver.

> The testinium-selenium4-driver dependency enables this integration and is therefore required.

#### Testinium Maven Repository

```
<distributionManagement>
        <repository>
            <id>testinium-mvn</id>
            <url>https://mvn.testinium.com/repository/public/</url>
        </repository>
    </distributionManagement>

    <repositories>
        <repository>
            <id>testinium-mvn</id>
            <url>https://mvn.testinium.com/repository/public/</url>
        </repository>
    </repositories>
```

#### Java & Compiler Configuration

```
<properties>
    <maven.compiler.source>21</maven.compiler.source>
    <maven.compiler.target>21</maven.compiler.target>
</properties>
```

The project is configured to use Java 21, fully compatible with Selenium 4 and JUnit 5.
