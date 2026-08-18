---
标题: Hugging Face 工程师 elie：DSH 能把 Claude Code 和 Codex 当子 agent 调用
类型: 社区讨论
来源平台: X/Twitter
原始链接: https://x.com/eliebakouch/status/2087904176357437820
发布日期: 2026-08-13
热度: 1.3k 赞 / 47 回复（采集于 2026-08-18；转发数未获取）
语言: 英文
作者: @eliebakouch（elie，Hugging Face 研究工程师）
获取方式: 直接抓取（Twitter syndication 接口）
---

## 中文摘要
Hugging Face 研究工程师 elie 在官宣 1 小时后发布的上手解读，是英文圈传播最广的技术向单帖之一（1.3k 赞）。核心信息量：DSH 实际是一个 Web UI 内嵌多个 harness 的结构，可以通过 SDK 把 Claude Code 和 Codex agent 当作子 agent 生成调用；默认支持多种「mode」（本质是不同 harness）：带程序化工具调用（TypeScript）的 code mode、bash+edit 模式等。附截图。这条帖直接支撑「DSH 不是又一个 CLI 编码代理，而是能吞下其他家 agent 的容器」这一叙事。

## 原文要点/摘录
原文（正文有截断）：
> amazing release. it's a web UI with multiple harnesses inside it, you can spawn claude code and codex agent through their SDK
>
> "deepseek harness" supports different "modes" by default (which are harnesses): code mode with programmatic tool calling (in typescript), bash+edit […截断]

中译：
> 非常出色的发布。它是一个内嵌多个 harness 的 Web UI，你可以通过 SDK 生成（spawn）Claude Code 和 Codex agent。
> DeepSeek Harness 默认支持多种「模式」（本质上就是不同的 harness）：带程序化工具调用（TypeScript 实现）的 code mode、bash+edit 模式……

## 素材价值点
- 「能把 Claude Code / Codex 当插件/子 agent 用」是插件推荐文章的天然钩子，此帖是该说法的高热度出处
- 点出 mode = harness 的设计（code mode / bash+edit / minimal 等），可作为文章讲解 DSH 模式系统的引用
- 大 V 背书样本：Hugging Face 工程师视角的正面评价

## 配图/视频
- 截图：https://pbs.twimg.com/media/HPm4yO-WUAAE8Q1.jpg
