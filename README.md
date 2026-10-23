# cn-math-taxonomy APK（「中小学·高中知识图谱」离线版）

将开源静态知识图谱站 [xiaoyang111222/cn-math-taxonomy](https://github.com/xiaoyang111222/cn-math-taxonomy) 完整打包为 Android WebView 离线应用：全部题库、知识图谱、诊断功能装进手机，**运行零联网**。

## 下载与安装

1. 手机浏览器打开本仓库 [Releases](https://github.com/ktzhush/cn-math-taxonomy-release/releases)，下载最新 `cn-math-taxonomy-x.x.x-debug.apk`
2. 允许"安装未知来源应用"后安装（Android 7.0+，包名 `com.cnmath.taxonomy`）
3. 首次启动即进入首页，无需任何网络与账号

## 完整性校验

| 版本 | 修复 | SHA256 | 大小 |
|---|---|---|---|
| v1.0.1（最新） | 目录索引 + file 源 fetch 放行 | `C3E09A628E06431C524DDA466FBCBB79FFEB26EA0E3AED84B431E9E8003E665F` | 8,763,170 字节 |
| v1.0.0（勿用） | 存在目录导航 404 | `FB513FE7E23C312771BAAA57D6DF4DD4C3E22BCC783596762DAB5DC945CFC4BD` | 8,772,654 字节 |

## 溯源（供应链指纹）

| 组件 | 来源 | 指纹 |
|---|---|---|
| 站点内容 | xiaoyang111222/cn-math-taxonomy | commit `d58785c`（2026-10-23T12:40Z，main） |
| WebView 壳 | xchacha20-poly1305/webview-apk-template | dev 分支（Kotlin，app.properties 配置驱动） |
| 构建流水线 | ktzhush/cn-math-taxonomy-apk（私有） | Actions run `39969143589`，source 检出后原样拷入 assets |

构建方式：GitHub Actions 检出源站 → 显式清单拷贝（index.html / sw.js / manifest / assets / data / children / explore / diagnose）→ `app.url=file:///android_asset/index.html` 离线加载 → assembleDebug。

## 许可

- 站点内容（随 APK 分发的全部题库与页面）：**CC BY-NC 4.0**，原作者 xiaoyang111222——非商业使用，再分发须保留本署名与原作链接
- WebView 壳工程：MIT（版权见其 LICENSE，作者 HystericalDragons@proton.me）
- 本仓库为非商业转发行分发，任何商用需上游另行授权
