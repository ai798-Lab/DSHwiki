---
标题: ModLens——给纯文本模型「开天眼」的 dsh 首个视觉插件
类型: 插件
来源平台: GitHub
原始链接: https://github.com/liustack/modlens
发布日期: 2026-02-22（仓库创建）
热度: star 2,789（采集于 2026-08-18）
语言: 英文（有简体中文 README）
作者: liustack（独立开发者）
---

## 中文摘要
DeepSeek 和 GLM 的旗舰对话模型是纯文本的，看不了图——这是国产模型用户的日常痛点。ModLens 自称「dsh 首个视觉插件、也是所有纯文本编码 agent 的视觉桥」：往聊天框里直接粘贴图片，插件调用视觉引擎把图变成结构化 JSON 证据（OCR 文字、版面布局等）喂回文本模型，不用先存文件再传路径。README 文案很有独立开发者气质（自嘲徽章「Not backed by Y Combinator」「users unknown」），文档齐全：故障排查、输出契约、安全说明单独成页，还有姊妹项目 ModSearch（网页搜索）。对写文章的价值在于它精准补了 DeepSeek 模型的能力短板——「模型缺什么，插件补什么」的典型样本。star 数（2,789）在榜单里不算头部，但差异化极强。

## 原文要点/摘录
- "Give a text-only model sight, and just paste the image."（给纯文本模型视力，贴图就行）
- "The flagship DeepSeek and GLM chat models are text-only and cannot read images. ModLens is a plug-in vision engine that gives a text-only model sight."
- 输出为结构化 JSON 证据（OCR、layout 等），有明确 output contract 文档
- npm 包：@liustack/modlens；MIT 协议；作者活跃于 X（@liustack）
- 竞品参考：目录站 Vision & Multimodal 分类下还有其他视觉桥插件，ModLens 是该类目认知度最高的

## 素材价值点
1. 「DeepSeek 看不了图？装个插件」是极好的实用推荐点，读者痛点直接命中
2. 「模型的短板由插件生态补齐」呼应 Everything is a Plugin 主题
3. 独立开发者的自嘲式 README 可作为生态活人感/社区文化的引用素材

## 配图
- https://raw.githubusercontent.com/liustack/modlens/main/assets/banner.jpg （官方 banner）
