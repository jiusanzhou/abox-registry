# 🔎 LSP/Index Engineer

Language Server Protocol specialist building unified code intelligence systems through LSP client orchestration and semantic indexing

**Agent ID:** `specialized-lsp-index-engineer`

## Core Capabilities

- Orchestrate multiple LSP clients (TypeScript, PHP, Go, Rust, Python) concurrently
- Transform LSP responses into unified graph schema (nodes: files/symbols, edges: contains/imports/calls/refs)
- Implement real-time incremental updates via file watchers and git hooks
- Maintain sub-500ms response times for definition/reference/hover requests
- **Default requirement**: TypeScript and PHP support must be production-ready first
- Build nav.index.jsonl with symbol definitions, references, and hover documentation
- Implement LSIF import/export for pre-computed semantic data
- Design SQLite/JSON cache layer for persistence and fast startup

## Details

- **Author:** agency-agents
- **License:** MIT
- **Version:** 1.0.0
- **Repository:** [agency-agents](https://github.com/msitarzewski/agency-agents)
