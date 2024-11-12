---
theme: seriph
background: https://cover.sli.dev
title: Selenium WebDriver Chrome Options| QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Selenium WebDriver Chrome Options | QAJune2024 Automation with Java
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

# Selenium WebDriver Chrome Options

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

# Chrome Options

- ChromeOptions is separate in Selenium which will help to manage options specific to ChromeDriver.
- ChromeOptions is class extends MutableCapabilities.
- It added after Selenium 3.6.0
## Why it is required?

- If you want to make/change any settings of browser then you can use this class.
- By default Selenium starts fresh profile of browser which don't have any settings, cookies, history and so on.

---
layout: center
---

# Chrome Options: Use Cases

`Chrome Options options = new ChromeOptions()`

- To add new extension
  - `options.addExtensions(new File("/path/to/extension.crx"));`
- To add binary path
    - `options.setBinary(new File("/path/to/chrome"));`
- To accept untrusted certificate
    - `options.setAcceptInsecureCerts(true);`
- To Disable infobar
    - `options.addArguments("disable-infobars");`
- For Headless Mode
    - `options.addArguments("--headless");`
    - `options.addArguments("--disable-gpu");`

---
layout: center
---

# Chrome Options: Code Example

> To download extension.crx file, you can visit [Chrome Web Store](https://chrome.google.com/webstore/category/extensions) and download any extension using [CRX Extractor](https://chromewebstore.google.com/detail/crx-extractordownloader/ajkhmmldknmfjnmeedkbkkojgobmljda)

```java
class ChromeOptionsExample {
  public static void main(String[] args) {
    ChromeOptions options = new ChromeOptions();
    options.addExtensions(new File("/Users/mahmud/Downloads/extension.crx"));

    // Add chrome switch to start browser in maximized mode
    options.addArguments("--start-maximized");

    // Add chrome switch to set browser language (here setting as Bangla)
    options.addArguments("--lang=en");

    // Add chrome switch to disable tooltips
    options.addArguments("--disable-popup-blocking");

    WebDriver driver = new ChromeDriver(options);
  }
}
```

---
layout: center
---

# Selenium WebDriver File Upload: Code Example

```java
class FileUploadExample {
  public static void main(String[] args) {
    WebDriver driver = new ChromeDriver();
    driver.get("https://www.lambdatest.com/selenium-playground/upload-file-demo");
    
    WebElement chooseFile = driver.findElement(By.id("file"));
    chooseFile.sendKeys("/Users/mahmud/Downloads/github-1-1-1.png");
    
    String message = driver.findElement(By.id("error")).getText();
    
    System.out.println(message);
  }
}
```


---
src: ../../pages/common/end.md
---