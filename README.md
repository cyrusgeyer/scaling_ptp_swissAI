# Research Paper / Grant Proposal Template

A clean, minimal LaTeX template for research papers or grant proposals.

## 📄 Reference Paper

- `arXiv-2512.21323v1/` — "Parallel Token Generation for Language Models" ([arXiv:2512.21323](https://arxiv.org/abs/2512.21323)) — basis for this grant proposal

## 📋 Swiss AI Guidelines

This repo includes application guidelines from [Swiss AI](https://www.swiss-ai.org):

- `swissai_guidelines_large_projects.txt` — [Large Projects Application Guidelines](https://docs.google.com/document/d/1r6HKNBiEeyFPiC5gyPd3r5JX1nshBmASgLzNFC4bhsk/edit?tab=t.0)
- `swissai_guidelines_small_projects.txt` — [Small Projects Rolling Review](https://docs.google.com/document/d/1o8x3Ow-3kYx0FZXQrXsFwT-rwDqR747wZcZHxQIWXKw/edit?tab=t.0#heading=h.80aa7z1a2bc)

## 📁 Structure

- `main.tex` — Main document
- `math_commands.tex` — Reusable math notation (vectors, matrices, etc.)
- `bibliography.bib` — Bibliography file

## 🧱 Requirements

- **Compiler**: `pdflatex` (or `lualatex`/`xelatex`)
- **Citation backend**: `bibtex`

## 🔨 Compilation

```bash
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

Or use VS Code with LaTeX Workshop extension (recommended recipe below).

## 🛠 VS Code Settings (`.vscode/settings.json`)

```json
{
  "latex-workshop.latex.recipes": [
    {
      "name": "pdflatex -> bibtex -> pdflatex x2",
      "tools": ["pdflatex", "bibtex", "pdflatex", "pdflatex"]
    }
  ],
  "latex-workshop.latex.tools": [
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": ["%DOCFILE%"]
    }
  ]
}
```
