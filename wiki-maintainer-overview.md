# Wiki Maintainer — Component Overview

This document describes how the wiki maintainer works and its components.

## What It Is

`wiki-maintainer/` contains everything needed to run an AI agent that maintains a wiki on AI agents. The agent reads sources from the internet, decides what's worth adding, and updates a separate wiki repo accordingly. It can also answer open questions by researching the web and updating the wiki with findings.

The wiki itself lives at the path in `wiki-location.txt`. A separate, git-ignored file is used to make the setup more flexible.

---

## Entry Points

### `CLAUDE.md`

The top-level system prompt for the agent. Points the agent to the other documents it needs and gives it basic instructions to follow.

### `overview.md`

A plain-language description of what the project is trying to accomplish — what the wiki is, how it gets updated, and the newsletter/changelog concept. Written for the agent to read as orientation, but also useful for human collaborators.

---

## Design Documents (`design/`)

These are the agent's reference docs — the "how to" guides it consults while working.

### `design/wiki-structure.md`

Defines the layout and conventions of the wiki repo.

### `design/how-to-update-wiki.md`

Step-by-step instructions for the agent when it has new content to ingest.

### `design/how-to-add-question.md`

Step-by-step instructions for when the user asks the agent to add a question to the wiki.

### `design/how-to-add-page.md`

Step-by-step instructions for when the user asks the agent to research a concept or tool and add a page for it.

### `design/how-to-add-concept-or-tool.md`

Reusable instructions for researching and creating a new concept or tool page. Referenced by other flows rather than duplicating the steps inline.

## Subagents (`.claude/agents/`)

These are specialized Claude agents invoked for specific ingestion tasks.

### `.claude/agents/hn-post-digester.md`

Handles end-to-end processing of a Hacker News post.

### `.claude/agents/topic-researcher.md`

Handles open-ended topic research.

---
