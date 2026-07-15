---
name: inknote-wechat
description: Use when the user asks for 微信公众号配图, article cover images, section illustrations, social post visuals, or image prompts based on Chinese article content, especially for AI product, Vibe Coding, design, creator tools, productivity, or personal knowledge-work topics.
---

# WeChat Doodle Illustrations

## Overview

Generate finished WeChat article illustrations by default, not just prompts. Keep the style like a scanned notebook page: textured white ruled paper, pale blue horizontal lines, one red margin line, thick black marker doodles, rough hand-lettered Chinese text, imperfect boxes, tiny marginal notes, simple icons, and one or two small color accents.

The target should feel like a real marker sketch scanned from a notebook, not a clean SVG, poster, UI mockup, or digital illustration. All visible text must look hand-drawn: uneven brush pressure, irregular character size, slightly crooked baseline, and no clean digital fonts.

Load `references/style-guide.md` before writing final prompts or generating images.

## Style Baseline

Use `assets/examples/` as the current visual benchmark. New outputs should match these examples more than a clean diagram:

- `assets/examples/codex-mobile-cover.png` for cover density, paper texture, and hand-lettered headline scale. Treat it as a style benchmark, not as the current cover-delivery layout.
- `assets/examples/codex-mobile-work-anywhere.png`, `assets/examples/codex-mobile-decision.png`, and `assets/examples/codex-mobile-remote-ssh.png` for in-article `16:9` composition, rough UI cards, thick marker linework, and small red accent usage.

Treat `assets/style-reference.jpg` as a general style reference, and `assets/examples/` as the practical production standard for this skill.

## Workflow

1. Read the article or brief and extract the core reader promise in one sentence.
2. Split the article into 3-6 visual beats: cover, key concept, process, contrast, example, ending note.
3. Choose the minimum useful image set:
   - For a cover: design one `2.35:1` landscape version and one `1:1` square version, then combine them into one upload master image.
   - For a full article: create 1 cover plus 3-5 in-article illustrations.
   - For ideation: return a shot list only when the user asks for ideas or prompts.
4. Use concrete metaphors instead of abstract AI imagery. Prefer rough tool panels, notes, windows, arrows, checklists, robots, cursor pointers, folders, small people, and messy annotations.
5. Make each image readable on mobile. Use 1 focal idea, 3-7 words of visible text at most, and avoid dense paragraph text inside the image.
6. When the image contains Chinese text, explicitly request `bold hand-lettered Chinese marker characters, not typed font, not calligraphy, not printed typography`.
7. For a full article visual package, generate the cover first and wait for style confirmation unless the user explicitly asks to generate the whole set in one pass.
8. Generate finished images directly when an image generation tool is available.
9. Include a negative prompt internally that blocks clean digital fonts, polished vector art, 3D render, glossy gradients, corporate stock illustration, photorealism, and overly cute mascot style.

## WeChat Cover Master

Create two independently composed cover variants, then deliver them as one image:

- Left panel: `2.35:1` landscape cover for the message list.
- Right panel: `1:1` square cover for forwarded cards and the official-account home page.
- Keep both panels the same height and join them flush side by side. The combined master ratio is `3.35:1`.
- Do not treat the square panel as a crop of the landscape panel. Recompose the headline and focal sketch for the square format.
- Keep the visual idea, paper texture, line weight, characters, and accent color consistent across both panels.
- Let the square panel use a shorter headline when the landscape wording is too long. Preserve the same meaning rather than forcing identical text.
- Keep all essential content inside its own panel. Do not let headlines, characters, arrows, or key objects cross the panel boundary.
- Deliver only the combined master image unless the user explicitly asks for separate files.

If generating the two ratios separately produces better composition or text accuracy, generate them separately first and assemble them into the single combined master before delivery.

## Prompt Quality Lock

Direct image generation must still be prompt-first. Before calling any image generation tool, write a complete final English prompt internally using the same level of detail as the prompt-only output. Do not replace it with a short summary.

The prompt must include:

- `Hand-drawn notebook doodle illustration on white ruled paper with pale blue horizontal lines and one red margin line`
- `black marker pen linework`
- `slightly imperfect rectangles and arrows`
- `bold hand-lettered Chinese headline`
- `sparse layout, mobile-readable`
- `one small color accent only`
- `scanned paper texture, natural shadows, high contrast black ink`

For Chinese text, prefer this wording:

```text
bold hand-lettered Chinese headline "[exact text]", rough black marker strokes, uneven pressure, irregular character size, slightly crooked baseline, not a typed font
```

Do not let direct generation simplify the style into clean UI art, SVG-like illustration, or system-font typography.

## Output Format

Default output is finished images plus a short usage note. Do not expose long prompts unless the user asks for them.

If the user asks for `提示词`, `Prompt`, `prompt-only`, `只要提示词`, or `不要出图`, return prompt-only output instead of generating images.

For direct image generation:

- First create the complete final prompt internally using `Prompt Quality Lock`.
- Generate the image with the image generation tool.
- Show the finished image in the response when possible.
- Add a short note with `用途`, `建议位置`, and `尺寸`. For a cover, report `3.35:1 combined master (left 2.35:1 + right 1:1)`.
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
- If the user asks for prompts instead of finished images, do not call the image generation tool.
- If the user asks for a full article visual package, start with 1 cover image first and ask for style confirmation before generating in-article illustrations, unless they explicitly ask for all images at once.
- For a cover, count the combined landscape-plus-square master as 1 finished image, not 2 deliverables.
- If generating multiple images, keep the set visually consistent: same paper texture, same black marker line weight, same accent color logic.
- If text accuracy inside the image matters, keep visible text very short and repeat the exact Chinese words in the prompt.
- If style accuracy matters, prioritize hand-lettering, rough scanned paper texture, and imperfect marker linework over perfect text layout.
- Do not prescribe a default output folder. Save files only when the user or host project provides an output location; otherwise return the generated images in the response.
- If the tool cannot generate images, fall back to prompt-only output and clearly say so.

## Preflight Checklist

Before generating or returning prompts, quickly verify:

- Cover output is one `3.35:1` combined master with a left `2.35:1` panel and a right `1:1` panel; in-article images use `16:9`.
- Both cover panels work as independent compositions, with no essential content crossing the join.
- Full article packages start with 1 cover for style confirmation unless the user asks for all images at once.
- The prompt aligns with `assets/examples/` for paper texture, rough black marker linework, hand-lettered Chinese titles, hand-drawn UI cards, and restrained red accents.
- Visible text is short, mobile-readable, and described as hand-lettered marker text rather than typed typography.
- The negative prompt blocks SVG-like art, clean digital fonts, polished vector illustration, 3D render, corporate stock illustration, and dense infographics.

## WeChat Defaults

- Cover master: `3.35:1`, made from an equal-height `2.35:1` landscape panel on the left and a separately composed `1:1` square panel on the right.
- Cover text: use a concise landscape headline; shorten it further for the square version when needed while preserving the same idea.
- In-article ratio: `16:9`; keep line art thick enough for phone screens.
- Text language: default to Chinese unless the article title or user brief is English.
- Tone: clever, handmade, slightly messy, designer-notebook energy; avoid childish classroom worksheet vibes.
- Typography: visible words should look written by hand with a fat black marker. Avoid system fonts, clean sans-serif, vector lettering, perfect alignment, or poster-style typography.

## Prompt Skeleton

```text
Hand-drawn notebook doodle illustration on textured white ruled paper with pale blue horizontal lines and one red margin line, rough black marker pen linework with uneven pressure, slightly imperfect rectangles and arrows, tiny handwritten annotations, simple tool icons and small doodle characters, [subject/composition], [visible text as bold hand-lettered Chinese marker characters, irregular baseline, not typed font], sparse layout, mobile-readable, editorial illustration for a WeChat article, one small color accent only, scanned paper texture, natural shadows, high contrast black ink.
```
