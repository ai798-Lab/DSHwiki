---
标题: 「我的 DSH 第一印象」：慢、费 token、但把 DeepSeek 榨到极限
类型: 社区讨论
来源平台: Reddit r/DeepSeek
原始链接: https://www.reddit.com/r/DeepSeek/comments/1vnpt5n/my_first_impressions_of_deepseek_harness/
发布日期: 2026-08-13
热度: 87 赞 / 40 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-15）
语言: 英文
作者: u/LaxederBR
---

## 中文摘要
发布当天最扎实的一手实测报告，楼主是 Pi Harness 日常用户（TS+Vue 技术栈）。一句话总结：「慢、token 用量夸张、99% 缓存命中率、能把 DeepSeek 的性能榨到最大」。性能上，V4 Flash 在 DSH high 档的产出接近 GPT 5.6-luna low 档，重构任务表现稳定；易用性上则火力全开地吐槽：.agents 里的 skills 不会自动加载、文档讲不清楚、默认界面是中文得到处找英文选项、想用 CLI 模式但文档没写清楚能不能。最被点名的坑：插件多但没有描述，让人一头雾水。评论区反而出现了本次收集里最有价值的插件实证之一：u/214d 表示上手当天就用 DSH 自己写了 3 个插件（会话自动命名、git worktree 工作区、实时显示会话成本和余额），并给出「让 V4 Flash 给你写一个 dsh 插件」的玩法示范；多人证实 DSH 比 Claude Code 省 token、缓存命中 95~99%。反面评论也具体：@ 不能添加文件到上下文、系统提示词偏大导致资源消耗高。

## 原文要点/摘录
帖子核心（原文较长，摘要）：
> Summary: It's slow, uses way too many tokens, has a 99% cache hit rate, and gets the maximum performance out of Deepseek.
>（总结：慢、token 用量太大、缓存命中率 99%、能把 DeepSeek 性能榨到最大。）
> Usability: Very confusing. The skills in .agents don't load automatically... By default, it's in Chinese... The plugin-based system seems like it could be optimized like Pi Harness, but there are so many plugins with no descriptions that it gets confusing.
>（易用性：非常混乱。.agents 里的 skills 不自动加载……默认是中文……插件化系统看起来可以像 Pi Harness 一样被优化，但一堆插件连描述都没有，看得一头雾水。）

高赞评论：
- [16 赞] u/214d：「太好用了，我爱了。我已经写了 3 个插件（会话自动命名、git worktree 开工作区、实时显示会话成本和余额）。快（我用的是 2017 年的 MacBook Pro）、可靠、完全可定制、95-99% 缓存命中、又好看又极简。」
- [7 赞] u/Excellent_Can_3480：「我这跑 120t/s，比市面上很多 harness 都快。」
- [5 赞] u/214d：「这是『我』做的。直接开个新会话，让 DS v4 Flash 给你写一个在输入框下方显示余额的 dsh 插件就行。」（附成品截图）
- [3 赞] u/Stef43_：「我从 VS Code Continue 换到 Claude Desktop Code 再换到 DSH，很惊艳，它比 Claude Code 省 token。我无痛写了 3 个插件，非常便宜。」
- [3 赞] u/LaxederBR（楼主）：「『自己动手』没他们说的那么爽 xD 我让它给我建个极简 preset，代码多到我直接放弃。最难受的是用 JS——没有类型我怎么 debug？太原始了 xD」
- [3 赞] u/RandiyOrtonu：「兄弟，我还发现不能用 @ 把文件加进上下文 😢」
- [3 赞] u/LaxederBR（楼主）：「它和 GitHub Copilot 一个毛病：工具请求太多。看了下系统提示词，最小的都很大，工具定义估计也是，这就是资源消耗高的原因。」

## 素材价值点
1. 「用 DSH 让模型现场给自己写插件」（u/214d 的 3 个插件 + 余额显示插件教程式评论）是「插件推荐」文章里最有传播力的玩法素材——插件门槛低到一句话生成。
2. 被反复点名的插件方向：会话成本/余额显示、git worktree 工作区、会话自动命名——这些是社区自发需求最强的插件类型。
3. 坑点清单非常具体（skills 不自动加载、默认中文、@ 加文件缺失、插件无描述、系统提示词大），可直接写成文章的避坑段落。

## 配图
- 帖子头图（实测截图）：https://i.redd.it/ltgmed9g08jh1.png
- u/214d 的自制余额插件截图：https://preview.redd.it/xdisnwgj68jh1.jpeg?width=3024&format=pjpg&auto=webp&s=2f7ee107a9c6033dc70829b3c0cc6003b62047fb
