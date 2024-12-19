---
theme: seriph
background: https://cover.sli.dev
title: Postman API Testing | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Postman API Testing | QAJune2024 Automation with Java
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

# Postman API Testing

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

# Postman

Postman is a powerful API testing tool that simplifies the process of developing, testing, and documenting APIs.

<HL>Features:</HL>
- User-friendly interface for building and testing API requests.
- Supports various HTTP methods (GET, POST, PUT, DELETE, etc.).
- Automation of API tests with Postman Collections and Newman.
- Integration with CI/CD pipelines.
- Collaboration features for team environments.

---
layout: center
---

# Getting Started

1. Download and install Postman from [postman.com](https://www.postman.com/downloads/).
2. Create a free account
3. Create a workspace
4. Create a collection
5. Create a request

---
layout: center
---

# What is an API?

<C>API:</C>Stands for Application Programming Interface.
<Youtube id="-0MmWEYR2a8" width=300 height=150 />
<br><HL>Example:</HL>
- Weather App: Your weather app uses an API to get weather data from a weather service.
- Payment Processing: Online stores use APIs to connect to payment gateways like PayPal or Stripe.

---
layout: center
---

# Key Characteristics of APIs

- **Request**: A client sends a request to the server.
- **Response**: The server processes the request and sends a response back to the client.
- **Endpoint**: The URL where the API is located.
- **Method**: The HTTP method used to interact with the API (GET, POST, PUT, DELETE, etc.).
- **Headers**: Additional information sent with the request or response.
- **Body**: Data sent with the request or response (e.g., JSON, XML).
- **Status Code**: A code that indicates the success or failure of the request (e.g., 200 OK, 404 Not Found).

---
layout: center
---

# HTTP Methods

- **GET**: Retrieve data from the server.
- **POST**: Send data to the server.
- **PUT**: Completely updating data (e.g., updating all user details).
- **PATCH**: Partially updating data (e.g., updating only the user's email).
- **DELETE**: Delete data from the server.

# HTTP Status Codes

Resouce: [HTTP Status Code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

---
layout: center
---

# Postman Collection

A Postman Collection is a group of API requests that can be organized into folders and subfolders.

---
layout: center
---

# Postman Variables

Key Value Pairs that can be used in requests.

- **Key**: variable name
- **Value**: variable value

<br><HL>Example:</HL>
- Suppose, you have a variable `base_url` with value `https://api.example.com`. 
- You can use this variable in your requests like this: `{{base_url}}/users`.

---
layout: center
---

# Postman Variable Priority

1. **Local Variables**: Defined in the request.
2. **Environment Variables**: Defined in the environment.
3. **Collection Variables**: Defined in the collection.
4. **Global Variables**: Defined globally.

Resources: [Postman Variables](https://blog.scottlogic.com/2020/09/04/variableScopes.html)

---
layout: center
---

# Set Variables from scripts

<C>Syntax:</C>
- Local: `pm.variables.set("variable_name", "variable_value");`
- Environment: `pm.environment.set("variable_name", "variable_value");`
- Collection: `pm.collectionVariables.set("variable_name", "variable_value");`
- Global: `pm.globals.set("variable_name", "variable_value");`

---
layout: center
---

# Get Variables from scripts

<C>Syntax:</C>
- Local: `pm.variables.get("variable_name");`
- Environment: `pm.environment.get("variable_name");`
- Collection: `pm.collectionVariables.get("variable_name");`
- Global: `pm.globals.get("variable_name");`

---
src: ../../pages/common/end.md
---