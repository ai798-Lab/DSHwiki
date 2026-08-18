---
标题: Harness 对决：Claude Code vs OpenCode vs Pi——质量相同，路径悬殊
类型: 社区讨论
来源平台: Reddit r/LocalLLaMA
原始链接: https://www.reddit.com/r/LocalLLaMA/comments/1v7d8px/harness_showdown_claude_code_vs_opencode_vs_pi/
发布日期: 2026-07-26
热度: 283 赞 / 140 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-07-28）
语言: 英文
作者: u/xquarx
---

## 中文摘要
DSH 发布前两周多的高热对比帖，是理解「harness 到底改变什么」的最佳社区实验。楼主在本地 vLLM 上以约 180 tok/s 跑 DeepSeek V4 Flash（唯一变量就是 harness），用自己的真实工作负载对比 Claude Code、OpenCode、Pi 三者。结论反直觉：三个 harness 最终产出的代码 diff 基本相同（质量无差异），但耗时和 token 消耗差异巨大——Claude Code 落地相同 diff 要花最快者近 4 倍的时间；差异全部来自系统提示词、工具结构和调用路径（「Pi 靠推理，OpenCode 靠委派，Claude Code 太爱探索代码库」）。评论区高赞把话挑明：「harness 本质上就是一套提示词。Claude Code 的上下文里塞满了行为指令的膨胀内容，OpenCode 膨胀少且可精简，Pi 最干净、可以整个换掉」。这为一周后 DSH 的「万物皆插件、一切可换」提供了完美的需求侧注脚。

## 原文要点/摘录
帖子正文摘录：
> the quality did not change, each harness made the same code diffs, but took wildly different paths to get there... like «Pi reasons, OpenCode delegates», while Claude Code loves exploring the code base, maybe too much.
>（质量没变，三个 harness 生成了相同的代码 diff，但路径截然不同……「Pi 靠推理，OpenCode 靠委派」，而 Claude Code 太爱探索代码库了，可能爱过头了。）
> 完整数据：https://nqawhc.github.io/articles/harness-efficiency-not-quality/

高赞评论：
- [37 赞] u/Paku93：「harness 实际上就是一套提供给模型的提示词。Claude Code 上下文里塞了一大堆『模型应该如何行动』的自定义指令，不是秘密。OpenCode 膨胀得少、还能继续精简（据我所知只有工具定义不好改）。Pi 是三者里最干净的，而且可以整个换掉。」
- [14 赞] u/1ncehost：「`/goal 迭代优化这段代码。持续迭代直到我叫停。把实验和性能指标写进 OPT_LOG.md。只提交成功的优化。`」（无限迭代玩法示范）
- [10 赞] u/mdziekon：「但它是闭源的。」（指 Claude Code，引出开源 harness 需求）
- [10 赞] u/Littlepharaoh：「他们确实砍了系统提示词，但那不是 harness 里最大的负担，大头是其他那些定义——砍的是 15-20% 里的 80%。」
- [7 赞] u/ea_man：「很多日常任务可以关掉 reasoning 跑，token 能省到 1/4（生成 2k 而不是 8k），速度和上下文长度都受益。」
- [5 赞] u/akaifox：「别用自带的 build 和 general（agent），自己建 main 和 worker，只要给了自定义提示词，默认那套就不会加载。」（OpenCode 去膨胀技巧）

## 素材价值点
1. 「harness 不改变质量、只改变效率」+「harness 本质是提示词包」是文章解释 DSH 设计哲学（为什么要让一切可换）的最有力社区证据。
2. Claude Code 上下文膨胀、闭源两点吐槽，正是 DSH「开源+极简内核+插件化」的对位卖点，适合做对比段落。
3. 关 reasoning 省 75% token、自建 agent 去膨胀等技巧，可迁移为 DSH 配置建议。

## 配图
- 帖子头图（对比图表）：https://i.redd.it/93nz4nc02gfh1.png
