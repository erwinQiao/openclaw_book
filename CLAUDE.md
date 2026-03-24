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
- **Structure**: The book uses Quarto's part-based organization:
  - `index.qmd` - Welcome page (unnumbered)
  - `intro.qmd` - Introduction chapter with version history and book overview
  - **Part 1** (`firstpart.qmd`) - Groups theory/foundational chapters:
    - `openclawhistory.qmd` - OpenClaw development history
    - `openclawkey.qmd` - Core concepts and architecture
    - `openclawdevelop.qmd` - Current status and future directions
  - Additional parts and chapters can be added following this pattern
- **Styling**: `book.scss` - Custom CSS overrides for the Bootstrap-based theme (uses `cosmo` theme with custom `$primary: #D32F2F`)
- **Outputs**: Built files are written to `_book/` directory
- **Assets**:
  - `cover.png` - Book cover image
  - `share.png` - Favicon
  - `images/` - Directory for embedded images

## Chinese Language Support

The PDF format uses XeLaTeX engine with `ctexrep` document class for proper Chinese character rendering. Ensure XeLaTeX and ctex package are installed when building PDFs.

## Content Files

- `.qmd` files use Quarto markdown format with R code chunks
- Code chunks are executed during build and results are cached in `.quarto/_freeze/`
- Images are stored in `images/` directory (e.g., `images/wechat.png`)

## Content Organization

- **Part dividers** (e.g., `firstpart.qmd`) group related chapters and provide context
- **Callouts**: Uses Quarto callout blocks (`.callout-tip`, etc.) for highlighting important information
- **Blockquotes**: Used for emphasis and supplementary notes
- **Images**: Referenced with markdown syntax: `![](images/filename.png){fig-alt="description" fig-align="center"}`

## Writing Conventions

- Content is in **Simplified Chinese**
- Technical terms appear in English where appropriate (e.g., SaaS, Gateway-Node, MCP)
- Version update records are maintained in `intro.qmd`
- Author branding uses "碱辑比特" (Ji Bit)

## Repository

- GitHub: https://github.com/erwinQiao/openclaw_book
- Author: "虾酱1号" (Shajiang No. 1)
