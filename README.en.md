# GPTgps

[切换到简体中文 / Switch to 简体中文](./README.zh-CN.md)

GPTgps is a multi-site browser extension for navigating long AI conversations. It helps you find earlier prompts, split large chats into segments, add markers and notes, and generate AI summaries from saved context.

## Overview

As AI chats grow longer, a few problems become unavoidable:

- it becomes hard to jump back to an earlier key prompt
- one conversation often contains several different topics
- you may want bookmark-like anchors inside the chat body
- a compact summary is often more useful than rereading the whole thread

GPTgps solves this with an in-page sidebar, segmentation workflow, marker system, and AI-assisted summaries.

## Supported Sites

- ChatGPT
- Gemini
- Qwen / Tongyi / Qianwen
- Doubao
- Claude

## Core Features

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

## AI Providers

Current summary backends include:

- OpenAI-compatible APIs
- Qwen DashScope CN / Intl / US
- Qwen Coding endpoint
- MiniMax
- Custom OpenAI-compatible endpoints

## Install

### Chrome / Edge

1. Clone or download this repository.
2. Open `chrome://extensions`.
3. Turn on `Developer mode`.
4. Click `Load unpacked`.
5. Select `./dist_mv3`.

### Firefox

1. Open `about:debugging#/runtime/this-firefox`.
2. Click `Load Temporary Add-on`.
3. Select `./dist_mv2/manifest.json`.

## Build

- Windows: `build.bat`
- macOS / Linux: `build.sh`

This regenerates the unpacked builds in `dist_mv2` and `dist_mv3` from source.

## Basic Usage

1. Open a supported AI chat page.
2. Open GPTgps from the floating button.
3. Use the sidebar to search, jump, split, pin, rename, and annotate.
4. If needed, open AI settings to configure provider, model, base URL, language, and summary display limits.
5. You can also use `Tools` for diagnostics, export, and import.

## Documentation

- Chinese quick start: [docs/快速使用-中文.md](./docs/%E5%BF%AB%E9%80%9F%E4%BD%BF%E7%94%A8-%E4%B8%AD%E6%96%87.md)
- Regression checklist: [docs/nav-regression-checklist.md](./docs/nav-regression-checklist.md)
- Release workflow: [docs/GitHub发布流程.md](./docs/GitHub%E5%8F%91%E5%B8%83%E6%B5%81%E7%A8%8B.md)

## Current Status

This release is focused on long-chat navigation and multi-site support.

Stable for day-to-day use:

- ChatGPT
- Gemini
- Qwen
- Claude
- Doubao

Still being refined:

- Consecutive image-only messages may later be collapsed into a more compact expandable group

## Known Limitations

- AI summaries depend on the provider and API key you configure
- Multi-site adapters rely on live DOM structure and may require selector recalibration after upstream UI changes
- Image-only turns are preserved with placeholders such as `[Image-only message]`; richer grouping for consecutive image-only messages is still planned

## Attribution

GPTgps started from the open-source Prompt Genius / ChatGPT Prompt Genius codebase and has since evolved into a long-conversation navigation product with a different core focus.

The current version is centered on:

- segment-aware navigation
- marker / checkpoint anchors
- improved jump accuracy
- AI summary orchestration
- multi-site adapters
- diagnostics and session restoration

## License

This repository currently carries `CC BY-NC-SA 4.0`. See [LICENSE](./LICENSE) for details.

That means:

- attribution is required
- non-commercial use only
- share-alike applies to derivatives
