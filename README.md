# 🪁 青翔未阔工作室官网

> 青翔未阔工作室的官方网站 —— 集动态壁纸、一言语录、GitHub 文件下载、Minecraft 服务器状态监测、团队成员展示于一体，全静态页面，开箱即用，完美运行于 GitHub Pages。
>
> 可下载文件存储于 [TidalStarNan/QxwkFiles](https://github.com/TidalStarNan/QxwkFiles)，通过 GitHub API 动态读取。

## ✨ 功能一览

### 🏠 首页 (`index.html`)
- **全屏必应每日壁纸**：自动加载 1080P 高清壁纸，加载失败时显示优雅占位图。
- **一言（Hitokoto）**：每次访问随机展示一句励志语录，并显示来源。
- **三大功能模块**：
  - **资源中心**：站内下载（跳转 `download.html`）、站外下载（蓝奏云弹窗）、一中大辞典（自定义子项目）。
  - **网站导航**：域名导航（展示子域名）、外部项目（合作伙伴项目列表）、友情链接（友情站点）。
  - **更多功能**：MC 服务器状态监测、关于我们、更多功能入口（预留）。
- **访客计数器**：基于 hitscounter.dev，展示当日及总访问量。
- **响应式毛玻璃顶栏**：汉堡菜单支持移动端平滑滚动到各区块。

### 📦 下载中心 (`download.html`)
- 通过 **GitHub API** 动态列出 [QxwkFiles](https://github.com/TidalStarNan/QxwkFiles) 仓库下的文件。
- 多标签页支持（如 `mcpack-yz`、`test`），可轻松扩展新目录。
- 自动解析文件名中的日期（`YY.MM.DD` 格式），并按日期倒序排列。
- 展示文件类型、大小（自动换算 KB/MB/GB）、修改日期，并提供下载链接。
- 文件图标根据扩展名智能匹配（📄、🎬、📦、⚙️ 等）。

### 🎮 Minecraft 服务器状态 (`mc-status.html`)
- 双 API 冗余查询（主用 `mcsrvstat.us`，备用 `minecraft-serverhub.com`），提升可用性。
- 显示服务器在线状态、当前/最大玩家数、游戏版本、服务器图标（Favicon）。
- 支持彩色 MOTD 的 HTML 渲染，并自动降级为纯文本。
- 在线玩家列表以标签形式展示，支持滚动查看。

### 👥 关于我们 (`about.html`)
- **关于工作室**：自定义描述 + **一键邮件联系**（自动填充主题）。
- **摸鱼成员** / **特别贡献** / **域名赞助**：使用本地数据渲染成员卡片，支持头像（WeAvatar）与首字母降级。
- 响应式卡片布局，鼠标悬停有丝滑动效。

### 🛠️ 错误页面 (`error.html`)
- 仿 Cloudflare 风格错误页，直观展示浏览器、Cloudflare、源服务器三层状态。
- 实时 UTC 时间同步（通过 `timeapi.io`），每秒刷新。
- 提供“返回首页”按钮，便于用户导航。

## 🔌 使用的 API 与服务

| 用途 | 接口地址 | 说明 |
|------|----------|------|
| 每日壁纸 | `https://uapis.cn/api/v1/image/bing-daily?resolution=1080` | 首页全屏背景 |
| 一言 | `https://v1.hitokoto.cn/` | 随机语录 |
| 访客计数 | `https://hitscounter.dev/` | 页面底部统计 |
| MC 状态（主） | `https://api.mcsrvstat.us/3/{host}` | Java 版服务器查询 |
| MC 状态（备） | `https://minecraft-serverhub.com/api/ping?host={host}&platform=java` | 自动故障转移 |
| UTC 时间 | `https://timeapi.io/api/Time/current/zone?timeZone=UTC` | error 页实时时钟 |
| GitHub 内容 API | `https://api.github.com/repos/{owner}/{repo}/contents/{path}` | 下载中心拉取文件列表 |
| 头像服务 | `https://weavatar.com/avatar/{hash}?s=400` | 团队成员头像（支持邮箱哈希） |

## 🧱 技术栈

- **纯原生**：HTML5 + CSS3 + JavaScript (ES6)
- **无依赖**：所有交互、弹窗、API 请求均手写实现
- **响应式设计**：移动端适配、毛玻璃效果、平滑滚动
- **托管平台**：GitHub Pages（或任何静态 Web 服务器）

## 🔧 自定义扩展指南

**1. 添加/修改团队成员**
- 编辑 about.html 中的 coreMembers、contribMembers、sponsorMembers 数组，每个成员包含 name、desc、avatar（头像 URL，为空时显示名字首字母）。

**2. 修改蓝奏云下载链接**
- 在 index.html 中找到 #downloadModal 弹窗，修改 <a> 标签的 href 和提取码内容。

**3. 增删外部项目 / 友情链接**
- 编辑 index.html 中对应的弹窗（#externalProjectsModal、#friendLinksModal），按相同结构添加或删除条目。

**4. 调整 MC 状态 API 顺序**
- 修改 mc-status.html 中的 API_LIST 数组，可自由增删或调整优先级。

**5. 更换一言 / 壁纸源**
- 壁纸：修改 <img id="bgImage"> 的 src 地址。
- 一言：修改 fetchSaying() 函数中的 API 端点。

### 🌐 在线演示：[https://home.qxwkstudio.top](https://home.qxwkstudio.top/)
### 📧 联系邮箱：QxwkStudio@outlook.com
