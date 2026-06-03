---
name: inknote-wechat
description: Use when the user asks for 微信公众号配图, article cover images, section illustrations, social post visuals, or image prompts based on Chinese article content, especially for AI product, Vibe Coding, design, creator tools, productivity, or personal knowledge-work topics.
---

# WeChat Doodle Illustrations

## Overview

Generate finished WeChat article illustrations by default, not just prompts. Keep the style like a scanned notebook page: blue horizontal ruled paper, black marker doodles, imperfect boxes, handwritten labels, tiny marginal notes, simple icons, and one or two small color accents.

Load `references/style-guide.md` before writing final prompts or generating images.

## Workflow

1. Read the article or brief and extract the core reader promise in one sentence.
2. Split the article into 3-6 visual beats: cover, key concept, process, contrast, example, ending note.
3. Choose the minimum useful image set:
   - For a cover: create one strong 16:9 or 3:2 composition.
   - For a full article: create 1 cover plus 3-5 in-article illustrations.
   - For ideation: return a shot list only when the user asks for ideas or prompts.
4. Use concrete metaphors instead of abstract AI imagery. Prefer tools, notes, windows, arrows, checklists, robots, cursor pointers, folders, small people, and messy annotations.
5. Make each image readable on mobile. Use 1 focal idea, 3-7 words of visible text at most, and avoid dense paragraph text inside the image.
6. Generate finished images directly when an image generation tool is available.
7. Include a negative prompt internally that blocks polished vector art, 3D render, glossy gradients, corporate stock illustration, photorealism, and overly cute mascot style.

## Output Format

Default output is finished images plus a short usage note. Do not expose long prompts unless the user asks for them.

For direct image generation:

- Generate the image with the image generation tool.
- Show the finished image in the response when possible.
- Add a short note with `用途`, `建议位置`, and `尺寸`.
- Keep the written explanation concise.

For prompt-only requests, provide:

- `用途`: cover / section / transition / ending
- `画面`: one-sentence composition
- `文字`: exact visible words, if any
- `Prompt`: final English image prompt
- `Negative prompt`: style exclusions
- `尺寸`: recommended ratio

Use `assets/style-reference.jpg` as the local style reference when the image generation tool supports reference images.

## Direct Image Generation Rules

- If the user says `直接出图`, `生成图片`, `成品图`, `配图`, `封面图`, or gives an article and asks for visuals, generate finished images directly.
- If the user only needs a full article visual package, start with 1 cover image first unless they explicitly ask for multiple images.
- If generating multiple images, keep the set visually consistent: same paper texture, same black marker line weight, same accent color logic.
- If text accuracy inside the image matters, keep visible text very short and repeat the exact Chinese words in the prompt.
- Do not prescribe a default output folder. Save files only when the user or host project provides an output location; otherwise return the generated images in the response.
- If the tool cannot generate images, fall back to prompt-only output and clearly say so.

## WeChat Defaults

- Cover ratio: `2.35:1` or `16:9`; keep the main subject centered because WeChat crops previews.
- In-article ratio: `4:3`, `3:2`, or square; keep line art thick enough for phone screens.
- Text language: default to Chinese unless the article title or user brief is English.
- Tone: clever, handmade, slightly messy, designer-notebook energy; avoid childish classroom worksheet vibes.

## Prompt Skeleton

```text
Hand-drawn notebook doodle illustration on white ruled paper with pale blue horizontal lines and one red margin line, black marker pen linework, slightly imperfect rectangles and arrows, tiny handwritten annotations, simple UI icons and small stick-figure characters, [subject/composition], [visible text], sparse layout, mobile-readable, editorial illustration for a WeChat article, one small color accent only, scanned paper texture, natural shadows, high contrast black ink.
```
