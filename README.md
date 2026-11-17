# ZV Studio — 侧载源

本仓库只托管 [ZV Studio](https://github.com/ifeelok/zve10-studio) 的未签名 IPA 和应用源，**不含任何源码**。源码在私有仓库。

## 添加应用源（加一次，以后自动更新）

SideStore 和 LiveContainer 都兼容 AltStore 格式的源，用同一个地址即可：

```
https://raw.githubusercontent.com/ifeelok/zve10-studio-releases/main/apps.json
```

### SideStore

1. 打开 SideStore，**Sources** 标签 → 右上角 `+`
2. 粘贴上面的地址 → Add Source
3. 到 **Browse** 找到 ZV Studio → Install

SideStore 也支持一键链接（点开自动跳 SideStore 添加源）：

```
sidestore://source?url=https://raw.githubusercontent.com/ifeelok/zve10-studio-releases/main/apps.json
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

## 说明

IPA 未签名，由 SideStore/LiveContainer 在安装时签名。App 需相机开启「智能手机观看」并连入其 Wi-Fi 热点（`192.168.122.1`）。
