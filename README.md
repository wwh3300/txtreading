# 📖 听书阅读器

> 一款可安装到 iPhone 主屏幕的 TXT 文本朗读 PWA 应用，支持中文 GBK / UTF-8 自动识别，调用 iOS 系统 Siri 语音引擎进行朗读。

![Platform](https://img.shields.io/badge/平台-iOS%20Safari-purple?style=flat-square)
![PWA](https://img.shields.io/badge/类型-PWA-blueviolet?style=flat-square)
![License](https://img.shields.io/badge/许可-MIT-green?style=flat-square)
![Offline](https://img.shields.io/badge/离线-支持-success?style=flat-square)

---

## ✨ 功能特性

- **TXT 文件导入** — 支持批量导入，自动识别 UTF-8 / GBK / GB2312 编码，国内小说完美支持
- **智能语音朗读** — 调用 iOS 系统 Web Speech API（Siri 语音），推荐选择 Tingting / Meijia 普通话女声
- **朗读控制** — 支持播放/暂停、上下段跳转、进度条拖拽定位、0.75× ～ 2× 变速
- **阅读视图** — 当前段落高亮跟读，可调字号（12px ～ 24px）及行间距
- **书库管理** — 多文件书库，本地持久化存储，显示字数统计
- **完全离线** — Service Worker 缓存，断网也能正常使用
- **PWA 安装** — 可添加到 iPhone 主屏幕，全屏沉浸体验，支持刘海 / 灵动岛安全区域

---

## 📁 项目结构

```
tingshu-pwa/
├── index.html        # 主应用（UI + 全部业务逻辑）
├── manifest.json     # PWA 配置（名称、主题色、图标）
├── sw.js             # Service Worker（离线缓存策略）
├── README.md         # 项目说明文档
└── icons/
    ├── icon-192.png  # 主屏幕图标 192×192
    └── icon-512.png  # 启动画面图标 512×512
```

---

## 🚀 部署到 GitHub Pages

### 第一步：新建仓库

1. 登录 [github.com](https://github.com)，点击右上角 **+** → **New repository**
2. 填写仓库名称（如 `tingshu`），选择 **Public**
3. 点击 **Create repository**

### 第二步：上传文件

将本项目所有文件上传至仓库根目录：

```
index.html
manifest.json
sw.js
README.md
icons/icon-192.png
icons/icon-512.png
```

### 第三步：开启 GitHub Pages

1. 进入仓库 **Settings** → 左侧 **Pages**
2. Source 选择 **Deploy from a branch**
3. Branch 选 `main`，目录选 `/ (root)`，点击 **Save**

### 第四步：访问应用

约 1～2 分钟后，访问地址为：

```
https://<你的用户名>.github.io/<仓库名>/
```

---

## 📲 安装到 iPhone 主屏幕

1. 用 **Safari** 打开上方部署地址（必须用 Safari，Chrome 不支持 iOS PWA 安装）
2. 点击底部工具栏的 **分享按钮** ⬆️
3. 在菜单中选择 **添加到主屏幕**
4. 点击右上角 **添加**，图标即出现在主屏幕

安装后以全屏模式运行，体验与原生 App 一致。

---

## 🎙️ 语音设置建议

| 声音名称 | 语言 | 音质 | 说明 |
|---|---|---|---|
| Tingting | zh-CN | ⭐⭐⭐⭐ | 普通话女声，流畅自然（推荐） |
| Meijia | zh-TW | ⭐⭐⭐⭐ | 台湾普通话女声，清晰 |
| 系统默认 | zh-CN | ⭐⭐⭐ | 根据系统语言自动选择 |

若语音列表中未出现中文选项，请前往：**设置 → 辅助功能 → 朗读内容 → 声音** 下载中文语音包。

---

## 🔧 编码支持说明

本应用内置编码自动检测逻辑：

1. 读取文件原始字节流
2. 逐字节验证是否符合 UTF-8 规范
3. 验证通过 → 使用 **UTF-8** 解码；验证失败 → 自动切换 **GBK** 解码

支持的编码格式：`UTF-8`、`UTF-8 with BOM`、`GBK`、`GB2312`、`GB18030`

---

## 📦 技术栈

| 技术 | 用途 |
|---|---|
| 原生 HTML / CSS / JS | 无框架，零依赖 |
| Web Speech API | 语音合成（TTS） |
| Service Worker | 离线缓存 |
| Web App Manifest | PWA 安装配置 |
| localStorage | 书库与设置持久化 |
| FileReader API | 文件读取与编码检测 |

---

## 📄 许可证

MIT License — 自由使用、修改与分发。
