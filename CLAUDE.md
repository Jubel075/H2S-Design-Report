# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a LaTeX technical report for a sour gas sweetening (H2S removal) system design at the TA-58 production facility for Staatsolie Suriname. The document covers conceptual engineering design, technology evaluation, economic analysis, and risk assessment for a caustic scrubbing system with biological treatment.

## Build Commands

```bash
# Compile the document (requires LuaLaTeX)
latexmk -lualatex main.tex

# Generate nomenclature (handled automatically by .latexmkrc)
makeindex -s nomencl.ist -o main.nls main.nlo

# Clean auxiliary files
latexmk -c

# Full clean including PDF
latexmk -C
```

The project uses LuaLaTeX (not pdfLaTeX) due to `fontspec` and `unicode-math` packages for custom fonts.

## Document Structure

- **main.tex** - Root document with preamble, custom commands, and document assembly
- **Sections/** - Main report chapters (exec_summ, background, tech_eval, eco_eval, cost_est, risk_mit, etc.)
- **Appendix/** - Technical appendices (calculations, data_sheets, p&ids, python_sim)
- **Graphics/** - Figures including TikZ diagrams (.tex), PDFs, and PNGs
- **references.bib** - BibTeX bibliography (IEEEtran style)

## Custom LaTeX Commands

Chemical formulae shortcuts defined in main.tex:
- `\HtwoS` - H2S
- `\COtwo` - CO2
- `\NaOH`, `\NaHS`, `\NaTwoS` - Sodium compounds

Mass transfer parameters:
- `\KGa`, `\kGa`, `\kLa` - Mass transfer coefficients
- `\HTUog`, `\NTUog` - Transfer unit parameters
- `\Ha`, `\Eenh` - Hatta number, Enhancement factor

## Key Conventions

- Equations, figures, and tables are numbered by section (e.g., Equation 2.1)
- Use `\SI{}{}` for all units (siunitx package)
- Use `\ce{}` for chemical formulas (mhchem package)
- Cross-references use cleveref: `\cref{}`, `\Cref{}`
- Roman numeral lists use custom `romanlist` environment
