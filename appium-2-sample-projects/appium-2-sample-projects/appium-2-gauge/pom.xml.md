# pom.xml

The `pom.xml` file is the **configuration file of a Maven project**. Maven is a build automation tool used to **compile Java projects automatically**, **manage dependencies**, and **run tests**.

In order for a project to run properly, the `pom.xml` file must be included in the project structure.

Below is an explanation of some `dependencies` and `properties` used in the project:

* **distributionManagement**: Defines the distribution (publishing) settings of the project. In this case, it specifies that the project will be deployed to a private Maven repository named `testinium-mvn`.
* **repositories**: Indicates the Maven repository from which the project dependencies will be downloaded. A custom repository named `testinium-mvn` is defined here.

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

* **gauge-java**: [Gauge](https://gauge.org/) is a test automation framework. This dependency includes the Gauge Java API in the project. (Version 0.9.1 must be used to run tests on the Testinium platform.)
* **Appium java-client**: The [Appium](https://appium.io/) Java client library used for mobile application testing. It enables interaction with mobile devices. (Version 8.6.0 is required for compatibility with Testinium.)
* **maven-compiler-plugin**: This plugin allows Maven to compile Java code. The `source` and `target` parameters specify the Java version to be used.
* **maven-surefire-plugin**: A Maven plugin that runs unit tests. If the `skipTests` parameter is set to `true`, the tests will be skipped.
* **gauge-maven-plugin**: A dedicated plugin used to run Gauge tests via Maven.
* **java.version**: Specifies the Java version used for compiling the project. (Java 21 is required for execution on the Testinium platform.)
* **testinium-appium2-driver**: This library provides the Appium 2 driver required to run test scenarios on the **Testinium** platform.

```java
<dependency>
    <groupId>com.testinium</groupId>
    <artifactId>testinium-appium2-driver</artifactId>
    <version>0.0.14-SNAPSHOT</version>
</dependency>

```

To successfully add this library to your project, you also need to include the `distributionManagement` and `repositories` sections in the `pom.xml` file. This library is essential for running your tests on the Testinium platform.
