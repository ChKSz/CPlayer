<p align="center">
  <img src="img/icon.svg" alt="CPlayer 5 Logo" width="120" height="120">
</p>

<h1 align="center">CPlayer 5</h1>

<p align="center">
  <b>一款现代化的 Web 音乐播放器，支持超清母带音质、实时歌词、离线歌单导入与沉浸式动态背景。</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=pwa&logoColor=white" alt="PWA">
</p>

<p align="center">
  <a href="https://cp.chksz.top">在线演示</a> ·
  <a href="https://cp.chksz.top/playlist-downloader">歌单下载工具</a> ·
  <a href="https://github.com/ChKSz/CPlayer">GitHub 仓库</a>
</p>

---

## 简介

CPlayer 5 是一个纯前端、免构建的单页音乐播放器。项目基于浏览器原生能力实现播放控制、歌词同步、音频可视化、PWA 离线缓存、移动端手势交互与本地歌单导入，打开静态服务器即可运行。

当前版本除了基础播放体验，还加入了更完整的歌单加载链路：支持远程歌单 ID 拉取、`playlist.js` 本地离线歌单、JSON 文件导入、拖拽导入，以及 IndexedDB 歌单缓存与静默更新。

## 最新功能

- 支持通过歌单 ID 直接加载远程歌单，并自动写入本地缓存
- 支持导入 `playlist.js` 或 `.json` 歌单文件，适合离线或自定义场景
- 新增 `playlist-downloader.html`，可一键导出兼容 `playlist.js`
- 支持 IndexedDB 缓存歌单、歌词与封面，提升重复访问速度
- 支持 Service Worker 缓存核心静态资源，具备基础 PWA 离线能力
- 支持移动端底部抽屉、拖拽关闭、左右滑动切换歌词/封面
- 支持 Media Session 与 Wake Lock，改善锁屏控制和移动端连续播放体验
- 支持动态渐变背景与 WebGL 流体背景，增强沉浸式视觉效果

## 在线体验

- 在线演示：`https://cp.chksz.top`
- 歌单下载工具：`https://cp.chksz.top/playlist-downloader`
- 仓库地址：`https://github.com/ChKSz/CPlayer`

## 功能特性

### 播放与队列

- 播放 / 暂停 / 上一首 / 下一首
- 进度条拖拽跳转
- 音量调节与静音控制
- 顺序播放、随机播放、单曲循环
- 下一首预加载，减少切歌等待

### 音质支持

| level | 名称 | 说明 |
| --- | --- | --- |
| `standard` | 标准音质 | 128kbps MP3 |
| `exhigh` | 极高音质 | 320kbps MP3 |
| `lossless` | 无损音质 | FLAC |
| `hires` | Hi-Res | 高解析度 FLAC |
| `jyeffect` | 高清环绕声 | 空间音频效果 |
| `sky` | 沉浸环绕声 | Dolby Atmos 效果 |
| `jymaster` | 超清母带 | 默认优先音质 |

### 歌词体验

- LRC 实时同步显示
- 支持翻译歌词（TLRC）
- 兼容 YRC 扩展歌词链路
- 桌面端与移动端分别优化歌词滚动与遮罩表现
- 当前行高亮、缩放与透明度渐变

### 歌单与搜索

- 支持歌曲名 / 歌手名搜索
- 支持直接输入歌曲 ID 解析
- 支持歌单 ID 拉取播放列表
- 支持拖拽导入 `playlist.js` / `.json`
- 支持本地离线歌单优先启动
- 大列表虚拟化渲染，长歌单依然流畅

### 离线与缓存

- Service Worker 缓存核心资源
- IndexedDB 缓存歌单、歌词、封面缩略图
- 已缓存歌单支持优先读取，再后台静默刷新
- 可配合本地 `playlist.js` 实现离线歌单使用

### 视觉与交互

- 磨砂玻璃风格播放器界面
- 专辑封面主色提取与动态主题联动
- 动态渐变背景模式
- WebGL 流体背景渲染
- 全屏沉浸播放模式
- 移动端左右滑动切换内容、底部抽屉操作

### 系统集成

- Media Session API 系统媒体控制
- Android 锁屏控制
- Wake Lock 防止播放中息屏影响体验
- PWA 安装支持

## 技术栈

| 类别 | 技术 |
| --- | --- |
| 核心 | HTML5 + CSS3 + Vanilla JavaScript (ES6+) |
| 样式 | Tailwind CSS Runtime、CSS Variables、Backdrop Filter |
| 音频 | HTMLAudioElement、Web Audio API |
| 图形 | Canvas API、WebGL |
| 存储 | IndexedDB、LocalStorage、Cache Storage |
| PWA | Service Worker、Web App Manifest |
| 图标 | Font Awesome |
| 字体 | Noto Sans SC |
| 工具库 | Color Thief |

## 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/ChKSz/CPlayer.git
cd CPlayer
```

### 2. 启动静态服务

项目无需安装依赖，直接使用任意 HTTP 服务器即可：

```bash
python -m http.server 8080
```

或：

```bash
npx serve .
```

### 3. 打开浏览器

访问 `http://localhost:8080`。

## 项目结构

```text
CPlayer/
├── index.html               # 主播放器页面
├── playlist.js              # 本地离线歌单数据
├── playlist-downloader.html # 歌单导出工具页
├── sw.js                    # Service Worker
├── manifest.json            # PWA 清单
├── css/                     # 字体与图标样式
├── js/                      # 前端运行时依赖
├── fonts/                   # 本地字体
├── webfonts/                # 图标字体
└── img/                     # 图标与资源
```

## 使用说明

### 远程歌单

在播放器内输入歌单 ID，即可拉取远程歌单并自动缓存。

### 本地离线歌单

将导出的 `playlist.js` 放到项目根目录，播放器启动时会优先读取 `window.LOCAL_PLAYLIST`。

### 自定义 JSON 导入

支持直接导入 JSON 文件，常见格式如下：

```json
[
  {
    "id": 123456,
    "name": "歌曲名称",
    "artists": "歌手名",
    "album": "专辑名",
    "picUrl": "https://example.com/cover.jpg"
  }
]
```

也支持包装格式：

```json
{
  "title": "My Playlist",
  "data": {
    "tracks": []
  }
}
```

## 兼容性

推荐使用最新版 Chrome、Edge、Firefox 或 Safari。项目依赖以下浏览器能力：

- ES6+
- Web Audio API
- IndexedDB
- Canvas / WebGL
- Service Worker
- Media Session API（部分平台）

## 版权与合规声明

- 本项目仅提供播放器前端界面、歌单管理、歌词展示与浏览器侧缓存能力，不内置受版权保护的音频内容
- 项目本身不声明拥有任何第三方音乐、歌词、封面、商标或平台资源的权利，相关权利归其各自权利人所有
- 我们无意侵犯任何组织或个人的知识产权；如相关资源的权利人认为仓库内容存在问题，请通过仓库 Issues 或其他公开联系方式告知，我们会及时处理
- 使用者应自行确保其获取、调用、分享或播放的内容来源合法合规，并遵守所在地法律法规及相关平台协议
- 严禁将本项目用于传播盗版、绕过授权、批量抓取、非法牟利或任何违法违规用途

## 许可证

本项目采用 [MIT License](LICENSE) 开源发布，版权归 ChKSz 所有；使用、分发和二次开发时请保留原始许可证与版权声明。

## 致谢

- [Color Thief](https://lokeshdhakar.com/projects/color-thief/) - 专辑封面主色提取
- [Font Awesome](https://fontawesome.com/) - 图标资源
- [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC) - 开源中文字体
