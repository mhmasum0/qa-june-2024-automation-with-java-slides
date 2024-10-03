---
theme: seriph
background: https://cover.sli.dev
title: Selenium WebDriver Locators | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Selenium WebDriver Locators | QAJune2024 Automation with Java
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

# Selenium WebDriver Locators

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

# Elements on the Web Page

<img src="./images/element.png">

---
layout: center
---

# What is a Locator?

> Locator is a technique to find any element on web page.

<img width="600" src="./images/locator.png">

---
layout: center
---

# Types of Locators

- ID
- Name
- ClassName
- XPath
- CSS Selector
- PartialLinkText
- LinkText
- TagName

---
layout: center
---

# Dynamic XPath in Selenium

<C>Using single attribute</C>

`//tagname[@attribute-name=’value1’]`

<C>Example</C>

`//a[@href=’http://www.google.com’]` <br>
`//input[@id=’name’]` <br>
`//input[@name=’username’]` <br>
`//img[@alt=’sometext’]`

---
layout: center
---

# Dynamic XPath using multiple attributes

`//tagname[@attribute1=’value1’][attribute2=’value2’]`

<C>Example</C>

`//a[@id=’id1’][@name=’value1’]` <br>
`//img[@src=’’][@href=’’]` <br>
`//img[@src=’’ AND @href=’’]` <br>
`//img[@src=’’ OR @href=’’]`

---

# Dynamic XPath using contains()

> `contains()` is a function in XPath which is used to search for a specified text in the attribute value.

`//tagname[contains(@attribute, ‘value’)]`

<C>Example</C>

`//input[contains(@id,’’)]` <br>
`//input[contains(@name,’’)]` <br>
`//a[contains(@href,’’)]` <br>
`//img[contains(@src,’’)]`

---

# Dynamic XPath using starts-with()

> The XPath `starts-with()` function is used to find the element in which the attribute value starts with some specific character or a sequence of characters.

`//tagname[starts-with(@attribute, ‘value’)]`

<C>Example</C>

`//input[starts-with(@id,’’)]` <br>
`//input[starts-with(@name,’’)]` <br>
`//a[starts-with(@href,’’)]` <br>
`//img[starts-with(@src,’’)]`

---

# Dynamic XPath using text()

> The XPath `text()` function is used to find the element in which the text is present.

`//tagname[text()=’text’]`

<C>Example</C>

`//a[text()=’Google’]` <br>
`//a[text()=’Gmail’]` <br>
`//a[text()=’Images’]` <br>
`//a[text()=’Sign in’]`
`//*[text()=’text’]`

> `*` is used to represent all the elements.

---
src: ../../pages/common/end.md
---