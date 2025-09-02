# Steps

**Purpose:** Java implementations of the feature steps. In this project there are three basics: wait, click by id, click by xpath.

```java
public class Steps {
  private static void sleepSeconds(int seconds) {
    try { TimeUnit.SECONDS.sleep(seconds); }
    catch (InterruptedException e) { Thread.currentThread().interrupt(); }
  }

  @Then("Wait {int} seconds")
  public void wait_seconds(int seconds) { sleepSeconds(seconds); }

  @Then("Element with id {string} is clicked")
  public void element_with_id_is_clicked(String elementId) {
    Hooks.driver.findElement(By.id(elementId)).click();
  }

  @Then("Element with xpath {string} is clicked")
  public void element_with_xpath_is_clicked(String xpath) {
    Hooks.driver.findElement(By.xpath(xpath)).click();
  }
}
```

* **Wait**: simple fixed wait.
* **Click by id/xpath**: element interaction through `Hooks.driver`.
