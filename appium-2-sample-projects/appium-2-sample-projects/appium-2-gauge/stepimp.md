# StepImp

The `StepImplementation` class defines various steps used during test scenarios, such as clicking on elements, waiting for elements, and handling wait times. Each step is annotated with **@Step** and is converted into test steps by the Gauge framework. Additionally, the class uses the **SLF4J Logger** to keep logs of the tests.

#### 📜 **StepImplementation Class Explanation**

The **StepImplementation** class defines step-by-step actions in tests written using the Gauge framework. This class contains various steps used in Appium-based tests and ensures that Gauge correctly links each step using **@Step** annotations.

#### 📌 **General Purpose of the Class:**

This class provides methods for steps used in **test scenarios**. These methods are specifically written for interacting with **iOS devices** and include user interactions, waiting strategies, and other related tasks.

#### 🧩 **Methods and Their Explanations**

#### 1. **`waitBySecond` Method**

* **Annotation:** `@Step({"<seconds> saniye bekle", "Wait <second> seconds"})`
* **Purpose:** This method pauses execution for the specified number of seconds. The wait time is passed as the `seconds` parameter.

```java
java
CopyEdit
@Step({"<seconds> saniye bekle", "Wait <second> seconds"})
public void waitBySecond(int seconds) {
    try {
        TimeUnit.SECONDS.sleep(seconds);
        logger.info("{} saniye beklendi", seconds);
    } catch (InterruptedException e) {
        e.printStackTrace();
    }
}

```

#### 2. **`clickElementByXpathIOS` Method**

* **Annotation:** `@Step("XPath ile elementi bul ve tıkla <xpath>")`
* **Purpose:** This method finds the element specified by the given **XPath** and clicks it on an **iOS device**.

```java
java
CopyEdit
@Step("XPath ile elementi bul ve tıkla <xpath>")
public void clickElementByXpathIOS(String xpath) {
    WebElement element = driver.findElement(AppiumBy.xpath(xpath));
    element.click();
}

```

#### 3. **`clickElementByIdIOS` Method**

* **Annotation:** `@Step("ID ile elementi bul ve tıkla <id>")`
* **Purpose:** This method finds the element specified by the given **ID** and clicks it on an **iOS device**.

```java
java
CopyEdit
@Step("ID ile elementi bul ve tıkla <id>")
public void clickElementByIdIOS(String id) {
    WebElement element = driver.findElement(AppiumBy.id(id));
    element.click();
}

```
