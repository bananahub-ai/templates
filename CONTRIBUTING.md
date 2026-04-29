# Contributing

BananaHub official templates are curated. Keep contributions practical, reusable, and clear enough for agents to activate without reading a long tutorial.

## Template Rules

- Use the existing `template.md` schema.
- Declare provider/model support explicitly; do not imply a capability is cross-model if it is provider-specific.
- Keep prompt templates compact and variable-driven.
- Use workflow templates for multi-step tasks, approvals, or iterative image work.
- Add samples only when they help users judge quality. Avoid dumping large galleries.

## Quality Bar

A template should answer:

1. Who is this for?
2. What exact job does it make easier?
3. What inputs are required?
4. Which provider/model paths are supported?
5. How does a user know the output is good enough?

## Validation

From the sibling `bananahub-skill` repo, run:

```bash
python3 scripts/validate_templates.py ../templates
```
