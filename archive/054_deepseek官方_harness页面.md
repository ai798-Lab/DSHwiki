---
标题: DeepSeek Harness 官方英文页面（第一手权威信息）
类型: 新闻分析
来源平台: DeepSeek 官网
原始链接: https://deepseek.com/harness/en/
发布日期: 2026-08-13
热度: 该页面为 HN 736 分头条的原始链接（采集于 2026-08-18）
语言: 英文
作者: DeepSeek 官方
---

## 中文摘要

官方落地页，一切表述以这里为准。定位：构建 AI 智能体的开发者预览版框架，强调模块化——「每一项能力都是可替换、可重组的插件」，改能力不用动核心源码。插件系统建立在 Cordis 内核上，内核只管插件的挂载和依赖管理，插件之间通过 Cordis 的服务（services）和事件（events）通信；组合靠配置文件完成而不是改代码。页面明确给出社区插件的官方入口：GitHub 上打 `dsh-plugin` 标签的仓库。值得注意的是 HN 网友评价「落地页比 GitHub README 信息量大」，写文章查证时建议优先看这里和文档站。

## 原文要点/摘录

- 核心主张："every capability is a plugin that can be swapped or recomposed"（每项能力都是可替换、可重组的插件）。
- 四种运行模式：Standard、Code、Minimal、Creator；插件化范围覆盖 models、tools、skills、sessions、sandboxes、storage、loops、scheduling、UI。
- 只增不改（append-only）会话日志，保证全程可追溯。
- 快速开始：`npx @deepseek-ai/dsh web`；源码安装：`git clone https://github.com/deepseek-ai/deepseek-harness`。
- 关键链接：
  - GitHub 仓库：https://github.com/deepseek-ai/deepseek-harness
  - 开发者文档：https://deepseek-harness.github.io/deepseek-harness/en/guide/quickstart
  - 社区插件入口：https://github.com/topics/dsh-plugin （官方指定的插件发现方式）
  - Cordis 论文：https://github.com/cordiverse/paper

## 素材价值点

1. `dsh-plugin` GitHub topic 是官方认可的插件发现渠道——「插件推荐」文章里「去哪找插件」一节的第一入口，必写。
2. 官方页面自带两张产品截图（插件设置界面、轨迹视图），是最「名正言顺」的配图来源。
3. 所有技术表述的最终查证来源；与媒体转述冲突时以此为准。

## 配图

- 官方页面内嵌两张截图：插件设置界面（Plugin settings）、会话轨迹视图（Trajectory view）。建议直接访问 https://deepseek.com/harness/en/ 右键保存，或用 The New Stack 转载的同源图：
  - https://cdn.thenewstack.io/media/2026/08/da2cbcb1-feat-plugin.en_-1024x640.png
  - https://cdn.thenewstack.io/media/2026/08/b0af4f5e-trajectory-real-view.en_-1024x640.png
