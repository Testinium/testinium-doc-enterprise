# CucumberRunner

**Purpose:** Starts Cucumber tests with the JUnit 4 runner. Specifies the features path, glue packages, and minimal reporting plugins.

```java
@RunWith(io.cucumber.junit.Cucumber.class)
@CucumberOptions(
  features = "src/test/resources/features",
  glue = { "com.saha.cucumber.step", "com.saha.cucumber.driver" },
  plugin = { "pretty", "summary" },
  monochrome = true
)
public class CucumberRunner {}
```

* **Glue**: `Steps` and `Hooks` packages.
* **Plugin**: `pretty` & `summary`.
