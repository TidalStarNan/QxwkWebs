# 🪁 青翔未阔工作室官网

> 青翔未阔工作室的官方网站 —— 集资源下载、画廊、项目展示、团队介绍于一体，全静态页面，开箱即用，完美运行于 GitHub Pages。
>
> 可下载文件存储于 [TidalStarNan/QxwkFiles](https://github.com/TidalStarNan/QxwkFiles)，通过 GitHub API 动态读取。

## ✨ 功能一览

### 🏠 首页 (`index.html`)
- **全屏必应每日壁纸**：自动加载高清壁纸，毛玻璃欢迎区域 + 一言语录
- **项目概览**：照片堆叠展示工作室项目，支持触摸滑动切换
- **资源中心**：站内下载、站外下载（蓝奏云弹窗）、画廊、页面仓库、MC 服务器状态、易错点测试、Sails GitHub 状态
- **页面导航**：一中大辞典、邮箱站、关于我们、更多工具
- **网站链接**：外部项目与合作站点直接展示

### 📦 下载中心 (`tools/download.html`)
- 通过 **GitHub API** 动态列出 [QxwkFiles](https://github.com/TidalStarNan/QxwkFiles) 仓库文件
- 多标签页支持，自动解析文件名日期并按倒序排列
- 展示文件类型、大小、修改日期，一键下载

### 🖼️ 画廊 (`tools/gallery.html`)
- 从 `QxwkFiles/image-gallery` 目录动态读取图片
- 分类标签页，响应式图片网格
- 灯箱放大查看，键盘快捷键切换
- 禁止右键下载保护

### 👥 关于我们 (`about.html`)
- 工作室介绍 + 一键邮件联系
- 团队卡片（摸鱼成员 / 特别贡献 / 域名赞助）

### 🛠️ 错误页面 (`404.html`)
- 仿 Cloudflare 风格错误页
- 实时 UTC 时钟同步

### 📖 一中大辞典 (`dictionary/dictionary.html`)
- 分类词条浏览，标题解锁验证
- 全校卷内置音乐播放器

### 🛠️ 工具页 (`tools/`)
- **MC 服务器状态** (`mc-status.html`) — 查询 Minecraft 服务器在线状态、MOTD、玩家列表，支持多 API 回退
- **易错点测试** (`26keys-quiz.html`) — 26键拼音输入法易错点测试，随机抽题、计时答题、结果回顾
- **Sails GitHub 状态** (`sails.html`) — 查询 StarsailsClover 的 GitHub 用户信息、贡献日历、仓库动态

## 🔌 使用的 API 与服务

| 用途 | 接口地址 | 说明 |
|------|----------|------|
| 每日壁纸 | `bing.biturl.top` / `api.btstu.cn/bing` | 首页全屏背景（双 API 回退） |
| 一言 | `v1.hitokoto.cn` | 随机语录 |
| 访客计数 | `hitscounter.dev` | 页面底部统计 |
| UTC 时间 | `timeapi.io` | error 页实时时钟 |
| GitHub REST API | `api.github.com/users/{user}` / `repos` / `orgs` | 下载中心、画廊、Sails 状态 |
| GitHub GraphQL API | `api.github.com/graphql` | Sails 贡献日历 |

## 🧱 技术栈

- **纯原生**：HTML5 + CSS3 + JavaScript (ES6)
- **无依赖**：所有交互、弹窗、API 请求均在前端实现
- **响应式设计**：移动端适配、毛玻璃效果、平滑滚动
- **托管平台**：GitHub Pages（`docs/` 目录部署）

> **⚠️ 如果您 fork 了本项目**：部署前请务必将所有链接（计数器、下载链接、联系方式等）修改为您自己的地址，请勿直接使用原站链接。

## 🔧 自定义指南

**1. 添加/修改团队成员**
- 编辑 `about.html` 中的成员数组

**2. 修改蓝奏云下载链接**
- 编辑 `index.html` 中 `#downloadModal` 弹窗

**3. 增删外部项目 / 友情链接**
- 编辑 `index.html` 中 `#links-section` 的内容

**4. 更换一言 / 壁纸源**
- 壁纸：修改 `<img id="bgImage">` 的 src
- 一言：修改 `fetchSaying()` 中的 API 端点

**5. 添加画廊图片**
- 推送图片到 `QxwkFiles/image-gallery/` 目录

---

🌐 在线演示：[https://home.qxwkstudio.top](https://home.qxwkstudio.top/)

📧 联系邮箱：QxwkStudio@outlook.com

版权所有 2026 青翔未阔工作室
