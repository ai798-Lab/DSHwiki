---
标题: 开源一天后的社区突破：dsh-anchored-standard 插件把基准分从 91 拉到 98+
类型: 社区讨论
来源平台: Reddit r/accelerate
原始链接: https://www.reddit.com/r/accelerate/comments/1vpcvce/deepseek_harness_being_opensource_is_allowing_the/
发布日期: 2026-08-15
热度: 47 赞 / 2 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-17）
语言: 英文
作者: u/stealthispost
---

## 中文摘要
「开源红利」的教科书案例帖，也是本次收集里最重要的单体插件素材。帖子完整拆解了社区插件 dsh-anchored-standard（作者 xiaobright）的原理：既然发现 V4 Pro 对「第一次请求看到的环境」极度敏感（DSH Minimal 模式≈RL 训练环境，基准分 99/96，而 Standard 模式只有 91），但一直呆在 Minimal 又会失去 Standard 的全部实用工具，那就做个混合插件——第一次模型请求时呈现和 Minimal 几乎相同的环境（把模型「锚定」到 RL 训练出的更强推理轨道上），从第一个真实工具调用开始解锁完整 Standard 工具集。实测基准分 98/99，接近 Minimal 却保留全部功能。作者还做了控制变量实验：第一轮请求的工具 schema 是决定性变量——用真 Minimal 工具 schema 时 5/5 进入理想行为，用 Standard 风格 schema 时 11/11 变回 Standard 行为。发帖人的立意也很适合引用：「这不是什么玄学 prompt 增强器」，而是开源 harness 让社区在一天之内做出的可验证突破。

## 原文要点/摘录
帖子核心数据：
| Harness 配置 | 基准分 |
|---|---|
| Standard | 91 |
| PTC | 92 |
| Minimal | 99 / 96 |
| Anchored Standard | 98 / 99 |

> **Anchored Standard** (xiaobright/dsh-anchored-standard) does a clever hybrid: 1. First model request: presents V4 Pro with essentially the same environment as Minimal... 2. As soon as it makes its first real tool call/reply, it unlocks the full Standard toolset...
>（Anchored Standard 做了聪明的混合：1. 第一次模型请求时呈现与 Minimal 基本相同的环境……2. 一旦发生第一次真实工具调用/回复，就解锁完整 Standard 工具集……）
> The author found that the tool schema on that first request appears to be the decisive variable.
>（作者发现第一次请求携带的工具 schema 是决定性变量。）

评论（共 2 条）：
- [5 赞] u/icatel15：「有意思——有出处吗？还是只有 git？」
- [3 赞] u/stealthispost（楼主）：贴出出处，即 r/DeepSeek 的「Down the rabbit hole」帖（1votndx）。
- [1 赞] u/PolychromeMan：「说实话我得让 ChatGPT 先给我讲解一遍……我对 AI 的热情很大一部分就在于开源社区能这样用它，而不是前沿厂商那些封闭产品。」

## 素材价值点
1. dsh-anchored-standard 是「插件推荐」文章的头号种子选手：有名字、有作者（xiaobright）、有原理、有对照实验数据（91→98/99）、有安装价值，是「插件真的能改变模型表现」的最强实证。
2. 「Standard/PTC/Minimal/Anchored Standard」四种配置的分数表可直接复用为文章图表。
3. 「开源第 1 天社区就做出机制级突破」这条时间线，是「为什么 Everything is a Plugin 架构重要」的最佳论据。

## 配图
无（帖内为文字+表格）
