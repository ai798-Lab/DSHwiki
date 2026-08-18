---
标题: dsh-token-anxiety：给「token 焦虑症」做的成本透视插件（附省钱结论）
类型: 社区讨论
来源平台: Reddit r/DeepSeek
原始链接: https://www.reddit.com/r/DeepSeek/comments/1vph1ig/deepseek_harness_dsh_plugin_to_show_the_cost_per/
发布日期: 2026-08-15
热度: 11 赞 / 0 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-17）
语言: 英文
作者: u/Snoo_57113
---

## 中文摘要
社区开发者发布的成本可视化插件 dsh-token-anxiety（名字自嘲「token 焦虑」）：在 DSH 0.1 里显示每任务成本、峰谷时段、涨价后同任务将花多少钱，还能看单条 prompt 成本、定位「哪些任务在烧钱、为什么」。比插件本身更有价值的是作者基于自己数据给出的省钱结论：开放式研究问题、打错字、prompt 不具体、工具调用 bug 这四类占了 50% 以上的 token 浪费；峰谷时段差价巨大；「PRO 只留给最难的问题，其他一律 flash max」；「没有严格控制就别用 subagents」。安装方式一行命令（dsh plugin --profile web add），甚至可以「把仓库地址丢给 agent 让它自己克隆安装」。赞数不高（新插件帖），但它和 deepseek-peak 一起构成了 DSH 生态里最先繁荣的「成本管理」插件类目，与 DeepSeek 涨价的时代背景严丝合缝。

## 原文要点/摘录
帖子正文摘录：
> I made a plugin (Token anxiety) for the deepseek harness 0.1 that shows the cost per task, the peak hours and how much a task would cost after the hike... As tips to reduce your bill I found that open research questions, typos, not being specific in the prompts and bugs in toolcalling make up 50%+ of the tokens.
>（我给 DSH 0.1 做了个插件「Token anxiety」：显示每任务成本、峰值时段、涨价后同任务的价格……省钱心得：开放式研究问题、打错字、prompt 不具体、工具调用 bug 加起来占了 50% 以上的 token。）
> - peak vs valley hours make a HUGE difference（峰谷时段差别巨大）
> - you should use PRO only for the HARDEST problems, flash max for everything else（PRO 只用于最难的问题，其余全用 flash max）
> - Dont use subagents unless you have strict control（没有严格控制就别用 subagents）
> 仓库：https://github.com/mov-eax-eax/dsh-token-anxiety
> 安装：`dsh plugin --profile web add /path/to/dsh-token-anxiety`，或者直接让 agent 克隆仓库自行安装。

（本帖 0 评论，无评论摘录。）

## 素材价值点
1. dsh-token-anxiety 插件（作者 u/Snoo_57113，GitHub: mov-eax-eax/dsh-token-anxiety）进推荐清单，「成本可视化」类目代表作之一。
2. 四大 token 浪费源 + 「PRO 只留最难问题」+「慎用 subagents」三条实操建议，可直接改写为文章的省钱小节。
3. 「把仓库丢给 agent 让它自己装插件」体现 DSH 插件安装的低门槛，是好细节。

## 配图
- 成本 widget 截图：https://preview.redd.it/w50emycpcmjh1.png?width=806&format=png&auto=webp&s=2797eb84d742931c2a848b33bbc57eb2071ad1aa
- hover 状态截图：https://preview.redd.it/x8kbvinkcmjh1.png?width=748&format=png&auto=webp&s=f133490cfe2d20d275beae2fd642aa8b14b8a688
