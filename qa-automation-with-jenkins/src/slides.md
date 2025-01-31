---
theme: seriph
background: https://cover.sli.dev
title: TestNG Tests with Jenkins | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  TestNG Tests with Jenkins | QAJune2024 Automation with Java
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

# TestNG Tests with Jenkins

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

# Why Jenkins?

- **Automation:** Jenkins is an open-source automation server that can be used to automate all sorts of tasks related to building, testing, and delivering or deploying software.
- **Integration:** Jenkins can be used to integrate various DevOps stages, including building, testing, and delivering software.
- **Extensible:** Jenkins can be extended via plugins to support building, deploying, and automating any project.

---
layout: center
---

# Jenkins Installation

Official Website: [Jenkins](https://www.jenkins.io)

- Install Jenkins on Windows: https://www.jenkins.io/doc/book/installing/windows/
- Install Jenkins on macOS: https://www.jenkins.io/doc/book/installing/macos/
- http://127.0.0.1:8080/ (Default Jenkins URL)

---
layout: center
---

# Maven Plugin Installation in Jenkins

- Go to Jenkins Dashboard
- Click on Manage Jenkins
- Click on Plugins
- Click on Available plugins
- Search for Maven Integration plugin and install it
- Search for TestNG plugin and install it
- Search for GitHub integration plugin and install it

---
layout: center
---

# Configure Maven in Jenkins

- Go to Jenkins Dashboard
- Click on Manage Jenkins
- Click on Tools
- Go to Maven installations section
- Click on Add Maven
- Provide the name "M2_HOME" and select the Maven version
- Click on Save

---
layout: center
---

# Create a New Jenkins Job

- Go to Jenkins Dashboard
- Click on New Item
- Provide the item name
- Select the Maven project
- Click on OK
- Go to the Source Code Management section
- Select Git
- Provide the repository URL
- Provide the Branch Specifier
- Go to the Build section
- Provide the POM.xml path
- Provide the Goals and options (clean test)
- Click on Save


---
layout: center
---

# Maven Plugin Installation in POM.xml

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <configuration>
        <suiteXmlFiles>
            <suiteXmlFile>
                testng.xml
            </suiteXmlFile>
        </suiteXmlFiles>
    </configuration>
</plugin>
```





---
src: ../../pages/common/end.md
---