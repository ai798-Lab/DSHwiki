# DSH Wiki · DSH 情报站

> DeepSeek Harness 生态站 · by ai798 Lab · [dshwiki.com](https://dshwiki.com)

DeepSeek Harness（dsh）2026-08-13 开源，六天冲到 149,851 star。这个站按时间轴记录它的每一步：大事记、部署上手、12 个精选插件的安装与用法、GitHub 动态、插件排行榜，以及 X 与 Reddit 上的真实评论。

全部数字与命令为 2026-08-18 实抓，逐条附原文链接；官方没有文档的地方（例如升级/卸载命令）如实标注，不做补白。

## 语言版本

简体中文（根目录）· [English](en/) · [日本語](ja/) · [한국어](ko/) · [ไทย](th/) · [العربية](ar/) · [Español](es/) · [繁體中文](zh-TW/)

## 目录

| 路径 | 内容 |
|------|------|
| `index.html` | 首页：大事记 / 部署 / 插件精选 / GitHub / 排行榜 / 评论墙 |
| `timeline.html` | 完整大事记（15 个节点，含实证数据与出处） |
| `deploy.html` | 部署指南（4 种安装方式、模型接入、启动、常见坑） |
| `plugins/` | 12 个精选插件详情（安装命令、上手步骤、真实评论） |
| `ranking.html` | 生态插件排行榜（25 个，按 star 排序） |
| `voices.html` | 评论墙（40 条 X / Reddit 真实评论，带原文链接） |
| `archive/` | 资料库：68 条一手素材的精读版与 Markdown 原文 |
| `site_data.json` | 站点结构化数据（插件 / 时间轴 / 评论 / 部署），供外部程序读取 |

## 构建

站点由生成器产出，不要手改这里的 HTML：

```
python3 _build/scripts/assemble_v2.py      # 四路实抓数据 → site_data.json + 简中文案母本
python3 _build/scripts/extract_data_strings.py  # 抽数据层可见中文 → 送翻
python3 _build/scripts/build_v2.py         # 读数据 + 8 个语言包 → 生成全站
```

源数据与语言包在仓库外的工作区（`_work/`、`_build/`），不随站点发布。

## 图标

界面图标来自 [sketchyicons](https://sketchyicons.com)（代码 MIT，图形派生自 [Lucide](https://lucide.dev)，ISC）。
两份许可证在网页中使用均无需页面署名，此处仅作出处标注。GitHub 标志使用官方 mark 原样单色，未做改造。

## 声明

素材版权归原作者所有，本站用于学习与研究，每条均标注来源并附原文链接。
