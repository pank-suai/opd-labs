BUILD_DIR = build
DOCS_DIR = docs

DOC_SOURCE = $(DOCS_DIR)/index.typ
DOC_OUTPUT = $(BUILD_DIR)/index.pdf

.PHONY: all docs clean

all: $(DOC_OUTPUT)

docs: $(DOC_OUTPUT)

$(DOC_OUTPUT): $(DOC_SOURCE)
	@mkdir -p $(BUILD_DIR)
	@echo "🗒️ Сборка документации"
	@typst compile --root .. $< $@

clean:
	@echo "🔥 Очистка проекта..."
	@rm -rf $(BUILD_DIR)
