---
标题: MindStudio：什么是 DeepSeek Harness？插件化编码 agent 解读 + 实测
类型: 新闻分析
来源平台: MindStudio Blog
原始链接: https://www.mindstudio.ai/blog/deepseek-harness-agentic-coding
发布日期: 2026-08-14
热度: 未获取（企业博客不公开阅读数，采集于 2026-08-18）
语言: 英文
作者: Luis Chavez-Mattos（Director of Product）
---

## 中文摘要

AI 产品公司 MindStudio 的产品总监写的解读+实测文，比纯新闻多了两个独家信息点。第一，它是少数给出真实成本数据的英文文章：作者用 dsh 做了一个国际空间站（ISS）追踪应用，35 分钟消耗约 2000 万 token，但缓存命中率 100%，实际花费可控；作者建议日常编码任务用便宜的 Flash 模型而不是 Pro。第二，它明确验证了 dsh 最有话题性的能力：可以把竞争对手 Claude Code、Codex 当作「子 agent 插件」接进来，让 DeepSeek 当总指挥、对手当打工仔，组成多 agent 流水线。这一点对「插件推荐」文章是绝佳的钩子素材。

## 原文要点/摘录

- 定性：dsh 把工具、技能、会话、甚至竞争对手的 agent 都当作可替换组件，而不是写死的系统。
- 关键句："The harness itself is decomposable. Tools, skills, and even the underlying agent loop are plug-ins."（harness 本身就是可拆解的。工具、技能、乃至底层 agent 循环都是插件。）
- 实测数据：ISS 追踪应用，约 35 分钟、约 2000 万 token、缓存命中率 100%。
- 模型建议：常规编码任务选 Flash 比 Pro 更划算，推理强度（reasoning effort）可调。
- 子 agent 能力：明确支持把 Claude Code / Codex 作为插件式子 agent 编入 DeepSeek 编排的工作流。
- 自定义模型：MIT 协议 + YAML 配置即可接入任意模型服务商。

## 素材价值点

1. 「让 Claude Code 给 DeepSeek 打工」是插件推荐文章的天然爆点段落，此文是英文侧的实证来源（与 AI超元域视频的中文实测互为印证）。
2. 2000 万 token / 35 分钟 / 100% 缓存命中：为数不多的真实成本参照，可用于「用得起吗」小节。
3. 可开关的 Shell / 文件编辑 / 网页搜索插件与模式选择，是「哪些内置插件该开」清单的素材。

## 配图

- https://i.mscdn.ai/o/iZl0kkZU2R9KXyy7/a/3V2ICO3oSq2QZPii/generated-images/95881440-ab01-4778-bf65-c0e7ddd0f233.png （文章题图）
