# ProjectFramework
# Explain Your Framework to Me 🫠 👇

## Project Overview

We are using a **Maven Project** to manage all dependencies required by our framework and leveraging the **TestNG** framework. Alongside TestNG, we also use **Cucumber** to implement the **BDD (Behavior Driven Development)** approach using Gherkin keywords like:

> **Given**, **When**, **And**, **But**, **Then**

Business Analysts are actively involved in writing feature files along with the testing team.

---

## Folder Structure

### Folder 1: `src/test/java` 📁

- **Package: `runner`**
  - Contains `Runner.java` file.
  - Provides the path to feature files and uses the `glue` keyword to connect with the `stepDefinitions`.
  - Uses tags like `@smoke`, `@sanity` to selectively run tests.

- **Package: `features`**
  - Contains various feature files like `Login.feature`, `Logout.feature`, etc.
  - **Scenario** keyword: For running a single set of data.
  - **Scenario Outline** with **Examples** keyword: For running multiple sets of data (common interview question: Scenario vs Scenario Outline).
  - Tags like `@smoke`, `@sanity` are used to organize tests.

- **Package: `stepDefinitions`**
  - Contains Java classes like `LoginTest.java`, `LogOutTest.java` corresponding to features.

- **Package: `hooks`**
  - Contains `MyHooks.java`.
  - **beforeScenario()** method: Launches the Chrome browser before each scenario (annotated with `@Before`).
  - **afterScenario()** method: Quits the browser after each scenario (annotated with `@After`).

---

### Folder 2: `src/test/resources` 📁

- **Package: `utilities`**
  - Contains `data.properties` file (storing dev and test URLs).
  - Contains `extent.properties` file for Extent Reports configuration.

---

### Folder 3: `src/main/java` 📁

- **Package: `pageobjects`**
  - Contains all page object classes where we store locators for different web pages.

---

## Important Files

- **testng.xml**
  - Maintained to organize and run multiple tests together.
  - Properly configured in `pom.xml`.
  - Can be executed via Maven command.
  - (Tip: Memorize the structure of `testng.xml` as interviewers may ask you to write a sample.)

- **Jenkins Integration**
  - Our project is integrated with Jenkins.
  - We have provided the `pom.xml` path.
  - Tests are triggered using `mvn clean test` command.

- **GitHub**
  - All source code is maintained and version-controlled in GitHub. 🧑‍💻

---

> **Note:** This framework structure promotes scalability, reusability, and collaboration between testers and business analysts using the BDD approach.
