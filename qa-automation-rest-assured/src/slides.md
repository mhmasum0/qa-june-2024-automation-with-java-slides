---
theme: seriph
background: https://cover.sli.dev
title: Rest Assured | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Rest Assured | QAJune2024 Automation with Java
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

# Rest Assured

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

# Rest Assured

- REST Assured is a Java library.
- It is used to test RESTful APIs.
- Allows for writing readable, maintainable tests.

---
layout: center
---

# Why Use REST Assured?

- Simplifies interaction with REST APIs.
- Supports HTTP methods (GET, POST, PUT, PATCH, DELETE).
- Integrates well with testing frameworks (JUnit, TestNG).
- It supports BDD framework

---
layout: center
---

# Add Dependency

Link: [Maven Repository](https://mvnrepository.com/artifact/io.rest-assured/rest-assured)

```xml
<dependency>
    <groupId>io.rest-assured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>5.5.0</version>
    <scope>test</scope>
</dependency>
```

---
layout: center
---

# Basic Code Example

```java

class RestAssuredExample {

    @Test
    public void testGet() {
        Response response = RestAssured.get("https://reqres.in/api/users?page=2");

        System.out.println(response.getStatusCode());
        System.out.println(response.getStatusLine());

        System.out.println(response.getBody().asString());
        System.out.println(response.getHeader("Content-Type"));
        System.out.println(response.getTime());

        int statusCode = response.getStatusCode();
        Assert.assertEquals(statusCode, 200);
    }
}
```

---
layout: center
---

# REST Assured Code Example 2

```java

import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

class RestAssuredExample2 {

    @Test
    public void test2() {
        get("https://reqres.in/api/users?page=2")
                .then()
                .statusCode(200)
                .body("data[1].id", equalTo(8))
                .body("data.first_name", hasItem("Byron"));

    }
}
```

---
layout: center
---

# REST Assured Code Example 3

```java
class RestAssuredExample3 {
    @Test
    public void testPost() {
        baseURI = "https://reqres.in/api/";
        given()
                .header("Content-Type", "application/json")
                .body("{\n" +
                        "    \"name\": \"mahmud\",\n" +
                        "    \"job\": \"instructor\"\n" +
                        "}")
                .when()
                .post("users")
                .then()
                .statusCode(201)
                .body("name", equalTo("mahmud"))
                .body("job", equalTo("instructor"));
    }
}
```

---
layout: center
---

# Create a custom JSON Object

<B>Add Dependency</B>

```xml
<dependency>
    <groupId>com.googlecode.json-simple</groupId>
    <artifactId>json-simple</artifactId>
    <version>1.1.1</version>
</dependency>
```

## Code Example

```java
JSONObject request = new JSONObject();
request.put("name", "mahmud");
request.put("job", "instructor");
System.out.println(request.toJSONString());
```


---
layout: center
---

# Resources

- [Rest Assured Wiki](https://github.com/rest-assured/rest-assured/wiki/Usage)
- [JSONPath Finder](https://jsonpathfinder.com/)
- [JSONPath](https://jsonpath.com/)

---
src: ../../pages/common/end.md
---