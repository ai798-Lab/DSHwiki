---
标题: The Register：DeepSeek 的创新 harness 把一切都当插件
类型: 新闻分析
来源平台: The Register
原始链接: https://www.theregister.com/ai-and-ml/2026/08/14/deepseeks-innovative-harness-treats-everything-as-a-plug-in/5288095
发布日期: 2026-08-14
热度: 未获取（站方不公开阅读数，采集于 2026-08-18）
语言: 英文
作者: Thomas Claburn（AI 与软件条线记者）
---

## 中文摘要

英国老牌科技媒体 The Register 的分析文，比单纯报道多走了一步：它把 harness 讲成了「AI 的中间件层」——负责管提示词、上下文、工具调度和安全，模型好不好用，一半看 harness。文章给了一个非程序员也能懂的对比：同一个模型配不同 harness 表现差别巨大，比如 Pi 的系统提示词只有 200 个 token，而 Claude Code 曾经用到 10000 个。DeepSeek 的创新在于「动态可组合」：插件可以在系统不重启的情况下随时装上、拔掉（对比 VS Code 删扩展要重启宿主）。文章还点出一个行业风向：中国 AI 实验室在做架构创新，美国同行反而在防守。Pi 联合创始人 Armin Ronacher 公开说这个设计「启发」了他重新思考自己的方案。

## 原文要点/摘录

- Harness 定位：AI harness 是管理提示词、上下文、工具编排与安全的中间件层；同类产品有 Claude Code、Codex、Aider、Cline、Pi。
- 关键对比：Pi 用约 200 token 的极简提示词，Claude Code 曾用约 10000 token——同一模型在不同 harness 下表现差异显著。
- 核心创新：dynamic composability（时间与空间两个维度的动态可组合性），组件增删不需要重启系统；对比 VS Code 扩展模型删组件要重启宿主。
- 追溯机制："Everything the model sees is recorded in an append-only session log: system prompts, reasoning, tool calls"（模型看到的一切都记录在只增不改的会话日志里：系统提示词、推理过程、工具调用），支持检查、回放、分叉推理步骤。
- 行业反应：Pi agent 联合创始人 Armin Ronacher 表示该设计 "inspired"（启发）他重新审视现有方案，尤其是开源承诺部分。
- 竞争视角：文章认为这标志着竞争焦点从模型性能转向基础设施设计，中国实验室扮演创新者角色。

## 素材价值点

1. 「200 token vs 10000 token」是全网最好懂的 harness 重要性论据，文章开头讲「为什么 harness 值得关心」时可以直接用。
2. 「不重启就能插拔」对比 VS Code，是向非程序员解释 dsh 插件机制的最佳类比。
3. Armin Ronacher（Flask 作者、Pi 联创）的背书可作第三方权威引用。

## 配图

无（文中未提供可下载配图）
