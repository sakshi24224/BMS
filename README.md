# BMS CHO Cell Productivity KG — User Manual

Quarto book source for the BMS Knowledge Graph User Manual (Version 3).

## Prerequisites

### 1. Install Quarto
Download and install from https://quarto.org/docs/get-started/

```bash
# Verify installation
quarto --version  # should be >= 1.4
```

### 2. Install the Quarto VSCode Extension
In VSCode: Extensions → search **"Quarto"** → Install

### 3. (Optional) Install R or Python
Only needed if you add executable code chunks. For this manual, no R/Python is required — all content is static Markdown.

---

## Project Structure

```
bms-kg-manual/
├── _quarto.yml           # Project config (book structure, themes, formats)
├── index.qmd             # Welcome / preface page
├── references.bib        # Bibliography
├── assets/
│   ├── custom.scss       # Light theme overrides
│   └── custom-dark.scss  # Dark theme overrides
└── chapters/
    ├── 01-orientation.qmd
    ├── 02-internal-data.qmd
    ├── 03-public-literature.qmd
    ├── 04-cross-evidence.qmd
    ├── 05-pathway-enrichment.qmd
    ├── 06-transcription-factors.qmd
    ├── 07-hypothesis-testing.qmd
    ├── 08-target-prioritization.qmd
    ├── 09-utilities.qmd
    └── glossary.qmd
```

---

## Building the Manual

### HTML (recommended for daily use)
```bash
cd bms-kg-manual
quarto render          # builds everything
quarto preview         # live-reload server at localhost:4321
```

### PDF (for sharing / printing)
```bash
quarto render --to pdf
```
Output: `_book/BMS-CHO-Cell-Productivity-Knowledge-Graph.pdf`

### Single chapter preview (fast iteration)
```bash
quarto preview chapters/02-internal-data.qmd
```

---

## Editing Content

- Each chapter is a self-contained `.qmd` file in `chapters/`
- Add new sections with standard Markdown headers (`##`, `###`)
- Use the provided CSS classes for consistent styling:

| Class | Usage |
|---|---|
| `.query-box` | Wrap NLQ example queries in a `:::` div |
| `.step-box` | Numbered workflow steps (requires HTML div) |
| `.evidence-badge .badge-deg` | Inline evidence layer badges |
| `.callout-note / tip / warning` | Quarto callout blocks |

### Example: adding a query box
```markdown
::: {.query-box}
Which genes are upregulated in high vs. low Nivo producers?
:::
```

### Example: adding a callout
```markdown
::: {.callout-tip}
Your tip text here.
:::
```

---

## Adding a New Chapter

1. Create `chapters/10-new-topic.qmd` with YAML front matter:
   ```yaml
   ---
   title: "New Topic"
   subtitle: "One-line description"
   ---
   ```
2. Add it to the `chapters:` list in `_quarto.yml`
3. Run `quarto render`

---

## Customising the Theme

Edit `assets/custom.scss` for light mode, `assets/custom-dark.scss` for dark mode.
Key variables are at the top of each file under `/*-- scss:defaults --*/`.

---

## Contact

yogesh.lakhotia@elucidata.io | elucidata.io
