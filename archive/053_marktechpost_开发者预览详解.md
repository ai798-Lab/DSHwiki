---
标题: MarkTechPost：DeepSeek Harness 开发者预览版技术详解
类型: 新闻分析
来源平台: MarkTechPost
原始链接: https://www.marktechpost.com/2026/08/17/deepseek-ai-releases-deepseek-harness-in-developer-preview/
发布日期: 2026-08-17
热度: 未获取（站方不公开阅读数，采集于 2026-08-18）
语言: 英文
作者: Asif Razzaq
---

## 中文摘要

MarkTechPost 这篇是发布四天后的「冷静版」技术盘点，适合当规格说明书用。要点：dsh 是 v0.1 开发者预览版、MIT 协议，核心公式「Agent = Model + Harness」（智能体 = 模型 + 运行框架）；它明确定位是给开发者的基础设施，不是拿来就能用的成品，目标用户是 AI 创业公司、企业平台团队和研究机构。文章把插件化的范围列得最全：模型、工具、技能、会话、沙箱、存储、循环、调度、UI 全部可换。四种运行模式（标准/Code/极简/创造）和支持的模型服务商清单也很完整——不止 DeepSeek，Anthropic、OpenAI、AWS Bedrock、Google Vertex、Azure 都能接。

## 原文要点/摘录

- 核心理念："Agent = Model + Harness"；v0.1 开发者预览，MIT 协议，命令行简称 `dsh`。
- 架构：基于 Cordis 元框架；可替换插件涵盖 models、tools、skills、sessions、sandboxes、storage、loops、scheduling、UI 九大类。
- 四种运行模式：Standard（完整编码 agent）、Code Mode（多步 TypeScript 操作组合工具）、Minimal（只保留两个工具，用于基准测试）、Creator Mode（运行时自检与插件实验）。
- 模型支持：DeepSeek、Anthropic、OpenAI、AWS Bedrock、Google Vertex、Azure 及 OpenAI 兼容端点。
- 安装：`npx @deepseek-ai/dsh web` 或 Python SDK（需 Python 3.10+）。
- 关键句："Everything the model sees is written to an append-only session log. That includes system prompts, reasoning, tool calls and results, subagent scheduling, and every context injection."（模型看到的一切都写入只增不改的会话日志，包括系统提示词、推理、工具调用及结果、子智能体调度和每一次上下文注入。）

## 素材价值点

1. 九大插件类别清单（models/tools/skills/sessions/sandboxes/storage/loops/scheduling/UI）是文章里画「插件版图」示意图的最佳骨架。
2. 四种运行模式的准确英文名和用途，写安装上手章节可直接引用。
3. 多模型服务商支持清单说明 dsh 不锁定 DeepSeek 自家模型——这是推荐插件生态时的重要卖点。

## 配图

无（文中未提供可下载配图）
