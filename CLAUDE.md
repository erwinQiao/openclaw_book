# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Quarto book project** titled "教你养龙虾秘籍(OpenClaw)" (OpenClaw Crayfish Farming Guide), written in Chinese by author "虾酱1号" (Shajiang No. 1). The book is a comprehensive guide to the OpenClaw AI Agent framework, covering theory, deployment, configuration, and practical use cases.

The project combines markdown with executable R code chunks to create a publishable book in multiple formats (HTML and PDF).

## Build Commands

```bash
# Build all formats (HTML and PDF)
quarto render

# Build only HTML
quarto render --to html

# Build only PDF (requires XeLaTeX and ctex)
quarto render --to pdf

# Preview the book with live reload
quarto preview

# Clean build outputs and cache
quarto clean
```

## Book Architecture

### Configuration Structure
- **`_quarto.yml`** - Main Quarto configuration defining book structure, chapters, and output formats
- **HTML output**: Uses Bootstrap `cosmo` theme with custom overrides in `book.scss`
- **PDF output**: Uses XeLaTeX engine with `ctexrep` document class for Chinese character support

### Content Organization

The book uses a **four-part structure** with part-based dividers:

1. **Part 1: 理论知识** (Theory/Foundations) - `firstpart.qmd`
   - `openclawhistory.qmd` - AI Agent evolution and OpenClaw development history
   - `openclawkey.qmd` - Core concepts and Gateway-Node architecture
   - `openclawdevelop.qmd` - Current status, ecosystem, and future directions

2. **Part 2: 部署实战** (Deployment) - Planned
   - Installation, environment setup, cloud deployment, containerization

3. **Part 3: Skill 系统与配置** (Skills & Configuration) - Planned
   - Skill system, model configuration, security, cost management

4. **Part 4: 实际使用案例** (Use Cases) - Planned
   - Real-world examples and community contributions

### Special Files
- **`index.qmd`** - Welcome page (unnumbered), introduces the book's purpose
- **`intro.qmd`** - Introduction with version update records and book overview
- **Part dividers** (e.g., `firstpart.qmd`) - Provide context for grouped chapters

## Chinese Language Support

**Critical for PDF builds**: The PDF format requires:
- XeLaTeX engine (specified in `_quarto.yml`)
- `ctexrep` document class for proper Chinese character rendering
- `\usepackage[UTF8]{ctex}` in header

Ensure XeLaTeX and ctex package are installed on the build system.

## Content Conventions

### Writing Style
- **Language**: Simplified Chinese (简体中文)
- **Technical terms**: Keep in English where appropriate (e.g., SaaS, Gateway-Node, MCP, Agent)
- **Tone**: Educational yet conversational, matching the "养虾人" (crayfish farmer) persona
- **Author branding**: Use "碱辑比特" (Ji Bit) for author attribution

### Markdown Patterns

**Callouts** - Use Quarto callout blocks with these types:
```markdown
::: callout-tip
知其然然后知知其所以然
:::

::: callout-note
AutoGPT 框架 是一个开源的自主 AI 智能体系统
:::
```

**Blockquotes** - For emphasis and supplementary notes:
```markdown
> SaaS: Software as a Service（软件即服务）
```

**Images** - Reference with markdown syntax:
```markdown
![](images/filename.png){fig-alt="description" fig-align="center" width="50%"}
```
- Store all images in `images/` directory
- Use descriptive alt text
- Common sizes: 50% for screenshots, full-width for diagrams

**Version Updates** - Maintain in `intro.qmd` under "## OpenClaw版本更新记录":
```markdown
**YYYY年M月D日**
- Feature one
- Feature two
```

### Content Structure Patterns

**Part divider files** (like `firstpart.qmd`) should:
- Set context for the upcoming chapters
- Use callouts to highlight key learning objectives
- List all chapters in the part with brief descriptions
- Include motivational blockquotes

**Chapter files** should:
- Start with a clear, descriptive heading
- Use hierarchical sections (##, ###) for organization
- Include images and diagrams where helpful
- Balance depth with readability

## Build System Notes

- **Output directory**: `_book/`
- **Freeze cache**: `.quarto/_freeze/` stores executed code chunk results
- **Session files**: `.quarto/quarto-session-*` directories are temporary build artifacts
- **Search index**: `_book/search.json` generated for HTML output

## Assets

- **`cover.png`** - Book cover image
- **`share.png`** - Favicon for web version
- **`images/`** - All embedded images (currently: `wechat.png`, `AI agent.png`)

## Styling

The `book.scss` file customizes the Bootstrap theme:
- **Primary color**: `$primary: #D32F2F` (red)
- **Font size**: Root set to 18px
- **Custom heading styles** - Adjusted margins and weights for h2-h5
- **Code styling** - Custom colors and gradient background for pre blocks
- **Cover image** - Custom sizing with shadow and rounded corners

## Common Tasks

### Adding a new chapter to an existing part:
1. Create new `.qmd` file in project root
2. Add it to the `chapters` list in `_quarto.yml` under the appropriate part
3. Build and preview

### Adding a new part:
1. Create a part divider `.qmd` file (e.g., `secondpart.qmd`)
2. Add part entry to `_quarto.yml` with `part:` and nested `chapters:`
3. Create chapter files for the new part
4. Update `intro.qmd` to mention the new part in the book overview

### Updating version records:
1. Edit `intro.qmd`
2. Add new date entry under "## OpenClaw版本更新记录"
3. Use consistent format: `**YYYY年M月D日**`

## Repository

- **GitHub**: https://github.com/erwinQiao/openclaw_book
- **Author**: "虾酱1号" (Shajiang No. 1)
- **Brand**: 碱辑比特 (Ji Bit)
