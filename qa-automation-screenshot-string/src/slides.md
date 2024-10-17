---
theme: seriph
background: https://cover.sli.dev
title: Selenium WebDriver ScreenShots and String | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Selenium WebDriver XPATH Axes | QAJune2024 Automation with Java
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

# Selenium WebDriver ScreenShots and String

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

# String Escape Sequences

- `\n` - Creates a new line
- `\t` - Inserts a tab
- `\\` - Prints a backslash
- `\"` - Prints a double quotation mark
- `\'` - Prints a single quotation mark

<C>Example:</C>

```java
class StringEscapeSequences {
    public static void main(String[] args) {
        System.out.println("Hello\nWorld");
        System.out.println("Hello\tWorld");
        System.out.println("Hello\\World");
        System.out.println("Hello\"World");
        System.out.println("Hello'World");
    }
}
```

---
layout: center
---

# String Concatenation

- `+` operator is used to concatenate two strings

<C>Example:</C>

```java
class StringConcatenation {
    public static void main(String[] args) {
  
        // variable at the beginning
        String firstName = "Mahmud";
        System.out.println(firstName + " is a trying to learn Java");
        
        // variable at the end
        System.out.println("Hello " + firstName);
        
        // variable in the middle
        System.out.println("Hello " + firstName + "!");
    }
}
```

---
layout: center
---

# String Methods

- `length()` - Returns the length of the string
- `toUpperCase()` - Converts the string to uppercase
- `toLowerCase()` - Converts the string to lowercase
- `charAt(int index)` - Returns the character at the specified index

<C>Example:</C>

```java
class StringMethods {
    public static void main(String[] args) {
        String str = "Hello World";
        System.out.println(str.length());
        System.out.println(str.toUpperCase());
        System.out.println(str.toLowerCase());
        System.out.println(str.charAt(6));
    }
}
```

---
layout: center
---

# Why do we need ScreenShots?

- To capture the state of the application at a particular moment
- To debug the test case
- To check the visual appearance of the application
- To check the cross-browser compatibility

---
layout: center
---

# WebDriver ScreenShots Dependency


- Dependency: `commons-io`

Link: [https://mvnrepository.com/artifact/commons-io/commons-io](https://mvnrepository.com/artifact/commons-io/commons-io)

```xml
<dependency>
    <groupId>commons-io</groupId>
    <artifactId>commons-io</artifactId>
    <version>2.17.0</version>
</dependency>
```

---
layout: center
---

# WebDriver ScreenShots Code Example

```java
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import java.io.File;
import java.io.IOException;

public class ScreenShotExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.google.com");
        TakesScreenshot screenshot = (TakesScreenshot) driver;
        try {
            File source = screenshot.getScreenshotAs(OutputType.FILE);
            FileUtils.copyFile(source, new File("./Screenshots/screenshot.png"));
        } catch (IOException e) {
            System.out.println("Exception while taking screenshot " + e.getMessage());
        }
        driver.quit();
    }
}
```

---
src: ../../pages/common/end.md
---