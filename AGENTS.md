# AGENTS.md

## Build Commands
- Build PDF: `make` or `make docs` (runs `typst compile --root .. docs/index.typ build/index.pdf`)
- Clean: `make clean` (removes build/ directory)
- No lint/test commands (document generation project)

## Project Structure
- Each subfolder contains a separate document (answers_theme1/, report_practice1/, etc.)
- docs/index.typ: Main document file
- docs/lib/: Shared libraries (gost.typ, titlepage.typ)
- docs/bibl.yml: Bibliography in YAML format
- Makefile: Build configuration

## Code Style Guidelines

### Document Structure
- Import: `#import "lib/gost.typ": init` for GOST compliance
- Initialize: `init(titlepage(...))` wrapper around document body
- Title page: `titlepage()` with parameters (authors, city, department, documentName, etc.)
- Headings: `= Level 1`, `== Level 2`, etc. (auto-numbered "1.1" format)

### Typography
- Font: Times New Roman (14pt body, 12pt title page)
- Language: Russian (ru) with hyphenation enabled
- Paragraphs: Justified, 1.2em leading, 1.25cm first-line indent
- Code blocks: JetBrains Mono 10pt, left-aligned

### Figures & Tables
- Images: Supplement "Рисунок", Tables: "Таблица" (caption on top)
- References: Auto-numbered with custom formatting

### Bibliography
- Format: YAML in bibl.yml (fields: type, title, author, date, publisher, isbn/doi)
- Citation style: GOST-compliant
- Types: Book, Article, Thesis, Patent

### Naming Conventions
- Files: snake_case (index.typ, gost.typ, titlepage.typ)
- Functions/Variables: camelCase (init, titlepage, ch)

### Error Handling
- Typst handles compilation errors automatically
- Manually validate YAML bibliography syntax before building