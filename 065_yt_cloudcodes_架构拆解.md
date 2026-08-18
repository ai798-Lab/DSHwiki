---
标题: Cloud Codes：DeepSeek Harness 架构拆解——背后疯狂的软件工程
类型: 教程
来源平台: YouTube
原始链接: https://www.youtube.com/watch?v=1NyOG9z9RT0
发布日期: 2026-08-15
热度: 播放 43,600 / 点赞 1,199 / 评论 85（yt-dlp 实抓，采集于 2026-08-18）
语言: 英文
作者: Cloud Codes（3.53 万订阅，系统设计频道）
---

## 中文摘要

全网技术含金量最高的 dsh 视频之一：21 分钟专讲架构，不做安装教学。核心是解释 dsh 的「黄金工程法则」——「模型可见 ⟺ 持久引用」（model-visible ⟺ durably referenced）：模型看到过的内容必须被持久记录，历史对话一旦被修改就会打破前缀缓存（prefix caching），token 成本能翻 120 倍；dsh 用只增不改（append-only）的事件溯源架构规避了这一点，还把「上下文压缩指令放到提示词最末尾」来解决压缩与缓存的冲突。这套解释是理解「为什么 dsh 要这样设计插件和会话日志」的钥匙，也是量子位实测里「缓存命中率 99%+」的原理版答案。

## 原文要点/摘录

- 核心问题（视频简介原句大意）：为什么 7.2 万开发者在 24 小时内 star 了 dsh？让长上下文 agent 会话便宜 120 倍的那条黄金工程法则是什么？
- 黄金法则：model-visible ⟺ durably referenced（模型可见的内容必须持久可引用）；修改历史轮次会使前缀缓存失效，token 成本最高放大 120 倍。
- 架构定性：append-only event-sourced architecture（只增不改的事件溯源架构），即 `npx @deepseek-ai/dsh web` 背后的系统设计。
- 上下文压缩方案：把摘要指令移到提示词最末端，避免破坏缓存前缀。
- 内容覆盖：系统设计、编译器架构、插件机制（plugin mechanics）三块。

## 素材价值点

1. 「改一句历史消息，成本翻 120 倍」是向读者解释「为什么插件都围着会话日志转」的最戏剧化数字。
2. 与量子位「缓存命中率 99%+」实测互为因果，可在文章里串成「原理→实测」链条。
3. 讲插件机制（plugin mechanics）的段落可为文章的机制示意图提供画面参考。

## 配图

- https://i.ytimg.com/vi/1NyOG9z9RT0/maxresdefault.jpg （视频封面）
