# Research Paper / Grant Proposal Template

A clean, minimal LaTeX template for research papers or grant proposals.

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
