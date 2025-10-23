# AGENTS.md

## Build Commands
- Build PDF: `make` or `make docs` (compiles .typ to PDF using typst)
- Clean: `make clean` (removes build/ directory)
- No lint/test commands (document generation project)

## Code Style Guidelines

### Document Structure
- Use `#import "lib/gost.typ": init` for GOST-compliant formatting
- Title page: Use `titlepage()` function with required parameters
- Headings: `= Level 1`, `== Level 2`, etc. (auto-numbered 1.1 format)

### Typography
- Font: Times New Roman (14pt body, 12pt title page)
- Language: Russian (ru) with hyphenation enabled
- Paragraphs: Justified, 1.2em leading, 1.25cm first-line indent
- Code blocks: JetBrains Mono 10pt, left-aligned

### Figures & Tables
- Images: Supplement "Рисунок" (Figure)
- Tables: Supplement "Таблица" (Table), caption on top
- References: Auto-numbered, custom formatting for figures

### Bibliography
- Format: YAML in bibl.yml files
- Fields: type, title, author, date, publisher, isbn/doi, etc.
- Citation style: GOST-compliant

### Naming Conventions
- Files: snake_case (index.typ, gost.typ, titlepage.typ)
- Functions: camelCase (init, titlepage, ch)
- Variables: camelCase

### Error Handling
- No explicit error handling (Typst handles compilation errors)
- Validate YAML bibliography syntax manually