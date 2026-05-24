# Obsidian Second Brain

**Status:** 🔄 Active  
**Started:** Apr 13, 2026  

## What This Is

A knowledge management system built on Obsidian — and, increasingly, a working synthesis
engine rather than just a capture vault. Research, articles, and video content come in
through standardized templates; Claude helps turn them into synthesized writing and a
densely linked web of notes. Capture was the first phase. Synthesis is now the main event.

## Architecture

- **Core tool:** Obsidian — a local-first markdown vault
- **Capture layer:** multiple standardized intake paths, each one a template that lands
  source material in a consistent, metadata-tagged shape:
  - **Web Clipper** — browser extension that clips web content straight into the vault
  - **YouTube transcript template** — captures a video's raw transcript with metadata in a
    consistent format, so it arrives synthesis-ready rather than as an unstructured dump
- **Synthesis layer:** the heart of the system now. Claude works captured material into
  two outputs that compound differently — **synthesized writing** (essays, arguments, and
  distilled pieces drawn from across the vault) and **structural linking** (maps of
  content, topic hubs, and dense cross-links connecting notes captured weeks apart)
- **Writing practice:** dedicated Sunday sessions — the weekly forcing function that keeps
  synthesis moving
- **Integration:** Grok Brain Export (Project 18) feeds structured AI outputs into the
  vault as linked knowledge nodes

## Key Decisions

**Local-first over cloud.** Obsidian stores everything as plain markdown on disk. No
vendor lock-in, no subscription required for core features, and the files are readable by
any tool — including Claude via direct file access.

**Templates over ad-hoc capture.** Every intake path is a template — Web Clipper, the
YouTube transcript template, and more to come. A consistent, metadata-tagged shape at
capture time is what lets the synthesis layer scale: synthesis is only as fast as the
material is uniform. Standardize the input and the hard part gets cheaper.

**Capture is the means; synthesis is the point.** Passive capture without processing is
hoarding. The Sunday writing practice and the ongoing linking work are what turn the vault
from a filing cabinet into a thinking tool.

## Lessons Learned

A knowledge system lives or dies on its synthesis layer. The shift this project went
through — from "capture everything" to "synthesize relentlessly" — is the whole game.
Captured notes that are never processed don't compound; synthesized writing and linked
maps of content do.

Standardized capture is what makes synthesis scale. Once every source — a clipped article,
a YouTube transcript — arrives in the same shape, Claude can synthesize across them without
re-parsing each one from scratch. The template work is unglamorous, and it's the reason
the synthesis volume is now high.

The AI layer earns its keep finding non-obvious connections between notes captured weeks
apart — the linking a human wouldn't do by hand, but that produces real insight when
surfaced.

---

*Part of the [Claude Architect Journey](../../README.md)*
