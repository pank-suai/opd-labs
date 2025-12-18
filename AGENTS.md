# AGENTS.md

## Build & Verify
- **Build Document**: `cd <subfolder> && make` (outputs `build/index.pdf`)
- **Direct Compile**: `typst compile --root .. docs/index.typ build/index.pdf` (from subfolder)
- **Validation**: No linters/tests. Manually verify `bibl.yml` YAML syntax before building.

## Project Structure
- Subfolders (e.g., `report_practice*`) are independent documents.
- `docs/index.typ`: Main content file.
- `docs/lib/`: GOST formatting (`gost.typ`) and title templates (`titlepage.typ`).
- `docs/bibl.yml`: Bibliography data (required: `type`, `title`, `author`, `date`).

## Code Style
- **Boilerplate**: Use `#import "lib/gost.typ": init` and `#show: init`.
- **Formatting**: Times New Roman 14pt (ru), 1.2em leading, 1.25cm first-line indent.
- **Headings**: `=` for Level 1, `==` for Level 2 (auto-numbered).
- **Figures**: `Рисунок` (image), `Таблица` (table, caption on top).
- **Code**: JetBrains Mono 10pt, left-aligned.
- **Naming**: `snake_case` for files; `camelCase` for functions.
