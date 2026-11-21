# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Markdown-only knowledge base of notes about the **Music Thing Modular Workshop System**, a DIY modular audio synthesizer designed by Tom Whitwell. There is no code, build, lint, or test tooling. The work here is finding information about the system, understanding it, and writing it up as notes.

## Where information comes from

Prefer these sources, roughly in this order (URLs are in [README.md](README.md)):

1. **Workshop Quick Start** (`musicthing.co.uk/Workshop_Quick_Start/`). This is the main per-submodule reference. Each submodule has an anchor, for example `#ring-mod` or `#stompbox`.
2. **Workshop System Build Guide** (`musicthing.co.uk/Workshop_System_Build_Guide/`).
3. Tom Whitwell's GitHub org (`github.com/tomwhitwell`) for schematics, firmware, and hardware sources.
4. The Workshop Notes newsletter (Substack), the Music Thing Discord, and videos (Mylar Melodies, DivKit).
5. The browser-based virtual Workshop System at `vincentmaurer.de/patch-notes/` for trying out patches.

Every note should cite the source URL a fact came from. If a fact comes from somewhere other than the official Music Thing pages, say so in the note. Don't present guesses about circuit behavior as fact.

## Note structure

The notes follow the physical hardware: a **module** is a physical panel, and a **submodule** is a labeled section on that panel. [Modules/README.md](Modules/README.md) is the index of modules and their submodules, listed left to right as they sit in the case: Computer, VCO, Amplifier, Humpback Filters, Slopes, Mix.

So far only the VCO module has notes. To add notes for another module, copy the VCO pattern:

- `Modules/<module>-module.md`: names the submodules as labeled on the front panel and lists each submodule's note file.
- `Modules/<module>-<submodule>-submodule.md`, for example `vco-ring-mod-submodule.md`. Each one starts with:
  - an `# <Name> submodule` heading
  - a `Physical Module: <Module>` line
  - the Quick Start anchor URL for that submodule
  - then a prose description: what it does, alternate uses (for example, Ring Mod working as a VCA), and specs (for example, Stompbox pedal power)
- When you add a module or submodule note, update [Modules/README.md](Modules/README.md) and the parent `<module>-module.md`.

The Computer module is a separate, programmable product that has its own ecosystem (see the DivKit video in the README). Keep its notes clearly separated from the analog modules.

## Formatting

These rules come from `.editorconfig` and `.gitattributes`:

- LF line endings, UTF-8 without a BOM, and a final newline at the end of each file.
- Markdown files indent with 2 spaces. Don't use tabs. [Modules/README.md](Modules/README.md) currently mixes a tab with spaces in its nested list; fix that if you edit the file.
- Trailing whitespace is trimmed, so use `<br>` for a hard line break instead of trailing spaces.
- `.vscode/settings.json` holds the cSpell word list. Add proper nouns there (for example, Whitwell) when a new one is flagged.
