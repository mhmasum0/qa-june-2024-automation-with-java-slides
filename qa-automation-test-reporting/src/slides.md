---
theme: seriph
background: https://cover.sli.dev
title: Automation Test Reporting | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Automation Test Reporting | QAJune2024 Automation with Java
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

# QA Automation Test Reporting

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

# Why Automation Test Reporting?

- **Clear visibility:** into test execution and provides stakeholders with a comprehensive view of test coverage.
- **Efficiency in Debugging:** These tools offer detailed reports, including logs, screenshots, and error traces, making it easier to diagnose and fix issues, thereby reducing the time spent on debugging.

---
layout: center
---

# TestNG Report Listener Class

- org.testng.reporters.TestHTMLReporter
- org.testng.reporters.EmailableReporter2
- org.testng.reporters.FailedReporter

---
layout: center
---

# Extent Report

Official Website: [Extent Report](https://extentreports.com/)

Add the following dependency to your `pom.xml` file:

```xml  
    <dependency>
      <groupId>com.aventstack</groupId>
      <artifactId>extentreports</artifactId>
      <version>5.1.2</version>
    </dependency>
```

---
layout: center
---

# Extent Report Usage

```java
ExtentReports extent = new ExtentReports();

ExtentSparkReporter spark = new ExtentSparkReporter("target/Spark.html");
ExtentEmailReporter email = new ExtentEmailReporter("Email.html");

extent.attachReporter(spark);

ExtentTest extentTest = extent.createTest("MyFirstTest");
extentTest.log(Status.PASS, "This is a logging event for MyFirstTest, and it passed!");

extent.flush();
```

---
layout: center
---

# Extent Report with Screenshot

```java
ExtentTest extentTest = extent.createTest("MyFirstTest");
extentTest.log(Status.PASS, "This is a logging event for MyFirstTest, and it passed!");

TakesScreenshot screenshot = (TakesScreenshot) driver;
File source = screenshot.getScreenshotAs(OutputType.FILE);
File dest = new File("./Screenshots/screenshot.png");
FileUtils.copyFile(source, dest);
extentTest.addScreenCaptureFromPath(dest.getAbsolutePath());

// adding screenshots to log
extentTest.log(Status.INFO, "Screenshot", MediaEntityBuilder.createScreenCaptureFromPath(dest.getAbsolutePath()).build());
```




---
src: ../../pages/common/end.md
---