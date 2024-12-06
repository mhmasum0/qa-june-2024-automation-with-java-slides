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
- And, But: Additional steps.

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
src: ../../pages/common/end.md
---