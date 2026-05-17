# Consistent Character Storyboard Workflow

A BananaHub workflow template for role-consistent storyboard exploration. It helps the agent lock one master character image, branch into contact-sheet or storyboard exploration, and iterate with single-variable edits instead of rewriting everything from scratch each round.

## Install

```bash
bananahub add bananahub-ai/templates/consistent-character-storyboard
```

## Verified Models

- `gemini-3-pro-image-preview` — verified with `samples/sample-3-pro-01.png` using the bundled Miso contact-sheet exploration sample
- `gpt-image-2` — verified with `samples/sample-gpt-image-2-01.png` for a text-free 3x3 original character contact sheet

## Supported Models

- `gpt-image-2` — supported through the `gpt-image` prompt variant for text-light contact sheets and storyboard concepts
- `gemini-3.1-flash-image-preview` — good default for fast exploration
- `gemini-3-pro-image-preview` — better fit when continuity and panel quality matter more than speed

## Sample Outputs

| File | Model | Prompt / Variant |
|---|---|---|
| `samples/sample-3-pro-01.png` | `gemini-3-pro-image-preview` | `3x3 contact sheet` exploration of the bundled Miso Siamese cat IP master reference |
| `samples/sample-gpt-image-2-01.png` | `gpt-image-2` | Text-free 3x3 contact sheet for one original explorer character |

## License

CC BY 4.0 unless this directory states otherwise.
