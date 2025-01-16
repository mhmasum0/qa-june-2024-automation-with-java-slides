---
theme: seriph
background: https://cover.sli.dev
title: Mobile app testing with Appium | QAJune2024 Automation with Java
titleTemplate: '%s'
info: |
  Mobile app testing with Appium | QAJune2024 Automation with Java
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

# Mobile app testing with Appium

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

# What is Appium?

> Appium is an open-source project for automating native, mobile web, and hybrid applications on iOS mobile, Android mobile, and Windows desktop platforms.

<img width="600" src="./images/appium.png">

---
layout: center
---

# Environment Setup for Appium

1. Download Android SDK & Tools: [Link](https://developer.android.com/studio)
2. Set ANDROID_HOME environment variable. Example: `C:\Users\{username}\AppData\Local\Android\Sdk` for Windows and `/Users/{username}/Library/Android/sdk` for macOS
3. Add `platform-tools` to the PATH environment variable. Example: `C:\Users\{username}\AppData\Local\Android\Sdk\platform-tools` for Windows and `/Users/{username}/Library/Android/sdk/platform-tools` for macOS
4. Add `tools` to the PATH environment variable. Example: `C:\Users\{username}\AppData\Local\Android\Sdk\tools` for Windows and `/Users/{username}/Library/Android/sdk/tools` for macOS
5. Add emulator device using AVD Manager from Android Studio or use a real device

---
layout: center
---

# How to add environment variables?

1. Windows: `Control Panel > System and Security > System > Advanced system settings > Environment Variables`
1. macOS: `~/.bash_profile` or `~/.zshrc` file. Example: `export ANDROID_HOME=/Users/{username}/Library/Android/sdk` and `export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools`
  - Run `source ~/.bash_profile` or `source ~/.zshrc` to apply changes
  - Run command `echo $ANDROID_HOME` to verify the environment variable 
1. Run command `adb devices` to verify the Android setup
Note: To show hidden files in macOS, press `Cmd + Shift + .`


---
layout: center
---

# Install Appium

1. Install Node.js from [nodejs.org](https://nodejs.org)
2. Install Appium using npm `npm install -g appium`
3. Install Appium Doctor `npm install -g appium-doctor`
4. Verify Appium installation `appium --version`
5. Install Appium Inspector: [Link](https://github.com/appium/appium-inspector/releases)

## Install Appium Driver

- `appium driver list` to see available drivers
- `appium driver install <driver-name>` to install a driver
- Android: `appium driver install uiautomator2`
- iOS: `appium driver install xcuitest`

- `appium-doctor --android` to verify Android setup
- `appium-doctor --ios` to verify iOS setup

---
layout: center
---

# Add Appium Dependencies

1. Add Appium Java Client dependency in `pom.xml` file.<br>
Link: [Maven Repository](https://mvnrepository.com/artifact/io.appium/java-client)
```xml
<dependency>
    <groupId>io.appium</groupId>
    <artifactId>java-client</artifactId>
    <version>9.3.0</version>
</dependency>
```

---
layout: center
---

# Appium UIAutomator

Documentation: [Link](https://github.com/appium/appium-uiautomator2-driver)

UiAutomator2 options for installed app:
```java
UiAutomator2Options options = new UiAutomator2Options()
    .setDeviceName("emulator-5554")
    .setAppPackage("com.android.settings")
    .setAppActivity("com.android.settings.Settings");

AndroidDriver androidDriver = new AndroidDriver(new URL("http://127.0.0.1:4723/"), options);
```



---
layout: center
---



---
src: ../../pages/common/end.md
---