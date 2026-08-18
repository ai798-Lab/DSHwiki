---
标题: dsh 的 Skill 机制——技能目录也是插件，本地远程随便换
类型: 官方文档
来源平台: GitHub
原始链接: https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/subsystems/skills.md
发布日期: 2026-08-13
热度: star 149,856（主仓库，采集于 2026-08-18）
语言: 英文（有中文版 skills.zh.md）
作者: deepseek-ai
---

## 中文摘要
dsh 里的 Skill 是「给 agent 的可复用说明书」，和 Claude Code 的 skill 概念同源，但实现完全插件化：skill 能力family分四个包——`dsh-skill` 定义注册接口（ctx.skills）、`dsh-skill-filesystem` 从本地文件系统发现技能、`dsh-skill-badge` 提供内置示例技能、`dsh-tool-skill` 把技能目录和加载器暴露给模型。关键设计是 **provider 中立**：技能来源可以是本地目录、打包内置，也可以是远程注册中心，模型看到的目录和 `skill` 工具完全不变；换句话说社区可以自己做「技能商店」插件而不用动核心。多来源同名冲突有明确规则（离会话最近的一层直接赢），preset 级挂载的技能只在该 preset 里可见。这解释了为什么 topic 下大量 `xxx-skill` 仓库能直接被 dsh 吃进来。

## 原文要点/摘录
- "This capability remains outside the core control spine and can use local, embedded, or remote providers without changing the model-facing contract."（skill 能力在核心控制链之外，可换本地/内嵌/远程 provider，而模型侧接口不变）
- 注册表是 host + per-scope 分层：全局层与 preset 层叠加，最近的层同名直接胜出
- 提供方接口极简：`list()` 列出候选技能、`get()` 取完整技能体，异步、可取消
- `skills/change` 事件通知目录变化，消费者自行刷新快照
- 生态呼应：colleague-skill（23k star）、archify（13.8k star）、Vibe-Skills 等热门仓库都是 skill 形态；awesome-dsh-plugin 列表单设 Skills 分类

## 素材价值点
1. 帮读者厘清「插件 vs skill」两个词的关系：skill 是内容层能力，本身由插件机制承载
2. 「技能商店可以由社区自己做」是插件推荐文里推荐 skill 管理类插件的铺垫
3. 与 Claude Code skill 的相似性可做迁移类比（会写 SKILL.md 的人无缝上手）

## 配图
无
