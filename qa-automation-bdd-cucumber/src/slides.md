---
theme: seriph
background: https://cover.sli.dev
title: BDD Cucumber JAVA | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  BDD Cucumber JAVA | QAJune2024 Automation with Java
author: Mahmudul Hasan Masum
drawings:
  persist: false
transition: slide-left
mdc: true
lineNumbers: true
fonts:
  sans: Outfit
  weights: '200,400,600'
  serif: Robot Slab
  mono: Fira Code
hideInToc: true
addons:
  - ../addons/mhmasum0
---

# BDD Cucumber JAVA

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/mhmasum0/qa-june-2024-automation-with-java-slides" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
hideInToc: true
---

# Agenda
<Toc />

---
layout: center
---

# Introduction to BDD

<C>Definition:</C>BDD is a software development approach that emphasizes collaboration between developers, QA, and non-technical or business participants in a software project.
<C>Purpose:</C> To improve communication, create shared understanding, and ensure the software meets business requirements.

---
layout: center
---

# Key Concepts of BDD

<C>User Stories:</C> Descriptions of features from an end-user perspective.
<C>Scenarios:</C> Detailed examples of user stories, outlining specific use cases.
<C>Gherkin Syntax:</C> A business-readable domain-specific language for describing software behavior.

---
layout: center
---

# Introduction to Cucumber

<C>Definition:</C> Cucumber is a tool for running automated tests written in plain language.
<C>Language:</C> Uses Gherkin syntax to define test cases.
<C>Integration:</C> Can be integrated with various programming languages like Java, Ruby, and JavaScript.

---
layout: center
---

# Gherkin Syntax

<br>

**Feature:** Describes the feature under test.
<br>
**Scenario:** Describes a specific use case.
<br>
**Steps:** Given, When, Then, And, But.
<br>

- Background: Common steps for all scenarios.
- Scenario Outline: Parameterized scenarios.
- Examples: Data tables for Scenario Outline. 
- Given: Sets up the initial state. 
- When: TDescribes an action. 
- Then: Describes an expected outcome. 
- And: Additional steps.

---
layout: center
---

# Example of Gherkin Syntax

```gherkin
Feature: Login Functionality
    Scenario: Valid Login
        Given User is on the login page
        When User enters valid username
        And User enters valid password
        Then User should be logged in successfully
```
```gherkin
Feature: User Login
    Scenario Outline: Login with multiple credentials
        Given User is on the login page
        When User enters "<username>" and "<password>"
        Then User should see "<result>"

    Examples:
        | username   | password | result                 |
        | user1      | pass123  | Welcome message        |
        | user2      | wrongpwd | Error: Invalid password |
        | invalidusr | pass123  | Error: Invalid username |

```

---
layout: center
---

# Benefits of BDD with Cucumber

<br>

**Improved Communication:** Common language understood by all stakeholders.
<br>**Clear Requirements:** Detailed and executable specifications.
<br>**Early Bug Detection:** Automated tests catch issues early.
<br>**Living Documentation:** Tests serve as up-to-date documentation.

---
layout: center
---

# Setting Up Cucumber

- **Install Cucumber:** Follow installation steps for your programming language.
- **Write Feature Files:** Use Gherkin syntax to create feature files.
- **Implement Step Definitions:** Code to automate the steps defined in feature files.
- **Run Tests:** Use Cucumber to execute the tests and validate behavior.

---
layout: center
---

# Add Cucumber Dependencies


Link to the [Cucumber Java](https://mvnrepository.com/artifact/io.cucumber/cucumber-java) and [Cucumber TestNG](https://mvnrepository.com/artifact/io.cucumber/cucumber-testng) dependencies.

Add the following dependencies to your `pom.xml` file for Maven projects:

```xml
<dependency>
    <groupId>io.cucumber</groupId>
    <artifactId>cucumber-java</artifactId>
    <version>7.20.1</version>
</dependency>
<dependency>
    <groupId>io.cucumber</groupId>
    <artifactId>cucumber-testng</artifactId>
    <version>7.20.1</version>
</dependency>
```

---
layout: center
---

# Create Feature Files

Create feature files with `.feature` extension using Gherkin syntax in the `src/test/resources/features` directory.

```gherkin
Feature: Login to SWAG Labs
    Scenario: Login with valid credentials
        Given User is on the login page
        When User enters username "standard_user" and password as "secret_sauce"
        Then User should be logged in successfully
```
<br><HL>Feature files for multiple data sets can use Scenario Outline and Examples.</HL>
```gherkin
Feature: Login to SWAG Labs
    Scenario Outline: Login with multiple credentials
        Given User is on the login page
        When User enters "<username>" and "<password>"
        Then User should see "<result>"

    Examples:
        | username              | password      | result       |
        | standard_user         | secret_sauce  | Products     |
        | locked_out_user       | secret_sauce  | Products     |
```

---
layout: center
---

# Implement Step Definitions

Create step definition classes to map Gherkin steps to Java code. These classes should be in the `src/test/java/stepdefinitions` package.

```java
class LoginPageDefinitions {
    @Given("User is on the login page")
    public void userIsOnLoginPage() {
        // Code to navigate to the login page
    }

    @When("User enters username {string} and password as {string}")
    public void userEntersCredentials(String username, String password) {
        // Code to enter username and password
    }

    @Then("User should be logged in successfully")
    public void userShouldBeLoggedIn() {
        // Code to verify successful login
    }
}
```

---
layout: center
---

# Run Cucumber Tests

Create a test runner class to execute the Cucumber tests. This class should be in the `src/test/java/runners` package.

```java
@CucumberOptions(features = "src/test/resources/features",
                 glue = "stepdefinitions",
                 plugin = {})
public class CucumberRunnerTests extends AbstractTestNGCucumberTests {
    
}
```


---
src: ../../pages/common/end.md
---