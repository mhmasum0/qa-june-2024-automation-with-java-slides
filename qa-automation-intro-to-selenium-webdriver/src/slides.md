---
theme: seriph
background: https://cover.sli.dev
title: Introduction to Selenium Webdriver | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Introduction to Selenium Webdriver | QAJune2024 Automation with Java
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

# Introduction to Selenium Webdriver

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

# Selenium

- Selenium is an open-source, automated testing tool used to test web applications across multiple browsers.

Learn more about Selenium [here](https://www.selenium.dev/)


---
layout: center
---

# ChromeDriver Download

- Download ChromeDriver from [here](https://sites.google.com/chromium.org/driver/)

- Windows Platform: Download `win64` version
- Mac Apple Silicon: Download `mac-arm64` version
- Mac Intel: Download `mac-x64` version

---
layout: center
---

# Code Example of Selenium Webdriver

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTest {
    public static void main(String[] args) {
        // Windows Example: System.setProperty("webdriver.chrome.driver", "C:\\path\\to\\chromedriver.exe");
        // Mac Example: System.setProperty("webdriver.chrome.driver", "/path/to/chromedriver");
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");

        WebDriver driver = new ChromeDriver();
        driver.get("https://www.google.com");
        
        // Perform some actions
        driver.manage().window().maximize();
        System.out.println(driver.getTitle());
        
        // New way of using Selenium Webdriver
        
        // WebDriver driver = new ChromeDriver();
        // driver.get("https://www.google.com");
        // driver.manage().window().maximize();
        // System.out.println(driver.getTitle());
    }
}
```


---
src: ../../pages/common/end.md
---