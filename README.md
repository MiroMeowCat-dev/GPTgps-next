# GPTgps

GPTgps 是一个面向长对话场景的多站点 AI 聊天导航扩展，帮助你在超长会话里快速找回 earlier prompts、分段整理内容、添加标记与注释，并基于上下文生成 AI 摘要。

GPTgps is a multi-site browser extension for navigating long AI conversations. It helps you find earlier prompts, split large chats into segments, add markers and notes, and generate AI summaries from saved context.

## 项目简介 / Overview

当 AI 对话越来越长时，常见问题会变得很明显：

- 很难回到某一条早先的关键 prompt
- 同一条会话里混着多个子任务或主题
- 需要在聊天正文内部留下可回跳的位置
- 想快速看摘要，而不是反复重读整条线程

GPTgps 通过聊天页内侧边栏、分段系统、标记系统和摘要能力来解决这些问题。

As AI chats grow longer, a few problems become unavoidable:

- it becomes hard to jump back to an earlier key prompt
- one conversation often contains several different topics
- you may want bookmark-like anchors inside the chat body
- a compact summary is often more useful than rereading the whole thread

GPTgps solves this with an in-page sidebar, segmentation workflow, marker system, and AI-assisted summaries.

## 支持平台 / Supported Sites

- ChatGPT
- Gemini
- Qwen / Tongyi / Qianwen
- Doubao
- Claude

## 核心功能 / Core Features

- Prompt 导航侧边栏与搜索
- 长对话分段、重命名与整理
- Marker / checkpoint 锚点跳转
- Pin 重要 prompt 或标记
- Prompt 与 marker 的 Note 注释
- 右侧快速跳转 dock
- Segment 和条目级 AI 摘要
- 多 AI provider 切换、诊断与重试
- 当前导航状态导出 / 导入
- 刷新后的会话状态恢复

- Prompt navigation sidebar with search
- Segment split and rename workflow
- Marker / checkpoint anchors for chat-body jumping
- Pin important prompts or markers
- Notes on prompts and markers
- Right-side mini jump dock
- AI summaries for segments and prompt-level items
- AI provider switching, diagnostics, and retries
- Export / import of current navigation state
- Session-state restoration after refresh

## AI 提供方 / AI Providers

当前支持的摘要后端包括：

- OpenAI-compatible APIs
- Qwen DashScope CN / Intl / US
- Qwen Coding endpoint
- MiniMax
- 自定义 OpenAI-compatible endpoint

Current summary backends include:

- OpenAI-compatible APIs
- Qwen DashScope CN / Intl / US
- Qwen Coding endpoint
- MiniMax
- Custom OpenAI-compatible endpoints

## 安装 / Install

### Chrome / Edge

1. 克隆或下载本仓库。
2. 打开 `chrome://extensions`。
3. 打开 `Developer mode`。
4. 点击 `Load unpacked`。
5. 选择 `./dist_mv3`。

1. Clone or download this repository.
2. Open `chrome://extensions`.
3. Turn on `Developer mode`.
4. Click `Load unpacked`.
5. Select `./dist_mv3`.

### Firefox

1. 打开 `about:debugging#/runtime/this-firefox`。
2. 点击 `Load Temporary Add-on`。
3. 选择 `./dist_mv2/manifest.json`。

1. Open `about:debugging#/runtime/this-firefox`.
2. Click `Load Temporary Add-on`.
3. Select `./dist_mv2/manifest.json`.

## 构建 / Build

- Windows: `build.bat`
- macOS / Linux: `build.sh`

执行后会从源码重新生成 `dist_mv2` 和 `dist_mv3` 两套 unpacked build。

This regenerates the unpacked builds in `dist_mv2` and `dist_mv3` from source.

## 基本使用 / Basic Usage

1. 打开一个支持的 AI 聊天页面。
2. 从浮动按钮打开 GPTgps。
3. 使用侧边栏进行搜索、跳转、分段、Pin、重命名和注释。
4. 如需 AI 摘要，可在 AI 设置中配置 provider、model、base URL、language 和显示限制。
5. 也可以通过 `Tools` 使用诊断、导出和导入功能。

1. Open a supported AI chat page.
2. Open GPTgps from the floating button.
3. Use the sidebar to search, jump, split, pin, rename, and annotate.
4. If needed, open AI settings to configure provider, model, base URL, language, and summary display limits.
5. You can also use `Tools` for diagnostics, export, and import.

## 文档 / Documentation

- 中文快速使用: [`docs/快速使用-中文.md`](./docs/%E5%BF%AB%E9%80%9F%E4%BD%BF%E7%94%A8-%E4%B8%AD%E6%96%87.md)
- Regression checklist: [`docs/nav-regression-checklist.md`](./docs/nav-regression-checklist.md)
- GitHub 发布流程: [`docs/GitHub发布流程.md`](./docs/GitHub%E5%8F%91%E5%B8%83%E6%B5%81%E7%A8%8B.md)

## 当前状态 / Current Status

这一版主要聚焦于长对话导航和多站点支持。

目前日常可用的平台：

- ChatGPT
- Gemini
- Qwen
- Claude
- Doubao

仍在继续优化的部分：

- 连续图片-only 消息未来会进一步收敛成更紧凑的可展开分组

This release is focused on long-chat navigation and multi-site support.

Stable for day-to-day use:

- ChatGPT
- Gemini
- Qwen
- Claude
- Doubao

Still being refined:

- Consecutive image-only messages may later be collapsed into a more compact expandable group

## 已知限制 / Known Limitations

- AI 摘要依赖你自己配置的 provider 和 API key
- 多站点适配依赖实时 DOM 结构，上游 UI 变化后可能需要重新校准选择器
- 图片-only turn 目前会以 `[Image-only message]` 这样的占位形式保留，后续还会继续优化连续图片消息的展示

- AI summaries depend on the provider and API key you configure
- Multi-site adapters rely on live DOM structure and may require selector recalibration after upstream UI changes
- Image-only turns are preserved with placeholders such as `[Image-only message]`; richer grouping for consecutive image-only messages is still planned

## 来源与致谢 / Attribution

GPTgps 起步于 Prompt Genius / ChatGPT Prompt Genius 的开源基础，并在此基础上持续演进出现在这套以长对话导航为主的产品方向。

当前版本中，核心主线已经集中在：

- segment-aware navigation
- marker / checkpoint anchors
- improved jump accuracy
- AI summary orchestration
- multi-site adapters
- diagnostics and session restoration

GPTgps started from the open-source Prompt Genius / ChatGPT Prompt Genius codebase and has since evolved into a long-conversation navigation product with a very different core focus.

The current version is centered on:

- segment-aware navigation
- marker / checkpoint anchors
- improved jump accuracy
- AI summary orchestration
- multi-site adapters
- diagnostics and session restoration

## License

本仓库当前沿用 `CC BY-NC-SA 4.0`，详见 [`LICENSE`](./LICENSE)。

这意味着：

- 需要保留署名
- 仅限非商业使用
- 衍生版本需继续遵守同类共享要求

This repository currently carries `CC BY-NC-SA 4.0`. See [`LICENSE`](./LICENSE) for details.

That means:

- attribution is required
- non-commercial use only
- share-alike applies to derivatives
