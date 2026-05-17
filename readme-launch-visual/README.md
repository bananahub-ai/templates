# README Launch Visual Workflow

A BananaHub workflow template for converting README copy or product positioning into a launch-ready visual. It helps the agent lock one headline, one short support line, and one visual metaphor instead of letting the image drift into generic AI poster clutter.

## Install

```bash
bananahub add bananahub-ai/templates/readme-launch-visual
```

## Verified Models

- `gpt-image-2` — verified with `samples/sample-gpt-image-2-01.png` for a locked-copy README hero

## Supported Models

- `gpt-image-2` — supported through the `gpt-image` prompt variant for locked-copy README heroes and OG covers
- `gemini-3-pro-image-preview` — best fit when headline rendering and composition quality matter
- `gemini-3.1-flash-image-preview` — good option for faster concepting before refining the final hero

## Sample Outputs

| File | Model | Prompt / Variant |
|---|---|---|
| `samples/sample-gpt-image-2-01.png` | `gpt-image-2` | Wide README hero with locked headline `Build image workflows, not prompt piles` and support line `Templates, editing, and provider-aware routing` |

## License

CC BY 4.0 unless this directory states otherwise.
