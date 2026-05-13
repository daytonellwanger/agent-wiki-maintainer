# CLAUDE.md

This file is for you, Claude, as a collaborator on this project. (Note: `wiki-maintainer/CLAUDE.md` is a separate file for the wiki maintainer agent itself — that one is not for you.)

## What This Project Is

I'm building an AI agent that maintains a wiki on AI agents. Read `wiki-maintainer/overview.md` for the full picture.

## Repo Structure

- **`wiki-maintainer/`** — everything the agent needs to run: instructions, design docs, and agent definitions. This is the product. Read `wiki-maintainer-overview.md` to understand its design and structure.
- **Everything else** — meta-code for building and improving `wiki-maintainer/`. For example, instructions on how to update the wiki belong in `wiki-maintainer/`; instructions on how to update those instructions belong outside it.

The wiki itself lives in a separate repo. See `wiki-maintainer/wiki-location.txt` for its location.

## Design Principles

### Keep `wiki-maintainer-overview.md` in sync

`wiki-maintainer-overview.md` catalogs every file in `wiki-maintainer/` and what it does. Any time you add, remove, or rename a file there, update `wiki-maintainer-overview.md` in the same change.

### Keep reusable logic in its own file

When a piece of logic could be useful in more than one flow, extract it into a dedicated file rather than inlining it everywhere it's needed. Other files then reference that file instead of duplicating the steps. This keeps each flow focused and makes shared logic easy to find and update in one place.
