# LaTeX Setup Notes for This Project

This project uses the Springer `sn-jnl.cls` template and requires a specific setup to properly compile citations, tables, and Lua-enhanced content.

## 🧱 Requirements

- **Compiler**: `lualatex` (not `pdflatex` or `xelatex`)
- **Citation backend**: `bibtex` (not `biber`)
- **Bib style**: `sn-basic.bst` (must be in the project root)

## 📁 File Setup

- Make sure the bibliography file is named `sn-bibliography.bib`
- Ensure the `.bst` file matching your selected style (e.g., `sn-basic.bst`) is present in the **project root** directory — it is not always bundled with TeX Live.
- Use `\bibliography{sn-bibliography}` and **do not** use `biblatex` or `\addbibresource`.

## 🛠 VS Code Settings (`.vscode/settings.json`)

Make sure `latex-workshop` is configured to use the correct build sequence:

```json
"latex-workshop.latex.recipes": [
  {
    "name": "lualatex -> bibtex -> lualatex",
    "tools": ["lualatex", "bibtex", "lualatex", "lualatex"]
  }
],
"latex-workshop.latex.tools": [
  {
    "name": "lualatex",
    "command": "lualatex",
    "args": ["-synctex=1", "-interaction=nonstopmode", "-file-line-error", "%DOC%"]
  },
  {
    "name": "bibtex",
    "command": "bibtex",
    "args": ["%DOCFILE%"]
  }
]
```
