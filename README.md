# Paper to Note

A Codex skill that reads an academic paper PDF and creates a structured Markdown research note in a concise finance-journal style.

## What it produces

Each note follows a fixed template covering the abstract, research questions, sample and data, key variables, method, main findings, contributions, a one-sentence takeaway, and constructive comments.

Notes are written in English. The abstract is copied from the paper, while factual claims must be supported by the PDF.

By default, the note is saved alongside the PDF with the same base filename and a `.md` extension.

## Usage

With the skill installed, provide a paper PDF and ask Codex:

```text
Use $paper-to-note to read this PDF and create a Markdown research note using the skill's template.
```

See [SKILL.md](SKILL.md) for the full template and writing rules.
