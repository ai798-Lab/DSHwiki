---
标题: 「掉进 V4-Pro 的兔子洞」：单一 API 背后疑似多版本，与 DSH Minimal 模式的玄学
类型: 社区讨论
来源平台: Reddit r/DeepSeek
原始链接: https://www.reddit.com/r/DeepSeek/comments/1votndx/down_the_rabbit_hole_of_deepseekv4pro0813/
发布日期: 2026-08-15
热度: 157 赞 / 23 评论（采集于 2026-08-18，数据来自 arctic-shift 存档，快照时间 2026-08-16）
语言: 英文（转译自中文社区）
作者: u/HeavyPanzerPlus1s
---

## 中文摘要
DSH 第一周最戏剧性的技术悬案帖，转译自 X 中文社区的长文。核心爆料：V4-Pro 的 API 背后疑似藏着三个「思维链指纹」不同的模型（「Let me…」型≈Pro Preview、「The user wants me…」型≈Flash、「We…」型明显更强的「神级版本」），而那个神级版本正是从 DSH 的 Minimal 模式里被挖出来的。关键证据链指向 DSH 仓库 8 月 10 日的一个 commit：`fix(preset): align minimal agent with RL composition`——官方工程文档明说「minimal preset 拥有完整的 RL agent 组合」：极简系统提示词 + 持久化 Bash 等，即模型强化学习训练时的原生环境。评论区把结论推进了一步：高赞跟帖认为「V4 Pro GA 在 DSH minimal 环境上过拟合了，其他环境下表现全部崩掉」，还有人贴出 composio 的独立测试佐证「V4 Flash 也是在极简的 Pi harness 里表现最好」。这个帖子把「harness 环境=模型发挥的决定变量」这件事从经验论推到了机制层，也是后来 dsh-anchored-standard 等插件爆火的直接背景。

## 原文要点/摘录
帖子正文摘录：
> The strangest part? The author who uncovered this third "God-tier V4 Pro" claimed it was pulled directly out of the DeepSeek Harness Minimal mode... a key commit appeared in the official DeepSeek Harness repository: `fix(preset): align minimal agent with RL composition`... The minimal preset owns the complete RL agent composition.
>（最诡异的是：挖出第三个「神级 V4 Pro」的作者称它就是从 DSH Minimal 模式里拉出来的……官方 DSH 仓库出现了关键 commit：「fix(preset): 将 minimal agent 与 RL 训练组合对齐」……官方文档明说 minimal preset 拥有完整的 RL agent 组合。）

高赞评论：
- [35 赞] u/Public_Ad_5096：「上文很多内容在社区分析过程中已经过时了。真正的答案没那么复杂……就是『DeepSeek v4 pro GA 在 DSH 的 minimal（环境）上过拟合了』。」（附图）
- [15 赞] u/KoalaOk3336：「感觉是真的。我在 web 应用里注意到有些 prompt 走正常推理、有些走『原始人式推理』，两者频繁切换——原始人式推理的回答几乎总是更好。」
- [11 赞] u/Public_Ad_5096：「如果你从发布起就重度用 v4 Pro GA，会发现它表现几乎和 v4f 一个水平，这本身就很怪。不知道官方什么时候修，最悲观可能要等三个月后的下一个模型。」
- [9 赞] u/somebrunoguy：「有意思。此前对 V4 Flash 的独立测试（composio.dev）也显示它在极简的 Pi harness 里表现最好。不知道是 DeepSeek 独有还是所有模型都在极简 harness 里更强。」
- [9 赞] u/bambamlol：「说人话就是：模型主要是在这个环境（DSH minimal 模式）里训练的，所以它在这里最强？」
- [7 赞] u/Public_Ad_5096：「实际上……它把其他所有环境下的表现都变成了彻底的白痴。事情就是这么严重。」

## 素材价值点
1. 「模型在训练环境（DSH minimal preset）里表现最强」是全文最硬核的机制级论据——直接解释为什么 DSH 的 preset/插件选择不是玄学而是科学，可作为插件推荐文章的理论支柱。
2. `fix(preset): align minimal agent with RL composition` 这个 commit 是可查证的一手证据（指向官方仓库）。
3. 相关帖链条可一并引用：r/DeepSeek「minimal 模式只在 Linux 下发挥真实力」帖（1voi3h2，75 赞/13 评论）与「值得注意的发现」帖（1vof8nl，93 赞/11 评论，含「第一轮 minimal、第二轮切回 high/max」的偏方玩法）。

## 配图
- 帖内配图（commit 截图）：https://preview.redd.it/cxp0i493ygjh1.jpg?width=1556&format=pjpg&auto=webp&s=818a29edcc3b375bf888e1de6df3b021a82966a7
- 评论区 u/Public_Ad_5096 的分析图：https://preview.redd.it/w8rmhzmgghjh1.jpeg?width=873&format=pjpg&auto=webp&s=241fd4d94c0ee2aaa9835f9e9af8159bc32e7e76
