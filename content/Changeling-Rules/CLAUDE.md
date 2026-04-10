# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **Obsidian vault** converting the WOD: Changeling V20 Rulebook from PDF into organized Obsidian markdown files. There are no build/lint/test commands — the work is pure content processing.

**Note:** Content is being filled in directly into the created files (manual copy-paste from PDF), rather than via the `ingest/` folder workflow.

**Phase 1 (current):** Take raw text files placed in `ingest/` and:
1. Organize them into a sensible folder structure
2. Repair PDF-copy formatting artifacts (broken line wrapping, garbled columns, misplaced page numbers)

**Future phase:** Condense content into quick-reference rules, free of WOD's verbose prose style.

## Workflow

Raw source files appear in `ingest/`. Process them by:
- Creating a new chapter folder (e.g., `Chapter Five Rules/`)
- Splitting monolithic files into per-topic `.md` files where appropriate
- Fixing formatting issues introduced by PDF-to-text conversion (see common issues below)
- Adding Obsidian wiki-links `[[Page Name]]` for cross-references to other notes

The `ingest/` files `books table of contents.md` and `books index.md` serve as reference for organizing content and understanding what belongs where.

## Reference: Completed Work

`Chapter Four Arts and Realms/` is the gold standard for how finished content should look:
- Top-level overview files (`Arts.md`, `Cantrips.md`, `Bunks.md`, `Realms/Overview.md`, etc.)
- Subtopics broken into individual files under subdirectories (`Arts/Chicanery.md`, `Realms/Actor.md`, etc.)
- Obsidian wiki-links used for all cross-references: `[[Arts]]`, `[[Fae]]`, `[[Time]]`, etc.

## Common PDF Formatting Issues to Fix

- Broken mid-word line wraps (e.g., `"S ides"` → `"Sides"`)
- Two-column PDF text interleaved (page numbers and headings from the right column appearing mid-sentence in the left)
- Garbled section headers mixed into body text
- Inconsistent spacing around headings
- PDF aside boxes (extra info boxes inserted mid-topic) are represented as `> [!example]` Obsidian callouts

## Ingest Status

- `Inanimae.md` — considered complete, needs organizing
- `Creatures.md` — unfinished/incomplete source
- `books table of contents.md` / `books index.md` — reference only, not for direct conversion
