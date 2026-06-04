<div align="center">

# inknote-wechat

**Notebook-style doodle visuals for WeChat articles**

面向微信公众号文章的手帐涂鸦风配图技能

![Skill](https://img.shields.io/badge/skill-inknote--wechat-111111)
![Version](https://img.shields.io/badge/version-v0.1.0-blue)
![Default](https://img.shields.io/badge/default-direct%20image-2ea44f)
![Cover](https://img.shields.io/badge/cover-2.35%3A1-f45c50)
![Section](https://img.shields.io/badge/section-16%3A9-1f6feb)
![Prompt](https://img.shields.io/badge/prompt-output%20supported-6f42c1)

[中文](#中文) | [English](#english) | [Style Guide](references/style-guide.md)

</div>

---

<a id="中文"></a>

## 中文

面向微信公众号文章的手帐涂鸦风配图技能。

`inknote-wechat` 可以把中文文章选题、文章草稿或完整公众号文章，转成一组可直接使用的封面图和内文插图。它特别适合 AI 产品、Vibe Coding、设计工具、创作者工具、效率工具和个人知识工作类内容。

![Codex mobile article cover example](assets/examples/codex-mobile-cover.png)

## 示例：OpenAI Codex 移动端文章

下面这组图来自一篇关于 Codex 登陆 ChatGPT 移动应用的文章示例。目标不是做复杂信息图，而是让公众号读者在手机上快速抓住每一节的意思。

| 封面图 | 内文图 |
| --- | --- |
| ![Cover example](assets/examples/codex-mobile-cover.png) | ![Work anywhere example](assets/examples/codex-mobile-work-anywhere.png) |
| 随时随地使用 Codex | 随时接住进展 |
| ![Decision example](assets/examples/codex-mobile-decision.png) | ![Remote SSH example](assets/examples/codex-mobile-remote-ssh.png) |
| 关键时刻介入 | 远程环境继续跑 |

## 一句话用法

```text
用 $inknote-wechat 给这篇文章出一套公众号配图：1 张封面 + 3 张内文图。
```

默认会先生成 1 张封面图确认风格；你确认后，再继续生成内文图。如果想一次性生成整套，可以直接说明“全部一次出图”。

## 适合做什么

- 生成公众号封面图
- 生成文章内小插图
- 为长文章设计一组统一风格配图
- 把一篇文章拆成 3-6 个视觉节点
- 默认优先直接生成成品图
- 图片生成工具不可用时，退回输出 Prompt

## 视觉风格

- 白色笔记本纸
- 浅蓝色横线
- 一条红色页边线
- 黑色马克笔手绘线条
- 不完美的方框、箭头、UI 卡片、便签、文件夹、鼠标指针和小人
- 少量红、黄、蓝或绿色点缀
- 适合手机阅读，不做复杂信息图

## 更多使用示例

```text
用 $inknote-wechat 给这篇文章直接出一张公众号封面图。
```

```text
Use $inknote-wechat to generate a WeChat cover image for this article.
```

## 推荐输出

普通公众号文章：

- 先出 1 张封面图确认风格
- 3 张内文插图
- 每张图附一条简短使用建议

早期选题阶段：

- 输出视觉分镜
- 需要时再输出 Prompt

## 目录结构

```text
inknote-wechat/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── assets/
│   ├── style-reference.jpg
│   └── examples/
│       ├── codex-mobile-cover.png
│       ├── codex-mobile-work-anywhere.png
│       ├── codex-mobile-decision.png
│       └── codex-mobile-remote-ssh.png
└── references/
    └── style-guide.md
```

## 说明

这个技能不是单纯写 Prompt，而是服务于公众号生产流程：目标是直接拿到一组风格统一、能放进文章里的配图。

`assets/examples/` 中的示例图是当前风格基准：后续生成应尽量对齐它们的纸张质感、粗黑手写标题、手绘 UI 卡片和少量红色点缀。

它不规定图片保存位置。实际保存目录应由使用它的项目或用户自己决定。

## English

Notebook-style doodle illustrations for WeChat official account articles.

`inknote-wechat` turns Chinese article ideas, drafts, or finished WeChat articles into usable cover images and in-article illustrations. It is tuned for AI product, Vibe Coding, design tools, creator workflows, productivity, and personal knowledge-work topics.

![Codex mobile article cover example](assets/examples/codex-mobile-cover.png)

## Example: OpenAI Codex Mobile Article

This sample visual set is based on an article about Codex becoming available in the ChatGPT mobile app.

| Cover | In-article visuals |
| --- | --- |
| ![Cover example](assets/examples/codex-mobile-cover.png) | ![Work anywhere example](assets/examples/codex-mobile-work-anywhere.png) |
| Use Codex Anywhere | Catch progress on mobile |
| ![Decision example](assets/examples/codex-mobile-decision.png) | ![Remote SSH example](assets/examples/codex-mobile-remote-ssh.png) |
| Step in at key moments | Remote environments keep running |

## What It Does

- Creates WeChat article cover images
- Creates section illustrations for long articles
- Designs a consistent visual set for one article
- Splits an article into 3-6 visual beats
- Generates finished images by default
- Falls back to prompt-only output when direct image generation is unavailable

## Visual Style

- White notebook paper
- Pale blue ruled lines
- One red margin line
- Black marker doodles
- Imperfect boxes, arrows, UI cards, sticky notes, folders, cursors, and small people
- One or two small color accents
- Mobile-readable composition for WeChat articles

## Example Prompts

```text
Use $inknote-wechat to generate a WeChat cover image for this article.
```

```text
Use $inknote-wechat to create a full visual package: 1 cover image + 3 in-article illustrations.
```

By default, the skill generates the cover first for style confirmation, then continues with the in-article visuals after approval. Ask for all images in one pass if you want the full set immediately.

## Recommended Output

For a normal WeChat article:

- 1 cover image first for style confirmation
- 3 in-article illustrations
- Short usage note for each image

For early ideation:

- Visual shot list
- Prompt-only output when requested

## Notes

This skill is designed for article production workflows where the goal is not only to write prompts, but to produce usable WeChat visuals with a consistent editorial illustration style.

The images in `assets/examples/` are the current style baseline for paper texture, rough hand-lettered titles, hand-drawn UI cards, and restrained red accents.

It does not prescribe a fixed output directory. The save location should be decided by the host project or the user.
