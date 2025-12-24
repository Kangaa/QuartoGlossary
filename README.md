# Glossary Extension For Quarto

Collect inline glossary terms and link them to a generated glossary section. Definitions live in project metadata, and a placeholder block is replaced at render time.

## Installing

```bash
quarto add Kangaa/glossary
```

This installs the extension under `_extensions`. If you're using version control, check in this directory.

## Using

1) Add glossary definitions to `glossary.qmd` front matter:

```yaml
---
title: "Glossary"
glossary-include: auto # auto | all | used
glossary-sort: yaml    # yaml | alpha
glossary:
  - term: Quarto
    definition: "An open-source scientific and technical publishing system."
  - term: Filter
    definition: "A script that transforms a document during rendering."
    aliases: ["Filters"]
---
```

- By default the filter looks for `glossary.qmd` at the project root.
- If you use a different file, set `glossary-page` in `_quarto.yml` to point at it.
- If `glossary-page` ends in `.qmd`, it is rewritten to `.html` for HTML output.

2) Mark terms inline (hover to see the definition tooltip):

```markdown
[Quarto]{.glossary}
[Quarto project]{.glossary term="Quarto"}
```

3) Add a glossary placeholder where entries should be inserted:

```markdown
# Glossary

::: {#glossary}
:::
```

## Example

Example book files: `index.qmd`, `chapter-01.qmd`, `chapter-02.qmd`, `glossary.qmd`.
