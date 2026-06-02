# inknote-wechat

Notebook-style doodle illustrations for WeChat official account articles.

This Codex skill turns Chinese article ideas or finished WeChat drafts into finished cover images and in-article illustrations. It is tuned for AI product, Vibe Coding, design tools, creator workflows, productivity, and personal knowledge-work topics.

## What It Does

- Creates WeChat article cover images
- Creates section illustrations for long articles
- Uses a hand-drawn notebook style
- Generates finished images by default when an image tool is available
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
用 $inknote-wechat 给这篇文章直接出一张公众号封面图。
```

```text
用 $inknote-wechat 给这篇文章出一套公众号配图：1 张封面 + 3 张内文图。
```

## Recommended Output

For a normal WeChat article:

- 1 cover image
- 3 in-article illustrations
- Short usage note for each image

For early ideation:

- Visual shot list
- Prompt-only output if requested

## Structure

```text
inknote-wechat/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── style-reference.jpg
└── references/
    └── style-guide.md
```

## Notes

This skill is designed for article production workflows where the goal is not only to write prompts, but to produce usable WeChat visuals with a consistent editorial illustration style.
