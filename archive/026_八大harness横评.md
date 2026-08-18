---
标题: 8 大 agent harness 横评：DeepSeek V4 Flash 与 Pi 是「天作之合」
类型: 社区讨论
来源平台: Reddit r/DeepSeek
原始链接: https://www.reddit.com/r/DeepSeek/comments/1vli5uf/i_ran_deepseek_v4_flash_on_8_agent_harnesses_and/
发布日期: 2026-08-11
热度: 307 赞 / 95 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-13）
语言: 英文
作者: u/LimpComedian1317
---

## 中文摘要
DSH 发布前两天最重要的对比基准帖，解释了「为什么模型和 harness 要配对」。楼主用 25 个真实自动化任务（涉及 Slack、Sheets、Gmail、PostHog 等多应用）测了 DeepSeek V4 Flash 在 8 个主流 harness 上的表现。结论：模型-harness 匹配度（model-harness fit）是真实存在的——同一个模型在不同 harness 上的通过率从 46.7% 到 66.7% 不等，单次成功成本从 $0.028 到 $0.195 差了 7 倍。Pi Agent 通过率最高（66.7%）且最便宜（$0.028/次成功），Claude Code 最快但最贵（缓存命中只有 1.5%，而 Codex 有 70%）。评论区最有信息量的现象：一堆人刷屏求测 Reasonix（专为 DeepSeek 打造的第三方 harness，在 DeepSeek 社区知名度很高），以及对 OpenRouter 路由不一致导致测试口径问题的方法论质疑。这个帖子是 DSH 发布的「前情提要」：正因为社区早就意识到 harness 决定模型发挥，DeepSeek 亲自下场做 DSH 才被寄予厚望。

## 原文要点/摘录
帖子核心数据表（原文为 Markdown 表格）：
| Harness | 通过率 | 中位耗时 | 工具调用 | 单次成功成本 |
|---|---|---|---|---|
| Pi Agent | 66.7% | 132.2s | 443 | $0.028 |
| Prime Agent | 62.5% | 242.1s | 502 | $0.131 |
| OMP | 56.7% | 272.4s | 390 | $0.103 |
| Claude Code | 53.3% | 122.7s | 358 | $0.195 |
| Codex | 53.3% | 245.0s | 448 | $0.081 |
| DeepAgents | 53.3% | 187.1s | 353 | $0.045 |
| Hermes Agent | 50.0% | 175.5s | 386 | $0.056+ |
| OpenCode | 46.7% | 129.7s | 419 | $0.073 |

> Claude Code and OMP both used about 742,000 tokens per task, but Claude Code still cost almost twice as much. It cached only 1.5% of its tokens, compared with 70% for Codex and 57% for OMP.
>（Claude Code 和 OMP 每任务都用约 74.2 万 token，但 Claude Code 贵了近一倍：它只缓存了 1.5% 的 token，Codex 是 70%，OMP 是 57%。）

高赞评论：
- [67 赞] u/Lucifer812：「缺了 reasonx。」（指 Reasonix）
- [31 赞] u/UhhReddit：「测试没有一致性：Pi 用 DeepSeek API high 档，其他走 OpenRouter——OpenRouter 背后是多家供应商，成本差异巨大。」（方法论质疑）
- [31 赞] u/LimpComedian1317（楼主）：「刚知道这个（Reasonix），可以加进基准，谢谢。」
- [26 赞] u/Useful-Buyer4117：「求测 reasonix。」
- [20 赞] u/sdexca：「为什么用 OpenRouter？DeepSeek 官方比第三方便宜差不多 10 倍。」
- [8 赞] u/UhhReddit：「Reasonix 是专为 DeepSeek 打造的 harness，在 DeepSeek 社区非常有名。」
- [8 赞] u/Odd_Antelope9098：「同意，这让我更想要一个正经的 harness 基准了。」

## 素材价值点
1. 给「插件推荐」文章提供核心论据：harness（及其配置）对同一模型的通过率和成本影响是数量级的——这正是为什么值得花时间配置 DSH 插件。
2. 缓存命中率对比（Claude Code 1.5% vs Codex 70%）是解释「DSH 原生缓存优化为什么重要」的最佳背景数据。
3. Reasonix、Pi、OMP、OpenCode 等竞品名单可用于文章的「生态位对比」段落；「Reasonix 被刷屏求测」说明 DeepSeek 专用 harness 赛道在 DSH 之前已有玩家。

## 配图
- 帖子头图（基准结果图）：https://i.redd.it/kckepzoczqih1.png
