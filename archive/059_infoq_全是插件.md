---
标题: InfoQ 中文：DeepSeek 把 Harness 开源了——模型、工具、Agent Loop 全是插件
类型: 新闻分析
来源平台: InfoQ 中文站
原始链接: https://www.infoq.cn/article/de9AljWc4ejW2KAyW8dD
发布日期: 2026-08-14
热度: 未获取（站方不公开阅读数，采集于 2026-08-18）
语言: 中文
作者: Tina
---

## 中文摘要

InfoQ 这篇的独特价值在于「工程视角的冷静评估」：既承认插件边界做得深（工具调用要过 Hook、审批、权限检查、沙箱这一整条可插拔流水线），也直说了风险——插件边界越深，接口稳定性、版本兼容和调试复杂度越难控制，v0.1 阶段核心接口还在快速变化，现在深度投入的迁移成本不低。它还是唯一把 dsh 的多 agent 编排范式讲全的中文媒体：Spawn、Fork、Pipeline、Ralph Loop 四种方式全是可配置插件，甚至能把 Claude Code、Codex 或任何支持 ACP 协议的外部 agent 接到同一个子 agent 接口上。结论克制：架构有诚意，但编排范式都有成熟先例，算「开源 harness 里的先进水平」而非范式革命。

## 原文要点/摘录

- 关键句：「模型只负责预测下一步，Harness 决定模型能看到什么、可以调用哪些工具、如何组织上下文」。
- 关键句：「插件系统提供的是差异化空间，最终效果还要由具体实现兑现」——即「什么都能换」不保证更高成功率。
- 多 agent 编排范式（全部为可替换插件）：
  - Spawn —— 启动全新上下文的子 agent
  - Fork —— 继承已有会话的子 agent
  - Pipeline —— 流水线式组织
  - Ralph Loop —— 多 agent 轮次接力
  - Workflow 工具中的 parallel() 并行原语
- 外部 agent 接入：Claude Code、Codex、支持 ACP 协议的产品可挂到同一子 agent 接口。
- 优点：工具调用流水线（Hook→审批→权限→沙箱）全程可插拔；统一事件流支持会话追踪、回放、对比；Cordis 负责加载/卸载/依赖。
- 批评：接口快速变化、调试复杂度、编排非首创、效果依赖默认插件质量。

## 素材价值点

1. Spawn/Fork/Pipeline/Ralph Loop 清单是介绍「编排类插件」的权威中文来源。
2. 批评观点可直接用于文章的「什么人现在别上车」小节，平衡吹捧语气。
3. 「工具调用四道关卡皆可插拔」适合做一张流程配图的脚本。

## 配图

- https://static001.infoq.cn/resource/image/86/ed/86d5d2e70ea1df1a88b95e488305d4ed.jpg （文章配图）
