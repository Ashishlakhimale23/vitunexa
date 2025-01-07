# BatteryPermissionHelper
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
[![Android Build](https://github.com/WaseemSabir/BatteryPermissionHelper/actions/workflows/build.yml/badge.svg)](https://github.com/WaseemSabir/BatteryPermissionHelper/actions/workflows/build.yml)
[![Unit Tests](https://github.com/WaseemSabir/BatteryPermissionHelper/actions/workflows/tests.yml/badge.svg)](https://github.com/WaseemSabir/BatteryPermissionHelper/actions/workflows/tests.yml)
[![API](https://img.shields.io/badge/API-16%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=16)

An Android Library to detect battery optimizations settings and navigate the user to the relevant screens so that they can whitelist the app. This will prevent the app from getting killed in the background due to Battery Optimization Managers. The library supports multiple OEMs.

## Installation
### Gradle
Add this to your module's build.gradle file:
```gradle
dependencies {
    // ... other dependencies
    implementation 'com.waseemsabir:betterypermissionhelper:1.0.3'    
}
```

### Maven
```maven
<dependency>
    <groupId>com.waseemsabir</groupId>
    <artifactId>betterypermissionhelper</artifactId>
    <version>1.0.3</version>
</dependency>
```

Other instructions for installation can be viewed [here](https://central.sonatype.com/artifact/com.waseemsabir/betterypermissionhelper/1.0.0).

## Usuage
```kotlin
private val batteryPermissionHelper = BatteryPermissionHelper.getInstance()

// check whether or not Battery Permission is Available for Device
val isBatteryPermissionAvailable = batteryPermissionHelper.isBatterySaverPermissionAvailable(context = context, onlyIfSupported = true)

// Show a dialog based on availability (Implementation left to Dev) and OnClick open permission manager
dialog.setOnClickListener {
    batteryPermissionHelper.getPermission(this, open = true, newTask = true)
}
```


## Relevant Work

* [AutoStarter](https://github.com/judemanutd/AutoStarter)
* [dont-kill-my-app](https://github.com/urbandroid-team/dont-kill-my-app)
