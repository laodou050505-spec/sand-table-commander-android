# Tripo craft — Android Gradle 工程（Unity 导出）

本仓库是 Unity 工程用 Export Project 在本地导出的 Android Gradle 工程，供云端打包使用。
Unity 源码工程在 [sand-table-commander](https://github.com/laodou050505-spec/sand-table-commander)，本工程由其提交 `9d8fe1fbe73da0dd535eeef79ec69589ec6983eb` 导出。

- Unity 6000.5.5f1，脚本后端 IL2CPP
- IL2CPP 已预编译：libil2cpp.so 在 unityLibrary/src/main/jniLibs/arm64-v8a；Il2CppOutputProject 已移除，buildIl2Cpp 任务保留原样并在 unityLibrary/build.gradle 末尾禁用；清单见 .vibelab-prebuilt.json
- 目标架构只有 arm64-v8a，不导出调试符号（debugSymbolLevel none）
- compileSdk / targetSdk 36，minSdk 29
- 包名 `com.toybox.wartable`，版本 0.1.1119

构建：`gradle :launcher:assembleRelease`（需设置 ANDROID_HOME），产物在 `launcher/build/outputs/apk/release/`。
`local.properties` 未提交。
