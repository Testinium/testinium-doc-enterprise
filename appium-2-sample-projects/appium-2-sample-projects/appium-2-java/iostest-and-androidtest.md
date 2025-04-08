# IOSTest And AndroidTest

The `IOSTest` class is designed to perform basic user interaction tests on iOS devices. It uses the Appium library to interact with an iOS application through various UI actions. This class extends the `BaseTest` class to inherit the necessary Appium driver (`iosDriver`) setup.

***

#### `basicIosTest()`

This method is a test method executed with JUnit. It simulates typical user interactions such as swiping and tapping on elements within the iOS application.

***

#### `fingerSwipe()`

This helper method simulates a swipe gesture using Appium's `PointerInput` and `Sequence` classes. It performs a finger swipe based on the provided start and end coordinates and the swipe duration.

* This gesture helps to replicate the natural finger movement on the screen as part of test automation.
* It is particularly useful for testing scrollable views or triggering specific UI behaviors triggered by swipe gestures.



The `AndroidTest` class is designed to test basic user scenarios on Android devices.

In the `basicAndroidTest` method, a simple test is implemented using basic click actions to simulate user interaction on the Android application.
