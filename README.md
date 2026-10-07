# Pointfix for Android

Point at a UI problem in your running Android app, describe the fix, and your local coding agent makes it. Pointfix rebuilds and relaunches the app, and you review the change before anything is committed.

The SDK is published to Maven Central as a compiled library.

## Install

```kotlin
dependencies {
    debugImplementation("dev.pointfix:pointfix-android:0.2.0")
    releaseImplementation("dev.pointfix:pointfix-android-noop:0.2.0")
}
```

The no-op artifact has the same API and no capture code, so release builds ship nothing extra.

## Use

```kotlin
import dev.pointfix.Pointfix

capture = Pointfix.install(this, "Shop") // after setContent; close it in onDestroy
```

Long-press an element in a debug build, describe the change and send. You also need the Pointfix bridge (`brew install pointfix-dev/tap/pointfix`, then `pointfix start`) and `adb reverse tcp:4747 tcp:4747` for a device.

Docs: https://pointfix.dev/docs/android
