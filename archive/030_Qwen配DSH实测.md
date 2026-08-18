---
标题: 「Qwen 3.8 27b 配 DSH 太惊艳了」——DSH 跑第三方模型的 10 小时实测
类型: 社区讨论
来源平台: Reddit r/LocalLLaMA
原始链接: https://www.reddit.com/r/LocalLLaMA/comments/1vpv12b/qwen_38_27b_with_dshdeepseek_harness_is_amazing/
发布日期: 2026-08-16
热度: 139 赞 / 46 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-17）
语言: 英文
作者: u/cviperr33
---

## 中文摘要
证明 DSH 不只是「DeepSeek 模型专用」的关键帖：楼主在单张 RTX 3090（230W 限功耗）上用 DSH 跑本地 Qwen 3.8 27b，结论是试过一圈 harness 后「被 DSH 惊艳到了」——连跑 10 小时不停、不失败、不报错；上下文到 90k 时自动压缩且不丢失任务脉络；累计吃了 1000 万输入 token 仍不偏离目标、大多数问题一次搞定。缺点是速度：上下文变大后平均 37 tok/s（新会话 50+）。楼主还给出了完整可复现配置（UD q4 k xl 量化 + vision F16、92k 上下文、MTP + ngram 开启、GPU layers 66、不做 CPU offload），并指出默认 xHigh thinking 是效果好的原因（有时会思考 20 分钟才动笔）。评论区补充了实用优化：换 int4 autoround 量化可在一张 3090 上做到 70-90 t/s、256k 上下文、接近 q8 精度；把 thinking 从 xHigh 降到 high 能省约 50% 思考 token 且结果几乎一样。这是「DSH 万物皆插件（连模型都是插件）」最有说服力的实战案例。

## 原文要点/摘录
帖子正文摘录：
> It doesnt stop, it doesnt fail and it doesnt error. I have it running for 10 hours, even tho im at 90k contex it auto compresses on its own and doesnt loose track of where it was and what it was doing. 10mil input tokens it has gone thro, it does not diviate from its goal and oneshots every problem.
>（它不停、不失败、不报错。连跑 10 小时，哪怕到了 90k 上下文也会自动压缩，不丢失自己在哪、在干什么。已经吃了 1000 万输入 token，从不偏离目标，每个问题都一次搞定。）
> 配置：UD q4 k xl + vision F16、92k 上下文、MTP + ngram 开启、GPU layers 66、无 CPU offload；RTX 3090 限 230W。

高赞评论：
- [22 赞] u/bigsmokaaaa：「3090 可以用 int4 autoround（量化），单卡 256k 上下文能跑 70-90 t/s，精度接近 q8。」
- [8 赞] u/fbms2：「酷，那我得试试了，谢谢。」
- [1 赞] u/snapo84：「直接把 xhigh 换成 high thinking——差异微乎其微，思考 token 能省大约 50%，结果完全一样。」
- [1 赞] u/cviperr33（楼主）：「harness 就是你和 LLM 之间的通信层。你说的那些都不错，但试试 deepseek harness，一周前刚发布。」（楼主给新人科普）

## 素材价值点
1. 「DSH + 非 DeepSeek 模型」的标杆案例：连模型都是插件，本地 Qwen 也能吃到 DSH 的自动上下文压缩和长任务稳定性——文章讲「DSH 不锁定 DeepSeek」时的核心素材。
2. 自动上下文压缩（90k 不丢线索）是 DSH 内置能力中被点名最多的亮点之一，与社区记忆类插件形成呼应。
3. 完整的本地部署参数（量化、上下文、MTP/ngram、思考档位）可直接整理成文章的「本地党配置清单」。

## 配图
- 帖子头图（运行截图）：https://preview.redd.it/wkg27e152qjh1.png?width=853&format=png&auto=webp&s=2e3f8b11ea6393041f501e95c5835f9bea0245dd
