---
name: paper-to-note
description: Read one academic paper PDF and create or update a same-name Markdown research note using the template in this skill. Use when the user wants a concise finance-journal-style paper note covering the abstract, research question, sample and data, key variables, method, findings, contributions, takeaway, and constructive comments.
---

# Paper To Note

## Overview

Read one academic paper PDF and write a concise Markdown research note using the House Template below.
Use the template's headings, section order, and icon markers for both new and updated notes.

## Workflow

### 1. Locate the PDF and choose the output file

- Use the PDF specified by the user, or locate the target PDF in the working folder.
- Save the note as a same-name `.md` file alongside the PDF unless the user specifies a different output name or location.
- Use the House Template below as the structure for the note.

### 2. Read the paper with purpose

- Before drafting, read the full paper once from the first page through the final appendix page so you know the full structure of the paper and do not miss material details. References may be skipped unless needed.
- After the full read, re-read the abstract, introduction, data/sample section, empirical design or model section, and conclusion carefully.
- Use the literature review only when it helps clarify the paper's own stated contribution or positioning.
- Do not infer facts that are not explicitly supported by the paper.
- If a field is unclear or a draft note seems inaccurate, keep searching the PDF until the point is clear enough to write accurately.
- Check appendices, data descriptions, variable construction details, and method sections when needed.
- If the paper itself remains unclear after careful reading, write conservatively rather than guessing.

### 3. Write the Markdown note

- Write the note from the PDF using the House Template below.
- Follow the template's headings, section order, and icon markers.
- Fill only the standard metadata and sections required by the house template.
- Use concise bullets, compact wording, and a finance-journal tone.

### 4. Verify before finishing

- Confirm that only the target `.md` was edited.
- Check that YAML/front matter is valid.
- Check that the abstract excludes JEL codes.
- Check that `My thoughts` contains no wikilinks.
- Check that any formula in the note renders correctly in Obsidian and is not left as raw LaTeX text.
- Re-open the generated `.md` and verify that all icon markers render correctly as icons.
- If any mojibake or encoding corruption appears, such as broken emoji markers or garbled text like `馃`, `鈿`, or `锔`, repair the file and check again until the rendered text is clean.
- Check that the note follows the House Template and that its factual claims are supported by the PDF.

## House Template

Use this template for every note, including when updating an existing note.

```md
---
title: "Paper Title"
authors: "Author A, Author B, and Author C"
year: 2025
journal: "Journal Name"
---

PDF: [[Paper File.pdf]]

[[Topic 1]] [[Topic 2]]

### Abstract

A paragraph copied from the paper abstract.

### Research Questions

- 🎯 A research question phrased as closely as possible to the paper's own wording.

### Sample and Data

- 📌 Sample: period, scope, and setting.
- 📝 / 🎙️ / 🎥 Key data: the main data source used to construct the core variables.
- 📈 Frequency: the overall frequency of the key X data and the main Y or outcome data, stated explicitly when they differ (for example, `X` annual and `Y` monthly).

### Key Variables

- 🔑 Main dependent and independent variables.

### Method

- ⚙️ Concise description naming the exact baseline design, model, or measurement method.

### Main Findings

- 📊 One short bullet stating the headline finding.

### Contributions

- 📘 Contribution 1

### One-sentence Takeaway

A one-sentence takeaway.

### My thoughts

- Constructive comments.
```

## Writing Rules

- Write in English.
- Keep the writing concise, precise, and academic.
- Write like a top finance journal note, not like a long summary.
- Do not add a separate summary, literature synthesis, batch log, or extra sections.
- Do not add unsupported interpretations.
- If you include a formula, write it in valid Obsidian/MathJax syntax so it renders correctly, rather than as raw LaTeX text or code-formatted pseudo-math.
- Add topic links only when highly certain.
- If the paper has no clear journal information, write `"working paper"`.

## Metadata Rules

- Quote `title`, `authors`, and `journal` in YAML to avoid invalid front matter.
- Keep `year` numeric.
- Use the exact PDF filename in the `PDF: [[...]]` line.
- Add topic links only when highly certain.
- Use suitable topic links when they fit well, including:
  - `[[FOMC]]`
  - `[[Multimodel]]`
  - `[[Text analysis]]`
  - `[[LLM]]`
  - `[[Behavioral Finance]]`
  - `[[Macro]]`
  - `[[ML in asset pricing]]`
  - `[[Bond]]`
  - `[[Portfolio Optimization]]`
  - `[[Theoretical]]`
  - `[[Empirical]]`
- If these do not fit the paper well, generate one or two more suitable topic links based on the paper's core question, market, method, or field.
- If a knowledge base is available, reuse matching existing topic names before creating a new topic.
- If uncertain about a topic link, omit it rather than guess.

## Section Rules

### Abstract

- Present the abstract as a paragraph rather than bullets.
- Copy the paper's abstract verbatim.
- Remove trailing or standalone JEL codes such as `JEL ...`.
- Do not paraphrase.

### Research Questions

- Use compact bullets with the `🎯` marker.
- Use the paper's own wording when the core question is stated clearly in the abstract, introduction, or conclusion.
- If the paper does not state the question cleanly, write a tightly condensed version that stays very close to the authors' framing.
- Keep this section very short, usually one bullet and at most two.
- Focus only on the central research question, not every subquestion.

### Sample and Data

- Use compact bullets with the house markers.
- Use `📌` for the sample line.
- Use modality-appropriate markers such as `📝`, `🎙️`, or `🎥` for the key data lines.
- Use `📈` for the frequency or outcome-data line.
- Keep this short.
- State the sample period, market or setting, and scope.
- Always state the overall frequency of the key X data used to construct the main variables and the main Y or outcome data, such as daily, monthly, annual, quarterly, minute-level, answer-level, or meeting-level.
- If X and Y are observed at different frequencies, state both explicitly, for example `X` is annual while `Y` is monthly.
- If there are multiple core inputs at different frequencies, name the main ones separately rather than collapsing them into a vague label like "high-frequency" or "panel data."
- Describe only the key data used to construct the main variables.
- Do not list every auxiliary dataset.

### Key Variables

- Use compact bullets with the `🔑` marker unless a modality-specific marker is clearly better.
- Include only the main dependent variable(s) and the key independent variable(s).
- Do not include control variables.
- Name variables clearly and define them briefly.
- If notation is useful, render it with proper inline math such as `$...$` and keep it short.

### Method

- Use compact bullets with the `⚙️` marker.
- Keep this section concise.
- Describe only the baseline empirical strategy or main modeling approach.
- Name the method concretely and specifically, not generically.
- If the paper uses an empirical design, identify the exact design variant when available, such as `stacked difference-in-differences`, `staggered-adoption DID`, `TWFE event-study`, `Sun-Abraham event-study`, `Callaway-Sant'Anna DID`, `local projections`, `Bartik IV`, `shift-share IV`, `regression discontinuity`, `synthetic control`, `high-frequency identification`, or `Fama-MacBeth cross-sectional regression`.
- If the paper uses machine learning, signal processing, or NLP, identify the exact named model, architecture, or tool when available, such as `BERT`, `FinBERT`, `Sentence-BERT`, `RoBERTa`, `Whisper`, `Praat`, `FaceReader`, `Azure Video Indexer`, `XGBoost`, `random forest`, `LSTM`, `transformer encoder`, `contrastive learning`, or `factor analysis`.
- If the method combines multiple steps, state the exact baseline identification design and the exact named model or measurement tool used to build the core variables.
- Do not include robustness checks, extensions, or every auxiliary specification.
- Do not turn this section into a workflow summary or a long methods paragraph.

### Main Findings

- Use compact bullets with the `📊` marker.
- Keep this section very short and centered on the paper's core findings.
- Lead with the single headline result that best answers the research question.
- Add only the few additional findings needed to interpret that headline result.
- Usually write two to four bullets, and use one bullet if the paper's contribution is dominated by one central finding.
- Do not include robustness results.
- Do not restate data, method, or contribution claims here.

### Contributions

- Use compact bullets with the `📘` marker.
- Base this section on the paper's own contribution claims, but summarize them in your own concise wording.
- Keep it terse.
- If the paper explicitly frames its contribution in one, two, or several parts, mirror that structure rather than forcing a fixed bullet count.
- Keep each contribution point short and clean.

### One-sentence Takeaway

- Write one sharp sentence that captures the core contribution, method, and main finding.
- Keep it compressed and memorable.

### My thoughts

- Do not restate the paper.
- Write from the perspective of a senior finance scholar with multiple publications in JF, JFE, and RFS.
- Keep the prose accurate but more direct and easier to understand. Explain clearly why a point is a strength, a limitation, or a useful extension.
- Give constructive evaluation only: strengths, limitations, and plausible extensions.
- Favor extensions relevant to finance, asset pricing, bond markets, or ML when appropriate.
- Do not use wikilinks in this section.

## Style and Formatting

- Follow the House Template and formatting rules in this skill.
- Use compact bullets as the default format for section content.
- Use the house icon markers by default rather than plain bullets:
  - `🎯` for `Research Questions`
  - `📌` plus `📝` / `🎙️` / `🎥` / `📈` for `Sample and Data`
  - `🔑` for `Key Variables`
  - `⚙️` for `Method`
  - `📊` for `Main Findings`
  - `📘` for `Contributions`
- These icon markers are required unless the user explicitly forbids them.
- Never replace these icon markers with plain bullets on your own.
- Do not output garbled, corrupted, or abnormal symbols. If marker rendering or text looks broken in the generated file, fix it before finishing.
- Keep spacing clean and readable in Obsidian.

## Editing Discipline

- Modify only the target `.md` file unless the user explicitly asks for more.
- Use the House Template headings unless the user explicitly requests a different structure.
- Never fabricate missing facts.
- If a point is not yet accurate enough, return to the PDF and resolve it before writing.
- When updating a note, use the House Template and correct its content against the PDF.





