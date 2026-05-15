---
id: github-repo-visual-kit
type: workflow
title: GitHub 仓库运营视觉套件
title_en: GitHub Repository Visual Kit
description: 读取真实 GitHub 仓库后，为 README 生成首屏运营图、用户理解信息图或部署指南图。
author: bananahub
license: CC-BY-4.0
version: 1.0.0
profile: diagram
tags: [GitHub, README, 仓库配图, 信息图, 部署指南, repo, infographic, deployment, hero]
models:
  - name: gpt-image-2
    tested: false
    quality: best
  - name: gemini-3-pro-image-preview
    tested: false
    quality: good
  - name: gemini-3.1-flash-image-preview
    tested: false
    quality: good
providers:
  - id: openai
    family: gpt-image
    models:
      - id: gpt-image-2
        quality: best
        prompt_variant: gpt-image
      - id: gpt-image-1
        quality: ok
        prompt_variant: gpt-image
  - id: google-ai-studio
    family: gemini-image
    models:
      - id: gemini-3-pro-image-preview
        aliases: [nano-banana-pro]
        quality: good
        prompt_variant: gemini
      - id: gemini-3.1-flash-image-preview
        aliases: [nano-banana-2]
        quality: good
        prompt_variant: gemini
capabilities:
  generation: true
  edit: false
  mask_edit: false
prompt_variants:
  default: base
  gemini: prompt-gemini
  gpt-image: prompt-gpt-image
aspect: "16:9"
difficulty: intermediate
category: developer
samples: []
created: 2026-05-07
updated: 2026-05-15
---

## Goal

Create GitHub-ready visual assets from verified repository context: a README hero image for user attraction, a target-user infographic for fast understanding, or a deployment guide image for first successful use. Marketing clarity matters, but factual accuracy wins.

## When To Use

- A repository README needs a stronger first impression or launch-ready visual
- Users need to understand what the project does, who it serves, and how it works
- A project needs a deployment/setup visual based on real files and commands
- The agent can inspect a local repo, README excerpts, docs, package files, CI, Dockerfile, or deploy config

## Inputs

| Input | Required | Description |
|-------|----------|-------------|
| `repo_context` | required | Local repo path, GitHub URL, README, directory tree, package/deploy files, or agent-generated repo summary |
| `asset_type` | recommended | `readme-hero`, `user-infographic`, `deployment-guide`, `social-preview`, or `all` |
| `target_audience` | recommended | End users, developers, maintainers, operators, buyers, students, or contributors |
| `deployment_target` | optional | Local, Docker, Vercel, Netlify, Cloudflare, GitHub Pages, Kubernetes, package registry, or auto-detect |
| `style_preset` | optional | product-doc, developer-console, minimal-mono, sketchnote, brand-gradient, isometric-lite, dark-mode-neon, github-native |
| `brand_constraints` | optional | Brand colors, logo policy, forbidden claims, must-include labels, or light/dark mode requirement |

## Steps

1. Audit the repo before prompting. Read README, docs, package/build files, CI, Dockerfile, examples, license, and deploy config when available.
2. Build a verified brief: project type, one-line value proposition, target audience, 3–5 capabilities, proof points, and deployment facts. Mark unknowns instead of guessing.
3. Choose one asset path. Use `readme-hero` for attraction, `user-infographic` for comprehension, `deployment-guide` for setup, and `social-preview` for GitHub sharing.
4. Lock the text set before image generation. Keep titles short, labels to 3–7 items, and secrets or real credentials out of the visual.
5. Choose a layout and style preset. Prefer product-doc by default; use developer-console for CLI/devtools, minimal-mono for libraries, sketchnote for tutorials, and brand-gradient for launches.
6. Generate with the provider-specific prompt block. Prefer `gpt-image-2` for first-pass GitHub visuals because exact text constraints, label control, and README legibility matter most.
7. Review facts, text fidelity, reading order, contrast, and README fit. If the image invents modules, claims, commands, or numbers, regenerate from a smaller locked text set.
8. Package the result with filename, alt text, README insertion snippet, and optional note for light/dark or social-preview variants.

## Prompt Blocks

### Repo Audit Prompt

```text
Read {{repo_context|the provided repository context}} and produce a verified GitHub visual brief. Return: project type, target audience, one-line value proposition, 3 to 5 real capabilities, user journey or architecture summary, deployment facts, exact labels safe to show, claims to avoid, and unknowns. Use only evidence from README, docs, package/build files, CI, Dockerfile, examples, or user input.
```

### Asset Brief Prompt

```text
Plan one {{asset_type|readme-hero}} for {{project_name|this GitHub project}}. Audience: {{target_audience|developers evaluating the repo}}. Use only this verified brief: {{verified_brief|repo facts and safe labels}}. Return one short title, one subtitle or main message, 3 to 7 exact labels, one layout, one style preset, recommended aspect ratio, alt text, and a README insertion snippet. Do not include unsupported numbers, fake badges, fake screenshots, or unverified deployment claims.
```

### Generation Prompt: gemini

```text
Create a GitHub README visual for {{project_name|this project}}. Asset type: {{asset_type|readme-hero}}. Title: "{{title|Build Faster With This Repository}}". Main message: {{main_message|a concise verified value proposition for the target audience}}. Include only these exact short labels: {{locked_labels|"Install", "Configure", "Run", "Deploy"}}. Layout: {{layout|wide README hero with one clear headline area, three feature cards, and a simple product-flow illustration}}. Style: {{style_preset|product-doc style, warm off-white background, dark readable text, restrained banana-gold and teal accents, simple line icons, generous spacing}}. Audience: {{target_audience|developers evaluating the repository}}. Keep text large, high-contrast, and readable in under ten seconds. Do not invent modules, commands, statistics, GitHub stars, UI screenshots, badges, logos, or deployment platforms.
```

### Generation Prompt: gpt-image

```text
Design one GitHub README visual for {{project_name|this project}}. Asset type: {{asset_type|readme-hero}}. Title text: "{{title|Build Faster With This Repository}}". Main message text: "{{main_message|a concise verified value proposition for the target audience}}". The only additional text allowed in the image is: {{locked_labels|"Install", "Configure", "Run", "Deploy"}}. Layout: {{layout|wide README hero with one headline area, exactly three feature cards, and one simple product-flow illustration}}. Visual style: {{style_preset|product-doc style, warm off-white background, dark readable text, restrained banana-gold and teal accents, simple line icons, generous spacing}}. Do not add paragraphs, extra labels, fake badges, fake GitHub stars, fake charts, fake screenshots, logos, watermarks, unverified commands, secrets, or decorative clutter. Keep all text large and legible.
```

### Deployment Guide Prompt

```text
Create a deployment guide visual for {{project_name|this project}} targeting {{deployment_target|the detected deployment target}}. Show only verified steps from the repo: {{deployment_steps|Prerequisites; Configure env/secrets; Install dependencies; Build; Deploy; Verify}}. Include only these exact labels: {{locked_labels|"Prerequisites", "Env/Secrets", "Build", "Deploy", "Verify"}}. Use {{style_preset|developer-console style with clean cards, arrows, high contrast, and no secret values}}. Do not invent commands, expose credentials, or show real API keys.
```

### Repair Prompt

```text
Keep the same asset type, title, main message, layout, and exact labels. Repair only factual accuracy, text fidelity, contrast, connector direction, spacing, and README readability. Remove invented modules, commands, statistics, screenshots, badges, extra labels, and decorative clutter.
```


## Provider Prompt Rules

### Provider Variant: gemini

Use the repo audit, asset brief, generation, deployment, and repair blocks above as written for Gemini/Nano Banana. Keep source-derived facts, exact labels, layout, and style preset explicit. Prefer descriptive composition language, but do not add unverified repository claims.

### Provider Variant: gpt-image

Use the same workflow steps, but rewrite generation prompts with strict text limits, exact allowed labels, and negative constraints against extra copy, fake metrics, fake screenshots, unsupported commands, secrets, clutter, cropped edges, and duplicated UI fragments. Do not use a Gemini-tuned block directly when exact text fidelity is the main risk.

## Success Checks

- Every visible claim, module, command, platform, and label comes from repo evidence or user-approved text
- The asset has one clear purpose: attraction, comprehension, deployment, or social preview
- A README hero communicates value in under ten seconds and does not duplicate the full README
- An infographic uses one layout and 3–7 locked labels with an obvious reading order
- A deployment guide separates prerequisites, configuration/secrets, deploy, and verification without exposing credentials
- The result includes alt text and a README insertion snippet, not just an image prompt
