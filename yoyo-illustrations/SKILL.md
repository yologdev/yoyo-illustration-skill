---
name: yoyo-illustrations
description: Generate clean, quietly weird, hand-drawn 16:9 illustrations for article bodies, with yoyo (a soft purple octopus) as the recurring main character. Use when the user asks to illustrate an article, blog post, Notion doc, workflow doc, methodology, process, structure, state, metaphor or argument — triggers include "illustrate / 配图 / 正文配图 / 文章插图 / shot list / hand-drawn / 手绘 / yoyo 配图 / octopus illustration". Works in any language: annotations are written in the same language as the source article (English, 中文, etc.). yoyo is the single purple subject on an otherwise pure-white, black line-art canvas with sparse red/orange/blue handwritten notes.
---

# yoyo Hand-drawn Article Illustrations

## What this is

Design and generate **16:9 horizontal body illustrations** for an article. The goal is **not** commercial illustration, PPT infographics, or cute cartoon posters. It is to turn the article's key judgment, process, structure, state, or metaphor into one **clean, quietly weird, creative, readable-but-not-instructional hand-drawn explainer**.

The fixed visual IP is **yoyo**: a soft lavender-purple octopus with a bold black outline, two simple dot eyes, a small calm smile, and eight tentacles. yoyo is gentle, earnest, a little shy — a small self-evolving helper who *actually does the core work* in the picture with its tentacles. yoyo must perform the central action of the scene, never just stand beside it as decoration.

**Language is adaptive.** Detect the source article's language and write every handwritten annotation in that same language — English article → English labels, 中文文章 → 中文标注, and so on. yoyo is the same character in every language.

## Read these references as needed

Pull in only what the task needs; do not load everything at once.

- `references/style-dna.md` — style DNA, color rules, the one-purple-subject rule, hard "never" list.
- `references/yoyo-ip.md` — yoyo's look, personality, tentacle-action library, and don'ts.
- `references/composition-patterns.md` — structure types and the "reinvent the metaphor each time" method.
- `references/prompt-template.md` — the single-image prompt template (runtime-agnostic).
- `references/qa-checklist.md` — post-generation checks and iteration rules.
- `assets/yoyo-reference.png` — yoyo's canonical look. Use only to keep yoyo on-model (proportions, color, face). Do **not** copy its pose or framing into article illustrations.

## Workflow

### 1. Digest the article

Read the article, link, Notion page, Markdown file, or screenshot the user gives you. Extract:

- the core argument
- which paragraphs carry a cognitive turn
- which ideas are worth explaining with a picture
- which parts are better left as text with no image

Do not illustrate evenly. Prefer **cognitive anchors**: a core judgment, two breakpoints, an input→output loop, a fork, a before/after, one-input-many-outputs, a hand-off path, a common pit, a change of state.

### 2. Propose the shot list first

If the user only asks you to *analyze* where illustrations should go, return a **shot list** before generating anything. For each shot write:

- which paragraph it follows
- the topic
- the core idea
- the structure type
- **what yoyo is doing in it**
- suggested elements
- suggested handwritten labels (in the article's language)

Default **4–8 shots**. Short article: 1–3. Long article: rarely more than 9. Enough to help, never a picture book.

### 3. Generate one image at a time

If the user clearly asks you to *generate / output / make / produce* images, don't stop to re-confirm. Generate each image **separately** — never tile several concepts into one frame.

Use **whatever image-generation tool your runtime provides** (e.g. a built-in `image_gen`). **If your runtime has no image tool, output the finished prompt** for each shot so the user can paste it into an image model. Build each prompt from `references/prompt-template.md`. Every prompt must include:

- 16:9 horizontal body illustration
- pure white background
- black hand-drawn line art for the scene and props
- **yoyo as the single soft-purple subject performing the core action**
- a few red/orange/blue handwritten labels **in the article's language**
- lots of empty white space
- bans: PPT / commercial vector / childish-cute / dense architecture / top-left type-title

Invent a fresh visual metaphor from *this* article every time. Do not fall back to a generic conveyor-belt / funnel / box-sorting cliché unless the article genuinely calls for it.

### 4. Check and iterate

After generating, run `references/qa-checklist.md`. Regenerate or locally edit if you see:

- yoyo is just decoration
- the frame is too busy
- it looks like a flowchart / PPT
- annotations are too long, or wrong language, or full of typos
- a "common pit / flowchart / system architecture" title in the top-left corner
- the style drifted cute / childish / stiff
- the background is not clean white
- purple or pink leaked onto things that are not yoyo

### 5. Save and deliver

If the user is working inside a workspace, copy the finals to:

```text
assets/<article-slug>-illustrations/
```

Name them in order:

```text
01-topic-name.png
02-topic-name.png
```

Keep the original generated files. Do not overwrite existing assets unless the user explicitly asks for a replacement.

## Output discipline

The pre-generation strategy should be short and sharp. The post-generation delivery should state:

- how many images were generated (or how many prompts were produced, if no image tool)
- what each one is for
- the save path
- which images are the safe ones and which are optional

Don't lecture about style theory. Let the pictures talk.
