# Article Illustration Workflow

A BananaHub workflow template for turning article text into a compact illustration pack. It helps the agent read the article first, write a small outline, generate one visual at a time, and optionally insert Markdown image refs back into the source file.

## Install

```bash
bananahub add bananahub-ai/templates/article-illustration-workflow
```

## Verified Models

- `gpt-image-2` — verified with `samples/sample-gpt-image-2-01.png` for a strict-label three-stage article workflow diagram

## Supported Models

- `gpt-image-2` — supported through the `gpt-image` prompt variant when strict labels and text-light article visuals matter most
- `gemini-3-pro-image-preview` — best fit when label accuracy, layout clarity, and article fidelity matter most
- `gemini-3.1-flash-image-preview` — good faster option for outline-driven drafts and multi-image article packs

## Sample Outputs

| File | Model | Prompt / Variant |
|---|---|---|
| `samples/sample-gpt-image-2-01.png` | `gpt-image-2` | Three-stage article workflow diagram with locked labels `Extract claims`, `Plan slots`, and `Generate + review` |

## License

CC BY 4.0 unless this directory states otherwise.
