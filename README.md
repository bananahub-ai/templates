# BananaHub Official Templates

Official BananaHub prompt and workflow templates live here, outside the BananaHub Skill runtime. The skill stays lean; this repo carries richer prompts, workflows, examples, and sample assets that can evolve independently.

## Why This Repo Exists

- **Lean skill package**: starter templates remain in `bananahub-skill`; heavier official templates live here.
- **Faster content iteration**: prompts, samples, and workflows can update without shipping a new skill runtime.
- **Better onboarding**: official templates seed practical use cases for early users and give UGC authors good examples to copy.
- **Cross-provider clarity**: templates declare Gemini / Nano Banana and OpenAI GPT Image support separately.

## Template Library

| Template | Type | Best For |
|---|---|---|
| `app-web-logo-system` | workflow | App icons, favicons, wordmarks, platform-safe logo variants |
| `article-illustration-workflow` | workflow | Planning and generating article/blog/tutorial visuals |
| `asset-style-consistency-pack` | workflow | Restyling local assets into one coherent visual family |
| `consistent-character-storyboard` | workflow | Character identity, contact sheets, storyboard exploration |
| `cute-sticker` | prompt | Chibi sticker and emoji-style assets |
| `cyberpunk-city` | prompt | Cinematic neon city scenes |
| `github-repo-visual-kit` | workflow | Repo-aware README hero, user infographic, deployment guide, and social-preview visuals |
| `minimal-wallpaper` | prompt | Minimal mobile wallpapers |
| `readme-launch-visual` | workflow | README hero images, OG covers, launch visuals |

## Install

Install one template:

```bash
bananahub add bananahub-ai/templates/cute-sticker
```

Install all official templates:

```bash
bananahub add bananahub-ai/templates --all
```

Inside BananaHub Skill, prefer discovery:

```bash
/bananahub discover logo system
/bananahub discover character storyboard
```

## Authoring Standard

Each template should include:

- `template.md` with frontmatter, provider matrix, capabilities, and prompt/workflow body
- Gemini / Nano Banana and OpenAI GPT Image support when practical
- `samples/` only when the sample proves quality or workflow behavior
- A short `README.md` for richer workflows or templates with samples

Built-in starter templates should stay in `bananahub-skill/references/templates/`. Rich official templates and fast-changing samples belong here.
