# Concept File

#### **Explanation of the Concept File Format**

#### **Heading**

* **Test Name and Description:** The heading explains what the test is about and which functionality is being tested.

#### **Steps:**

* **Each step is explained sequentially** and **the flow of the test** is clearly defined.
* The steps may include:
  1. **Element Loading:** Locating an element using a specific `Xpath` or ID.
  2. **Clicking:** Clicking on the element to perform the desired action.
  3. **Wait:** If the test involves any time-based wait, the duration is explicitly stated.

#### **Explanations:**

* **The purpose of each step** is explained to provide clarity on how the test operates.
* **Xpath** or **Locator** expressions help understand how the step is performed.

```java
java
CopyEdit
# IOS Basic (Xpath)
* Find and click the element with XPath "//XCUIElementTypeButton[contains(@name, \\"Markalar\\")]"
* Find and click the element with XPath "//XCUIElementTypeButton[contains(@name, \\"Kampanyalar\\")]"
* Wait for "1" second

```

This test verifies if the user is successfully redirected by clicking on the "Markalar" and "Kampanyalar" tabs on an iOS device.

```java
java
CopyEdit
# Android Basic (ANDROID)
* Wait for "2" seconds
* Find and click the element by ID "com.gratis.android:id/nav_graph_categories"

```

This test step in the concept file is designed to locate and click a specific element on an Android device.

#### **Step-by-Step Explanation:**

1. **Wait for Element to Load (Xpath):**
   * **Xpath:** `"YOUR_XPATH"`
   * The test waits for the target element, identified by the given **Xpath**, to be visible and accessible.
2. **Click on the Element (iOS Xpath):**
   * **Xpath:** `"YOUR_XPATH"`
   * Performs a click action on the specified **Xpath** and verifies if the click behavior works as expected.
3. **Wait for "1" Second:**
   * Waits for 1 second after the click. This is often needed for animations or page transitions to complete.
