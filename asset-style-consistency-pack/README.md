# Local Asset Style Consistency Workflow

A BananaHub workflow template for building a consistent asset pack from local images. It is meant for agent runs where one approved anchor style should be propagated across additional images without changing locked composition, text, or subject identity.

## Install

```bash
bananahub add bananahub-ai/templates/asset-style-consistency-pack
```

## Verified Models

- `gpt-image-2` — verified with `samples/sample-gpt-image-2-01.png` as a workflow preview board for source assets, a style anchor, and a consistent output pack

## Supported Models

- `gpt-image-2` — supported through the `gpt-image` prompt variant when provider edit support is available

## Sample Outputs

| File | Model | Prompt / Variant |
|---|---|---|
| `samples/sample-gpt-image-2-01.png` | `gpt-image-2` | Workflow preview board showing `Source`, `Style anchor`, and `Consistent pack`; not a substitute for running the edit workflow with real input images |

## License

CC BY 4.0 unless this directory states otherwise.
