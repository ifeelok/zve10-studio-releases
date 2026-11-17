# ZV Studio — 侧载源

本仓库只托管 [ZV Studio](https://github.com/ifeelok/zve10-studio) 的未签名 IPA 和应用源。

## 添加应用源（加一次，以后自动更新）

SideStore 和 LiveContainer 都兼容 AltStore 格式的源，用同一个地址即可：

```
https://raw.githubusercontent.com/ifeelok/zve10-studio-releases/refs/heads/main/apps.json
```

### SideStore

1. 打开 SideStore，**Sources** 标签 → 右上角 `+`
2. 粘贴上面的地址 → Add Source
3. 到 **Browse** 找到 ZV Studio → Install

SideStore 也支持一键链接（点开自动跳 SideStore 添加源）：

```
sidestore://source?url=https://raw.githubusercontent.com/ifeelok/zve10-studio-releases/refs/heads/main/apps.json
```

### LiveContainer

1. 打开 LiveContainer → **Sources** 标签 → `+`
2. Add Manual 里粘贴上面的地址 → Add Source
3. 在源里找到 ZV Studio → 安装到容器

## 为什么加源后不用再复制地址

- 源里的 `downloadURL` 用的是 GitHub `releases/latest/download` **固定直链**，永远指向最新版本的 IPA。
- 每次发新版，CI 自动更新源文件中的版本号并推送到本仓库；在 SideStore/LiveContainer 里刷新源即可看到更新提示。

## 直接下载 IPA（不想加源时）

```
https://github.com/ifeelok/zve10-studio-releases/releases/latest/download/ZVStudio-unsigned.ipa
```

历史版本见 [Releases](https://github.com/ifeelok/zve10-studio-releases/releases)。

## 滤镜 LUT 链接（App 内按需下载）

`luts/` 目录放的是富士官方 F-Log2 胶片模拟 LUT 经色彩空间转换后的 sRGB 版本（面向普通 JPEG）。在 App 里点「从链接导入 LUT 包」，填下面任一地址即可一次导入 10 款：

```
https://cdn.jsdelivr.net/gh/ifeelok/zve10-studio-releases@main/luts/fuji-luts.json
https://raw.githubusercontent.com/ifeelok/zve10-studio-releases/refs/heads/main/luts/fuji-luts.json
```

导入后出现在滤镜编辑器的「富士原版」分组，可在设置页删除、可换成任意自己的清单或单个 `.cube` 直链。这些文件不随 IPA 分发，只在你点导入时下载到手机本机。

> 富士官网对下载内容的说明是导入视频编辑软件使用，未授予随第三方 App 再分发的许可；此处为衍生文件，使用前请自行确认富士官方条款。

## 说明

IPA 未签名，由 SideStore/LiveContainer 在安装时签名。App 需相机开启「智能手机观看」并连入其 Wi-Fi 热点（`192.168.122.1`）。
