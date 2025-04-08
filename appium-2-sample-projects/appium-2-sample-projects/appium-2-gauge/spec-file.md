# Spec File

A **Specification (Spec)** file in the **Gauge** framework defines the test scenarios and the steps involved in them. It outlines **how tests should be performed** and ensures each test remains meaningful and traceable. Each heading in a spec file corresponds to a specific test case or scenario.

```java
IOSBasicTest
-----
tags: Ios Basic Test
* IOS Basic (Xpath)

```

> This spec runs the concept step for basic iOS UI interaction using XPath locators.

```java
AndroidBasicTest
-----------
tags: Android Basic Test
* Android Basic (ANDROID)

```

This spec defines a basic Android interaction test, referencing the concept that waits and clicks an element by ID.

🔗 **How It Connects with Concept Files**

In Gauge, **specification files** define _what the test does_, while **concept files** define _how the steps are executed_. The connection between the two is made through **step text matching**.

When a step is written in the spec file, Gauge searches the concept files to find a matching implementation (by exact string match or with parameter patterns).
