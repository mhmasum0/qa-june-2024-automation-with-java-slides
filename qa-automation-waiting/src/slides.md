---
theme: seriph
background: https://cover.sli.dev
title: Selenium WebDriver Implicit Wait, Explicit Wait and Fluent Wait | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Selenium WebDriver Implicit Wait, Explicit Wait and Fluent Wait | QAJune2024 Automation with Java
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

# Selenium WebDriver Implicit Wait, Explicit Wait and Fluent Wait

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

# PageLoadTimeOut

> A timeout value that specifies the maximum amount of time Selenium will wait for a web page to load.

<br>

> If the page does not load within the specified time, Selenium will throw an exception.

## When to use it?

- When you are unsure how long a web page will take to load.
- When you want to prevent your tests from hanging indefinitely.

```java
driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(3));
driver.get("https://learn-automation.com/selenium-webdriver-tutorial-for-beginners/");

```

---
layout: center
---

# Code Example: PageLoadTimeOut

```java
class PageLoadTimeOutExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(20));

        driver.get("https://learn-automation.com/selenium-webdriver-tutorial-for-beginners/");
        System.out.println(driver.getTitle());
        driver.quit();
    }
}
```


---
layout: center
---

# Implicit Wait

<B>Purpose:</B> Implicit wait is used to instruct the WebDriver to wait for a certain amount of time before throwing a NoSuchElementException. This is useful when elements take time to load or become visible on the web page.
<br><B>Global Setting:</B> Once set, the implicit wait time is applied to all subsequent WebDriver element lookups. This means every time an element is searched for, WebDriver will wait up to the specified time before failing.

<B>Syntax:</B>  `driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));`

---
layout: center
---

# How Implicit Wait Works?

<B>Duration:</B> The duration is specified in seconds, and it is set only once. For example, if the implicit wait is set to 10 seconds, WebDriver will wait up to 10 seconds for each element search.

<br><B>Default Behavior:</B> By default, WebDriver does not have any implicit wait set. If you don't set an implicit wait, WebDriver will immediately throw an exception if an element is not found.
<B>Overriding with Explicit Wait:</B> Implicit wait can be overridden by explicit waits in specific scenarios where a different waiting time is required. Explicit waits allow for more fine-grained control over waiting conditions.

---
layout: center
---

# Code Example: Implicit Wait

```java
class ImplicitWaitExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(3));

        driver.get("https://www.facebook.com/");
        System.out.println(driver.getTitle());

        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

        driver.findElement(By.xpath("//input[@id='email']")).sendKeys("deb.nexxvali@gmail.com");
        driver.findElement(By.xpath("//input[@id='pass']")).sendKeys("deb.nexxvali@gmail.com");
        driver.findElement(By.xpath("//button[text()='']")).click();

        driver.quit();
    }
}
```

---
layout: center
---

# Explicit Wait

<B>Purpose:</B> Explicit wait is used to pause the execution of the script until a certain condition is met or the maximum specified time has elapsed. This is particularly useful when dealing with elements that may take unpredictable amounts of time to appear or become interactable.
<br><B>Condition-Based Waiting:</B> Unlike implicit wait, explicit wait allows you to wait for specific conditions to be true. Common conditions include the presence of an element, visibility of an element, element to be clickable, etc.
<B>WebDriverWait Class:</B> Explicit wait is implemented using the WebDriverWait class in conjunction with ExpectedConditions.

<br><B>Syntax:</B>:

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("someId")));
```


---
layout: center
---

# Why Use Explicit Wait?

<B>Flexibility and Control:</B> Explicit waits provide greater flexibility and control over the waiting mechanism. You can specify the exact conditions under which the wait should proceed or time out, making tests more robust and reliable.
<br><B>Timeouts:</B> Explicit wait will wait for the specified amount of time (in seconds) before throwing a TimeoutException if the condition is not met. You can also specify polling intervals to check the condition at regular intervals.
<B>Avoid Overusing Implicit Waits:</B> It’s generally a good practice to use explicit waits for elements that have variable load times or require specific conditions to be met. Combining implicit and explicit waits should be done cautiously to avoid conflicts.

---
layout: center
---

# Scenario of Using Explicit Wait

<B>Commonly Used Conditions:</B>

- presenceOfElementLocated
- visibilityOfElementLocated
- elementToBeClickable
- textToBePresentInElement
- alertIsPresent

## Example Scenarios:

- Waiting for an element to become clickable before attempting a click.
- Waiting for a specific text to appear in an element before proceeding.
- Waiting for an alert to be present and accepting it.

---
layout: center
---

# Code Example: Explicit Wait

```java
class ExplicitWaitExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("http://seleniumpractise.blogspot.in/2016/08/how-to-use-explicit-wait-in-selenium.html");

        driver.findElement(By.xpath("//button[text()='Click me to start timer']")).click();
        
        // By default, it  accepts in Seconds
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(15));

        // Here we will wait until element is not visible, if element is visible then it will return web element
        // or else it will throw exception
        WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//p[text()='WebDriver']")));

        boolean status = element.isDisplayed();
        
        if (status) {
            System.out.println("===== WebDriver is visible======");
        } else {
            System.out.println("===== WebDriver is not visible======");
        }
    }
}
```

---
layout: center
---

# Fluent Wait

<B>Purpose:</B> FluentWait is used to wait for a condition with a customized timeout and polling interval. It also allows configuring what exceptions to ignore while waiting for the condition to be met.
<br><B>Customization:</B> FluentWait provides several options to customize the wait:

- Timeout: The maximum amount of time to wait for a condition.
- Polling Interval: How often to check the condition.
- Ignored Exceptions: Specify which exceptions to ignore during the wait period (e.g., NoSuchElementException).

---
layout: center
---

# Code Example: Fluent Wait

```java

import com.google.common.base.Function;

class FluentWaitExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("http://seleniumpractise.blogspot.in/2016/08/how-to-use-explicit-wait-in-selenium.html");

        driver.findElement(By.xpath("//button[text()='Click me to start timer']")).click();

        Wait<WebDriver> wait = new FluentWait<>(driver)
                .withTimeout(Duration.ofSeconds(30))
                .pollingEvery(Duration.ofSeconds(2))
                .ignoring(NoSuchElementException.class);

        WebElement element = wait.until(new Function<WebDriver, WebElement>() {
            public WebElement apply(WebDriver driver) {
                WebElement ele = driver.findElement(By.xpath("//p[text()='WebDriver']"));
                return ele;
            }
        });

        boolean status = element.isDisplayed();

        if (status) {
            System.out.println("===== WebDriver is visible======");
        } else {
            System.out.println("===== WebDriver is not visible======");
        }
    }
}
```


---
src: ../../pages/common/end.md
---