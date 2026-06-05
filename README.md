# yoyo Illustrations

An AI-agent **skill** that generates clean, quietly weird, hand-drawn **16:9 body illustrations** for an article — starring **yoyo**, a soft purple octopus, as the recurring main character.

It turns an article's key judgment, process, structure, state, or metaphor into a single hand-drawn explainer: pure white background, black line art, **yoyo as the one purple subject doing the core action with its tentacles**, and a few handwritten annotations.

> This is an adaptation of [Ian's `ian-xiaohei-illustrations`](https://github.com/helloianneo/ian-xiaohei-illustrations) skill. The methodology, style DNA, and workflow are Ian's; this fork swaps the recurring character from **小黑** to **yoyo** and makes the skill multilingual and runtime-portable. See [`NOTICE.md`](NOTICE.md).

## What changed from the original

- **Main character:** 小黑 (a solid-black creature) → **yoyo** (a soft lavender-purple octopus). yoyo is the single filled-color subject; everything else stays black line art on white.
- **Multilingual:** annotations are written in the **same language as the source article** — English, 中文, and others. yoyo is the same character in every language.
- **Runtime-portable:** the instructions don't hard-depend on any one runtime's image tool. If your agent has a built-in image generator, it uses it; if not, it emits the finished prompt for you to paste into an image model.

## Layout

```text
yoyo-illustrations/            ← the installable skill folder
  SKILL.md                     ← entry point (name + description frontmatter)
  agents/openai.yaml           ← Codex / OpenAI agent manifest
  references/
    yoyo-ip.md                 ← yoyo's look, personality, tentacle-action library
    style-dna.md               ← color rules, the one-purple-subject rule, the "never" list
    composition-patterns.md    ← structure types + reinvent-the-metaphor method
    prompt-template.md         ← the runtime-agnostic image prompt
    qa-checklist.md            ← post-generation checks
  assets/
    yoyo-reference.png         ← yoyo's canonical look (on-model reference only)
```

## Install

The skill is just `SKILL.md` + the `references/` markdown — plain prose, so it runs anywhere an agent can load instructions. Pick your runtime:

### Claude Code

Copy the inner skill folder into your skills directory:

```bash
cp -r yoyo-illustrations ~/.claude/skills/yoyo-illustrations
```

Claude Code reads the `name` and `description` from `SKILL.md`'s frontmatter and invokes it when a request matches.
**Image step:** Claude Code has no built-in image generator, so the skill will output the finished prompt for each shot — paste it into your image model of choice (or wire up an image MCP tool).

### Codex / OpenAI agents

The `agents/openai.yaml` manifest is already included. Register the `yoyo-illustrations` folder as a skill; it can be invoked explicitly with `$yoyo-illustrations` or implicitly (`allow_implicit_invocation: true`).
**Image step:** if your runtime has a built-in `image_gen`, the skill uses it directly to render each illustration.

### yoyo / other agent tools

Any agent that can load a system prompt or instruction file can use this. Point your agent at `yoyo-illustrations/SKILL.md` and let it pull in the `references/` files as needed. The skill detects whether an image tool exists and either generates images or emits prompts accordingly.

## Use

- *"Analyze where this article needs illustrations"* → returns a **shot list** (paragraph, topic, structure type, what yoyo is doing, suggested labels).
- *"Generate the illustrations"* → produces one image per shot (or one prompt per shot if there's no image tool), with annotations in the article's language.

Trigger words include: `illustrate / 配图 / 正文配图 / 文章插图 / shot list / hand-drawn / 手绘 / yoyo 配图 / octopus illustration`.

## License

MIT — see [`LICENSE`](LICENSE) and [`NOTICE.md`](NOTICE.md).
