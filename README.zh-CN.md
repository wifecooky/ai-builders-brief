[English](README.md) | **中文** | [日本語](README.ja.md)

> **Credits:** 原始项目由 [Zara Zhang](https://x.com/zarazhangrui)（[follow-builders](https://github.com/zarazhangrui/follow-builders)）创建。MIT 许可。

<p align="center">
  <img src="assets/cover.svg" alt="AI Builders Brief" width="100%">
</p>

# AI Builders Brief

**你的每日 AI 行业情报，来自真正在造东西的人。**

一个 AI agent 技能，追踪 25+ 位顶尖 AI 建造者的 X/Twitter 动态、6 档头部播客和官方博客，
将最新内容提炼成一份精简的每日/每周简报，推送到你的首选渠道。无需任何 API key。

> 追踪有独立见解的建造者，而非搬运信息的网红。

## 你会得到什么

每日或每周推送到你常用的通讯工具（Telegram、Discord、WhatsApp 等），包含：

- 25 位精选 AI 建造者在 X/Twitter 上的关键观点和洞察
- 6 档顶级 AI 播客新节目的精华摘要
- AI 公司官方博客精选（Anthropic Engineering、Claude Blog）
- 所有原始内容的直链
- 支持英文、中文或双语版本

## 快速开始

### 一键安装（推荐）
```bash
npx skills add wifecooky/ai-builders-brief
```
支持 Claude Code、Cursor、Codex 等各类 agent。

### 手动安装
```bash
# Claude Code
git clone https://github.com/wifecooky/ai-builders-brief.git ~/.claude/skills/ai-builders-brief
cd ~/.claude/skills/ai-builders-brief/scripts && npm install

# OpenClaw
git clone https://github.com/wifecooky/ai-builders-brief.git ~/skills/ai-builders-brief
cd ~/skills/ai-builders-brief/scripts && npm install
```

然后输入 **"set up ai builders brief"** 或执行 `/ai-builders-brief`。Agent 会以对话方式
引导你完成设置，不需要手动编辑任何配置文件。

Agent 会询问你：
- 推送频率（每日或每周）和时间
- 语言偏好（英文、中文或双语）
- 推送方式（Telegram、邮件或直接在聊天中显示）

不需要任何 API key，所有内容由中心化服务统一抓取。
设置完成后，你的第一期简报会立即推送。

## 修改设置

通过对话即可修改推送偏好。直接告诉你的 agent：

- "改成每周一早上推送"
- "语言换成中文"
- "把摘要写得更简短一些"
- "显示我当前的设置"

信息源列表（建造者和播客）由中心化统一管理和更新，你无需做任何操作即可获得最新的信息源。

## 自定义摘要风格

技能使用纯文本 prompt 文件来控制内容的摘要方式。你可以通过两种方式自定义：

**通过对话（推荐）：**
直接告诉你的 agent，如"摘要写得更简练一些"、"多关注可操作的洞察"、"用更轻松的语气"。Agent 会自动帮你更新 prompt。

**直接编辑（高级用户）：**
编辑 `prompts/` 文件夹中的文件：
- `summarize-podcast.md` — 播客节目的摘要方式
- `summarize-tweets.md` — X/Twitter 帖子的摘要方式
- `summarize-blogs.md` — 博客文章的摘要方式
- `digest-intro.md` — 整体简报的格式和语气
- `translate.md` — 英文内容翻译为中文的方式

这些都是纯文本指令，不是代码。修改后下次推送即生效。

## 默认信息源

### 播客（6档）
- [Latent Space](https://www.youtube.com/@LatentSpacePod)
- [Training Data](https://www.youtube.com/playlist?list=PLOhHNjZItNnMm5tdW61JpnyxeYH5NDDx8)
- [No Priors](https://www.youtube.com/@NoPriorsPodcast)
- [Unsupervised Learning](https://www.youtube.com/@RedpointAI)
- [Data Driven NYC](https://www.youtube.com/@DataDrivenNYC)
- [AI & I by Every](https://www.youtube.com/playlist?list=PLuMcoKK9mKgHtW_o9h5sGO2vXrffKHwJL)

### X 上的 AI 建造者（25位）
[Andrej Karpathy](https://x.com/karpathy), [Swyx](https://x.com/swyx), [Josh Woodward](https://x.com/joshwoodward), [Kevin Weil](https://x.com/kevinweil), [Peter Yang](https://x.com/petergyang), [Nan Yu](https://x.com/thenanyu), [Madhu Guru](https://x.com/realmadhuguru), [Amanda Askell](https://x.com/AmandaAskell), [Cat Wu](https://x.com/_catwu), [Thariq](https://x.com/trq212), [Google Labs](https://x.com/GoogleLabs), [Amjad Masad](https://x.com/amasad), [Guillermo Rauch](https://x.com/rauchg), [Alex Albert](https://x.com/alexalbert__), [Aaron Levie](https://x.com/levie), [Ryo Lu](https://x.com/ryolu_), [Garry Tan](https://x.com/garrytan), [Matt Turck](https://x.com/mattturck), [Zara Zhang](https://x.com/zarazhangrui), [Nikunj Kothari](https://x.com/nikunj), [Peter Steinberger](https://x.com/steipete), [Dan Shipper](https://x.com/danshipper), [Aditya Agarwal](https://x.com/adityaag), [Sam Altman](https://x.com/sama), [Claude](https://x.com/claudeai)

### 官方博客（2个）
- [Anthropic Engineering](https://www.anthropic.com/engineering) — Anthropic 团队的技术深度文章
- [Claude Blog](https://claude.com/blog) — Claude 的产品公告与更新

## 工作原理

1. 中心化 feed 每日更新，抓取所有信息源的最新内容（博客文章通过网页抓取，YouTube 字幕通过 Supadata，X/Twitter 通过官方 API）
2. 你的 agent 获取 feed — 一次 HTTP 请求，不需要 API key
3. 你的 agent 根据你的偏好将原始内容重新提炼为精简的简报
4. 简报推送到你的通讯工具（或直接在聊天中显示）

查看 [examples/sample-digest.md](examples/sample-digest.md) 了解输出示例。

## 系统要求

- 一个 AI agent（Claude Code、OpenClaw、Cursor 或类似工具）
- 网络连接（用于获取中心化 feed）

仅此而已。不需要任何 API key。所有内容由中心化服务每日抓取更新。

## 隐私

- 不发送任何 API key — 所有内容由中心化服务获取
- 如果你使用 Telegram/邮件推送，相关 key 仅存储在本地 `~/.follow-builders/.env`
- 技能只读取公开内容（公开的博客文章、YouTube 视频和 X 帖子）
- 你的配置、偏好和阅读记录都保留在你自己的设备上

## 许可证

MIT
