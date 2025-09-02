# Feature

**Purpose:** Simple navigation scenarios for Android and iOS, separated by tags.

```gherkin
Feature: Open Application and Navigate Between Sections

  @NavigationIOS
  Scenario: Navigate to Brands and Categories on iOS
    Given Wait 5 seconds
    Then Element with xpath "//XCUIElementTypeButton[@name='Brands']" is clicked
    Then Wait 2 seconds
    Then Element with xpath "//XCUIElementTypeButton[@name='Categories']" is clicked
    Then Wait 2 seconds

  @NavigationAndroid
  Scenario: Navigate to Brands, Categories, and Campaigns on Android
    Given Wait 5 seconds
    Then Element with id "com.gratis.android:id/nav_graph_trademarks" is clicked
    Then Wait 2 seconds
    Then Element with id "com.gratis.android:id/nav_graph_categories" is clicked
    Then Wait 2 seconds
    Then Element with id "com.gratis.android:id/nav_graph_campaign" is clicked
    Then Wait 2 seconds
```

