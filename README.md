# ProxyPin - AI 增强版

[English](README.md) | 中文

## 开源免费抓包工具，内置 AI 助手

基于 [ProxyPin](https://github.com/wanghongenpin/proxypin) (wanghongenpin) 增强，此版本新增 **内置 AI 助手**，通过自然语言即可操控整个抓包工具。

## 功能特性

### 核心功能 (上游)
* 手机扫码连接: 不用手动配置 Wifi 代理，包括配置同步。
* 域名过滤: 只拦截所需流量，避免干扰其他应用。
* 搜索：根据关键词、响应类型等多种条件搜索请求。
* 脚本: 支持编写 JavaScript 脚本处理请求或响应。
* 请求重写: 支持重定向，替换请求或响应报文。
* 请求映射: 不请求远程服务，使用本地配置或脚本响应。
* 请求解密: 配置 AES 解密密钥，自动解密 HTTP 消息体。
* 请求屏蔽: 支持根据 URL 屏蔽请求。
* 历史记录：自动保存抓包数据，支持 HAR 格式导入/导出。
* 其他：收藏、工具箱、常用编码工具、二维码、正则等。

### AI 助手 (此 fork 新增)
- **自然语言控制**：通过聊天即可启停代理、列/搜索/分析请求、修改请求头/体、屏蔽域名等。
- **工具箱 AI 化**：URL/Base64 编解码、时间戳转换、正则测试等工具。
- **VPN 与悬浮窗控制**：启停 VPN 模式、显示/隐藏 AI 悬浮球、进入画中画模式。
- **报告服务器与加密**：增删改查报告服务器和 AES 加密/解密规则。
- **规则开关**：按名称启停单个重写、屏蔽、映射规则。
- **进程查询**：查询占用某端口的 Android 应用。
- **Android 悬浮气泡**：快捷 AI 入口，代理状态指示灯（绿色=运行中）。
- **分享给 AI**：长按任意抓包请求 → 分享给 AI 即时分析。

## 从源码构建

```bash
# 克隆
git clone https://github.com/YOUR_USERNAME/proxypin.git
cd proxypin

# 安装依赖
flutter pub get

# 运行
flutter run -d android

# 构建调试 APK
flutter build apk --debug

# 构建正式版 APK (需要签名密钥)
# 1. 在 android/ 目录创建 key.properties：
echo "storeFile=../app/release-keystore.jks
storePassword=你的密码
keyAlias=release
keyPassword=你的密码" > android/key.properties

# 2. 生成密钥库（或使用自己的）：
keytool -genkey -v -keystore android/app/release-keystore.jks \
  -keyalg RSA -keysize 2048 -validity 10000 \
  -alias release -storepass 你的密码 -keypass 你的密码

# 3. 构建：
flutter build apk --release
```

正式版 APK 位于 `build/app/outputs/flutter-apk/app-release.apk`。

**注意**：Windows 上项目路径不能包含中文等非 ASCII 字符，否则 AOT 编译可能失败。正式版构建请使用纯英文路径。

## 下载地址

- **国内下载**: https://gitee.com/wanghongenpin/proxypin/releases
- **iOS App Store**: https://apps.apple.com/app/proxypin/id6450932949
- **Android Google Play**: https://play.google.com/store/apps/details?id=com.network.proxy
- **TG**: https://t.me/proxypin_tg

## 赞助

如果您觉得 ProxyPin 对您有帮助，欢迎通过以下方式支持我们：

- [爱发电赞助](https://afdian.com/a/proxypin)
- [Buy Me A Coffee](https://buymeacoffee.com/proxypin)
- 提交反馈和建议，帮助我们改进
- 为项目贡献代码或文档

**您的支持将用于项目的维护、功能开发和用户体验优化，非常感谢！**

> **Mac**: 首次打开提示"不受信任开发者"，到系统偏好设置 → 安全性与隐私 → 允许任何来源。

<img alt="image"  width="580px" height="420px"  src="https://github.com/user-attachments/assets/80f30d64-f2b5-473c-98f5-bae50b309278">.<img alt="image"  height="500px" src="https://github.com/user-attachments/assets/3c5572b0-a9e5-497c-8b42-f935e836c164">
