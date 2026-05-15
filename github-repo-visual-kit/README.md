# GitHub Repository Visual Kit

A BananaHub workflow template for turning real repository context into GitHub-ready visuals: README hero images, target-user infographics, deployment guide visuals, and social-preview concepts. It is intentionally kept in the official template library rather than the BananaHub Skill starter pack because it carries richer repo-audit and packaging guidance.

## Install

```bash
bananahub add bananahub-ai/templates/github-repo-visual-kit
```

Inside BananaHub Skill, prefer discovery:

```bash
/bananahub discover GitHub README 配图 部署指南
/bananahub use github-repo-visual-kit
```

## Best Practices

- Read the repo first: README, docs, package files, CI, Dockerfile, examples, license, and deployment config when available.
- Build a verified brief before prompting. Treat unknowns as unknown instead of turning them into visual claims.
- Choose one asset target per pass: README hero for attraction, infographic for comprehension, deployment guide for first successful use, or social preview for sharing.
- Lock all visible text before image generation. Keep labels short and limit infographic/deployment diagrams to 3–7 items.
- Do not show fake GitHub stars, fake badges, fake dashboards, unsupported metrics, invented commands, or real secrets.
- Package the result with alt text and a Markdown insertion snippet so the image is immediately README-ready.
- Consider light/dark variants or a 1280×640 social preview when the visual is meant for broad GitHub sharing.

## Style Presets

- `product-doc` — default clean documentation visual with restrained color and strong readability.
- `developer-console` — dark terminal/card composition for CLIs, SDKs, and developer tools.
- `minimal-mono` — monochrome plus one accent for libraries and frameworks.
- `sketchnote` — hand-drawn explainer for tutorials and education.
- `brand-gradient` — launch-oriented hero with a bolder editorial feel.
- `isometric-lite` — lightweight cloud or architecture metaphor without heavy 3D clutter.
- `dark-mode-neon` — high-contrast AI/security/devtool look; use sparingly.
- `github-native` — GitHub-adjacent documentation language without faking GitHub UI state.

## Verified Models

No sample image is checked in yet. The workflow is prompt- and process-validated, with model verification pending.

## Supported Models

- `gpt-image-2` — recommended first-pass model for strict text limits, label control, and README legibility.
- `gemini-3-pro-image-preview` — good fit for richer composition and polished README visuals.
- `gemini-3.1-flash-image-preview` — good faster option for early visual directions.
- `gpt-image-1` — compatible fallback through the `gpt-image` prompt variant.

## Sample Outputs

No sample outputs are included yet. Add samples only after validating them against a real repository brief and keeping any visible claims factual.

## License

CC BY 4.0 unless this directory states otherwise.
