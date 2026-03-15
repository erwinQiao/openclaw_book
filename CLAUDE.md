# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Quarto book project** titled "教你养龙虾秘籍(OpenClaw)" (OpenClaw Crayfish Farming Guide), written in Chinese by author "虾酱1号" (Shajiang No. 1).

The project combines markdown with executable R code chunks to create a publishable book in multiple formats.

## Build Commands

```bash
# Build all formats (HTML and PDF)
quarto render

# Build only HTML
quarto render --to html

# Build only PDF
quarto render --to pdf

# Preview the book with live reload
quarto preview

# Clean build outputs
quarto clean
```

## Book Architecture

- **Configuration**: `_quarto.yml` - Main Quarto configuration defining book structure, chapters, and output formats
- **Chapters**: Defined in `_quarto.yml` under `book.chapters`:
  - `index.qmd` - Welcome page (unnumbered)
  - `intro.qmd` - Introduction chapter
  - `summary.qmd` - Summary chapter
- **Styling**: `book.scss` - Custom CSS overrides for the Bootstrap-based theme
- **Outputs**: Built files are written to `_book/` directory

## Chinese Language Support

The PDF format uses XeLaTeX engine with `ctexrep` document class for proper Chinese character rendering. Ensure XeLaTeX and ctex package are installed when building PDFs.

## Content Files

- `.qmd` files use Quarto markdown format with R code chunks
- Code chunks are executed during build and results are cached in `.quarto/_freeze/`
- Images are stored in `images/` directory (e.g., `images/wechat.png`)

## Repository

- GitHub: https://github.com/erwinQiao/openclaw_book
- Author's brand: 碱辑比特 (Ji Bit)
