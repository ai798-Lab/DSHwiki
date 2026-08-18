---
标题: awesome-dsh-plugin——每条人工验货的插件精选清单（配套插件市场）
类型: 教程
来源平台: GitHub
原始链接: https://github.com/awesome-dsh-plugin/awesome-dsh-plugin
发布日期: 2026-08-13（与 dsh 开源同日创建）
热度: star 7,572（采集于 2026-08-18）
语言: 英文/中文/日文三语
作者: awesome-dsh-plugin（社区组织）
---

## 中文摘要
生态里最权威的插件清单（7,572 star，与 dsh 同日创建），核心卖点是**收录标准**：只收能用 `dsh plugin add` 装上、描述与实际一致、分类正确、仍在维护的插件，且每条提交都有人对照源码核验——「如果描述说有 46 个工具，就真有人去数」。清单明确声明不做排名不评质量，失联/停更的条目会被移除。列表分 20 个类目（UI 增强、用量计费、主题外观、模型 Provider、会话消息、记忆、工具能力、浏览器、视觉多模态、语音、文档渲染、Skills、工作流自动化、Git 代码审查、通知集成、开发运行时、安全权限、远程移动、插件市场、娱乐），grep 统计列表项约 1,250 行。配套生态：**dsh-market**（828 star）把整张清单做成 dsh 内置的可视化插件市场，一键安装/升级/换主题；**dsh-find-plugin** 让 agent 替你找插件。README 还有一段所有推荐文都该抄的安全警告：装插件等于用你的权限跑第三方代码，工具审批不会沙箱插件本身。

## 原文要点/摘录
- 收录门槛原文："An entry is added when the plugin installs with `dsh plugin add`, does what its one-line description says, sits in the right category, and is maintained. … if a description claims '46 tools', someone counts them."
- 安全警告："Installing a plugin runs third-party code on your machine with your own permissions — it can read your files, use your credentials, and reach the network. Tool approvals don't sandbox plugin code. Being on this list is not a security review."（装插件=用你的权限跑第三方代码，上榜不等于安全审查）
- dsh-market 安装：`dsh plugin --profile web add dshmarket`
- 20 个分类目录 + 徽章体系（awesome-dsh-plugin.com 提供 badge 和 count 接口）

## 素材价值点
1. 写推荐文的第一手选品池：分类体系可直接借用为文章结构
2. 安全警告段落建议原样翻译进文章（对小白读者是必要的负责任提醒）
3. dsh-market「清单变市场」的玩法本身是插件生态成熟度的标志性素材

## 配图
- https://awesome-dsh-plugin.com/banner-en.png （清单官方 banner）
- https://raw.githubusercontent.com/dsh-market/dsh-market/main/assets/demo-en.png （dsh-market 市场界面截图）
