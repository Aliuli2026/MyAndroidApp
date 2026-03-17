# MyAndroidApp

一个简单的 Android 示例应用，使用 GitHub Actions 自动编译 APK。

## 项目结构

```
MyAndroidApp/
├── app/
│   ├── src/main/
│   │   ├── java/com/example/myapp/
│   │   │   └── MainActivity.java
│   │   ├── res/
│   │   │   ├── layout/activity_main.xml
│   │   │   └── values/
│   │   │       ├── colors.xml
│   │   │       ├── strings.xml
│   │   │       └── themes.xml
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── .github/
│   └── workflows/
│       └── build.yml        ← GitHub Actions 自动编译配置
├── gradle/wrapper/
├── build.gradle
├── settings.gradle
└── gradle.properties
```

## GitHub Actions 自动编译

每次向 `main` 或 `master` 分支推送代码时，会自动触发构建：

1. ✅ 编译 **Debug APK**
2. ✅ 编译 **Release APK**（未签名）

构建完成后，可在 GitHub Actions 页面的 **Artifacts** 中下载 APK 文件。

## 本地构建

```bash
# 编译 Debug APK
./gradlew assembleDebug

# 编译 Release APK
./gradlew assembleRelease
```

APK 输出路径：`app/build/outputs/apk/`

## 环境要求

- Android SDK compileSdk: 34
- minSdk: 24 (Android 7.0+)
- Java: 17
- Gradle: 8.4
