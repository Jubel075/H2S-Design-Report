# Project Analysis: H2S Design Report

This project is a formal, multi-section technical report on "Sour Gas Sweetening for Gas Engine at TA-58," created using LaTeX. The report details the design, evaluation, and justification of a process to remove Hydrogen Sulfide (H₂S) from sour gas, likely using a "Caustic Scrubbing" process.

## File Structure

The project is organized into several directories, each with a specific purpose:

*   **Root Directory:** Contains the main LaTeX file (`main.tex`), bibliography (`references.bib`), build configuration (`.latexmkrc`), and final output PDF.
*   **`Sections/`:** Holds the individual chapters of the report, which are included by `main.tex`. This modular structure makes editing and management easier.
*   **`Appendix/`:** Contains supplementary technical materials like calculations, data sheets, and diagrams. Note: As of the last analysis of `main.tex`, the appendix files are commented out and not included in the final document.
*   **`Graphics/`:** A repository for all visual aids. This includes:
    *   Images and PDFs of process diagrams (BFD, PFD).
    *   `.tex` files that programmatically generate diagrams using TikZ (e.g., `design_mindmap.tex`).
    *   Company logos.
*   **`Fonts/`:** Includes the "Fira Code" font, used for monospaced text in the report.
*   **`Presentation/`:** Contains a Beamer presentation (`presentation.tex`) that likely summarizes the main report for a different audience.
*   **`Context/`:** Contains files that are not part of the report itself, but were used for analysis or planning.

## LaTeX Build System

*   **Compiler:** The project is configured to be compiled with **`lualatex`**. This is explicitly set in `main.tex` and is necessary for the `fontspec` and `unicode-math` packages to work correctly with custom fonts.
*   **Build Tool:** The presence of a `.latexmkrc` file indicates that **`latexmk`** is the preferred tool for automating the build process. `latexmk` handles running `lualatex` and `bibtex` the required number of times to resolve all cross-references and citations.
*   **Main File:** The root document is `main.tex`.

## Report Structure (as per `main.tex`)

The main body of the report is assembled using `\input` commands in the following order:

1.  `Sections/exec_summ.tex` (Executive Summary)
2.  `Sections/introduction.tex`
3.  `Sections/technology_options.tex`
4.  `Sections/spent_caustic.tex`
5.  `Sections/eco_eval.tex` (Economic Evaluation)
6.  `Sections/risk_mit.tex` (Risk Mitigation)
7.  `Sections/control_safety.tex`
8.  `Sections/conclusions.tex`

The bibliography is handled by `references.bib` using the `IEEEtran` citation style.

## Key LaTeX Packages & Conventions

The project leverages several powerful LaTeX packages and defines custom commands to ensure consistency:

*   **Typography:** `fontspec` and `unicode-math` are used to load custom fonts (`STIX Two Text`, `TeX Gyre Heros`, etc.).
*   **Graphics:** `tikz` is used extensively for creating professional diagrams and flowcharts directly within LaTeX.
*   **Units:** `siunitx` is configured to ensure consistent formatting of scientific units throughout the document.
*   **Chemistry:** The `mhchem` package is used for typesetting chemical formulas.
*   **Cross-referencing:** `hyperref` and `cleveref` are used for intelligent hyperlinking and cross-referencing of figures, tables, and equations.
*   **Custom Commands:** The preamble of `main.tex` defines several custom LaTeX commands for commonly used chemical formulas (e.g., `\HtwoS`) and engineering parameters (e.g., `\KGa`). This is a key convention to follow when adding or editing content.

## Associated Files

*   **Beamer Presentation:** A presentation summarizing the report exists in the `Presentation/` directory. It uses the `beamerthemestaatsolie` style, suggesting a custom theme.