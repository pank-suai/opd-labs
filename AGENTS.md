# AGENTS.md

## Build Commands
- Build PDF: `cd <subfolder> && make` (compiles `docs/index.typ` → `build/index.pdf`)
- Clean build: `make clean` (removes build/ directory)
- Single document: `typst compile --root .. docs/index.typ build/index.pdf` (from subfolder)
- No tests/lints (document generation project using Typst 0.14.0)

## Project Structure
- Each subfolder = independent document (answers_theme*, report_practice*, questions_theme*)
- `docs/index.typ` - main document file
- `docs/lib/gost.typ` - GOST formatting library (Russian standard)
- `docs/lib/titlepage.typ` - title page template
- `docs/bibl.yml` - bibliography (YAML format, GOST-compliant)

## Code Style

### Document Structure
```typst
#import "lib/gost.typ": init
#show: init
// Content starts here
```
- GOST init must wrap entire document body
- Headings: `= Level 1`, `== Level 2` (auto-numbered "1.1")
- Title page parameters: authors, city, department, documentName, education, group, teachers, position

### Typography & Formatting
- Font: Times New Roman 14pt, Russian (ru) with hyphenation
- Paragraphs: justified, 1.2em leading, 1.25cm first-line indent
- Code: JetBrains Mono 10pt, left-aligned, no justify
- Lists: `---` marker, 1.25cm indent
- Figures: "Рисунок" (images), "Таблица" (tables, caption on top)

### Bibliography (bibl.yml)
- Required fields: type, title, author, date
- Types: Book, Article, Thesis, Patent
- Optional: publisher, serial-number (isbn/doi), page-total, url
- Use YAML syntax - validate before building to avoid compile errors

### Naming
- Files: snake_case (index.typ, gost.typ)
- Functions: camelCase (init, titlepage, ch)