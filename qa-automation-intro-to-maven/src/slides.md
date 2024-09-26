---
theme: seriph
background: https://cover.sli.dev
title: Introduction to Maven | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Introduction to Maven | QAJune2024 Automation with Java
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

# Introduction to Maven

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

# What is Maven?

- Maven is an open-source build tool developed by the Apache Group.
- Used to build, publish, and deploy various projects.
- Written in Java, but supports projects in other languages like C#, Scala, Ruby, etc.


---

# Maven Repository

- Maven repositories contain <HL>packaged JAR files and metadata</HL>.
- Three types of repositories: Local, Remote, and Central.
- <HL>Local Repository</HL>: This is the local cache on your development machine where Maven stores dependencies that it has downloaded. By default, it's located in the .m2 directory in your user home folder. Maven first checks this repository for dependencies before attempting to download them from remote repositories.
- <HL className="text-orange-500 bg-orange-100 p-1">Remote Repository</HL>: These are repositories hosted on remote servers from where Maven downloads dependencies over the internet. Examples of remote repositories include Maven Central, JCenter, and custom repositories hosted by organizations or individuals. When you specify a dependency in your project's pom.xml file, Maven looks for it in these remote repositories if it's not found in the local repository.
- <HL className="text-red-500 bg-red-100 p-1">Central Repository (Maven Central)</HL>: This is the default repository used by Maven if no other repositories are specified. It contains a vast collection of open-source libraries and plugins that are commonly used in Java projects. Maven Central is a remote repository that's publicly available and maintained by the Maven community.

---
layout: center
---
# POM (Project Object Model)

- POM files contain project and configuration details in <HL>XML format</HL>.
- Describes project, versioning, and configuration management.
- Located in the project home directory.

## Dependencies and Repositories

- Dependencies are Java libraries needed for the project.
- Repositories store packaged JAR files.
- Maven downloads dependencies from Central Repository if not found in Local Repository.

---
layout: center
---

## Maven Lifecycle, Phases, and Goals

- Build Life Cycles consist of build phases and goals.
- Each phase contains goals responsible for specific tasks.
- Maven executes phases and goals during the build process.

## Maven Plugins

- Maven Plugins contain groups of goals.
- Used to perform specific tasks during the build process.
- Can use standard plugins or implement custom ones in Java.

---
layout: center
---

## Maven Architecture

- Maven architecture includes POM file, Maven Repository, Dependencies, Plugins, and Build Life Cycles.
- POM file contains project configuration.
- Maven downloads dependencies and executes build phases according to the POM.

## Maven Build Lifecycle

- Maven has three built-in build life cycles: Default, Clean, and Site.
- Each life cycle consists of various build phases.
- Phases include Compile, Test, Package, Integration-test, Verify, Install, and Deploy.

---
layout: center
---

## Advantages of Maven

- Maven simplifies project management processes.
- Increases performance and efficiency in project building.
- Automates the task of downloading dependencies.
- Provides easy access to project information and simplifies building in different environments.

<br>

> Configure IntelliJ IDEA to download all the sources and javadoc from maven.


---
src: ../../pages/common/end.md
---