---
标题: Web UI 使用指南与 CLI 入口——三步跑起第一个任务
类型: 官方文档
来源平台: GitHub
原始链接: https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/user/guide/index.md
发布日期: 2026-08-13
热度: star 149,856（主仓库，采集于 2026-08-18）
语言: 中英双语
作者: deepseek-ai
---

## 中文摘要
dsh 的默认形态不是命令行对话，而是本机 Web UI（这点在社区引发不少讨论，见 Discussions 素材）。使用指南只有三步：1）Settings → Models 填入 DeepSeek API key（不用重启即刻生效，也支持其他厂商和自定义 OpenAI 兼容端点）；2）Choose workspace 选择工作目录（不选目录不能开聊）；3）开会话发任务，agent 可以读改文件、跑命令、委派子任务、维护计划，需要审批的操作会先弹确认。CLI 侧由 `dsh` 启动器统一管理入口：`dsh web` 开 Web UI、`dsh --profile headless "任务"` 无界面跑一次性任务、`dsh plugin` 管理插件。另有 Python SDK 供程序化调用。

## 原文要点/摘录
- 入口模式表（apps/cli/README.md）：`dsh --profile <name>` 启动指定 profile；`dsh --profile headless "job"` 跑完打印答案即退出；`dsh web` 是 `--profile web` 的别名；`dsh plugin` 转发 pnpm 管理插件
- web 和 headless 两个 profile 首次使用自动从模板初始化；其他 profile 用 `dsh plugin` 创建
- 模型配置指南（providers.md）覆盖其他厂商与自定义 OpenAI 兼容端点；配置页有官方截图
- "The Web UI asks before operations that require approval under the active permission policy."（权限策略要求审批的操作，Web UI 会先询问）
- 延伸阅读入口：Python SDK 指南、其他 CLI 模式、插件开发教程

## 素材价值点
1. 文章「上手」小节可直接照抄三步流程，非程序员也能跟着做
2. 「默认是 Web 不是终端」是 dsh 和 Claude Code/Codex 的显著差异，也是 TUI/桌面类插件火爆的原因（与插件推荐主线强相关）
3. headless 模式一句话即可交代（自动化场景入口）

## 配图
- https://raw.githubusercontent.com/deepseek-ai/deepseek-harness/master/docs/user/guide/providers-models-page.zh.png （模型设置页中文截图）
- https://raw.githubusercontent.com/deepseek-ai/deepseek-harness/master/docs/user/guide/providers-custom-form.zh.png （自定义模型表单中文截图）
