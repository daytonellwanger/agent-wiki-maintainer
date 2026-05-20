# Wiki Structure

This document defines the structure of the agent-wiki — the persistent, LLM-maintained knowledge base on AI agents.

## Directory Layout

```
agent-wiki/
├── index.md               # Catalog of all pages, organized by category
├── log.md                 # Append-only chronological log of ingests and updates
├── overview.md            # High-level synthesis of the current state of AI agents
├── concepts/              # Foundational ideas, patterns, and techniques
│   └── <concept>.md
├── tools/                 # Specific frameworks, libraries, and platforms
│   └── <tool>.md
├── questions/             # Open questions from the editor, answered from wiki content
│   └── <question>.md
├── opinions/              # The editor's stated views and takes on topics in AI agents
│   └── <opinion>.md
└── newsletters/           # Archive of past newsletters; newest file = last-sent watermark
    └── YYYY-MM-DD.md
```

## Page Types

### `overview.md`

A high-level synthesis of the field — where things stand, what the key open questions are, and how major themes relate to each other. Updated as the wiki evolves. The starting point for a new reader.

### `index.md`

A catalog of all pages in the wiki, grouped by category. Each entry is a link plus a one-line description. The LLM reads this first when answering queries or deciding where to file new information.

Format:
```markdown
## Concepts

- [Tool Use](concepts/tool-use.md) — How agents invoke external tools and APIs
- [Memory](concepts/memory.md) — Mechanisms for agents to retain information across turns

## Tools

- [LangGraph](tools/langgraph.md) — Graph-based orchestration framework from LangChain

## Questions

- [When should you use multi-agent systems?](questions/when-to-use-multi-agent.md) — Tradeoffs between single-agent and multi-agent designs

## Opinions

- [Orchestrators should be thin](opinions/orchestrators-should-be-thin.md) — The case for keeping orchestration logic minimal
```

### `log.md`

An append-only record of every ingest.

Each log entry covers only what was actually added or updated — not what was considered and skipped. If a post was processed but nothing new was added to the wiki, write no log entry for it.

Each log entry includes two summaries:

**Technical**: files touched, links added or changed, new pages created.

**Reader-friendly**: written for someone already familiar with the wiki. Explains what actually changed in the field and why it matters — not just what files were edited. This is the material for the newsletter email.

Each entry begins with a consistent prefix for easy grepping:

```markdown
## [2026-05-04]

- Pages updated: concepts/tool-use.md, tools/openai-agents-sdk.md (new)
- Summary: OpenAI released a new Agents SDK…
```

### `concepts/<concept>.md`

One page per concept, pattern, or technique. Examples: `tool-use.md`, `memory.md`, `multi-agent.md`, `planning.md`, `evaluation.md`. Each page covers:

- What the concept is and why it matters
- Key variants and tradeoffs
- Links to relevant tools

### `tools/<tool>.md`

One page per framework, library, or platform. Examples: `langchain.md`, `langgraph.md`, `openai-agents-sdk.md`. Each page covers:

- What it is and what problem it solves
- Key features and design decisions
- How it relates to alternatives
- Links to relevant concept pages

### `questions/<question>.md`

One page per open question posed by the editor. Examples: `when-to-use-multi-agent.md`, `best-memory-architecture.md`. Each page follows this structure:

```markdown
# <Question stated as a title>

<The question written out in full>

## Background

<Context needed to understand the question. Link generously to relevant wiki pages.>

## Perspectives

### <Perspective or position 1>

<One take on the question, referencing specific wiki pages.>

### <Perspective or position 2>

<A contrasting or complementary take.>

## Answer

<Synthesis of the current best answer, drawn from and linking to wiki pages. If the wiki doesn't yet
have enough information to answer the question, leave this section as a note describing what's missing.>

## See Also

- [Related Page](../concepts/related.md) — one-line description
```

Questions are answered solely by referencing existing wiki content. If a question cannot be fully answered, the Answer section notes what information is missing — which informs future research and ingestion.

### `opinions/<opinion>.md`

One page per opinion or take expressed by the editor. Examples: `orchestrators-should-be-thin.md`, `evals-are-underrated.md`. Each page follows this structure:

```markdown
# <Opinion stated as a declarative title>

<The opinion written out in full, in the editor's own words.>

## Context

<Background needed to understand why this opinion is held. Link generously to relevant wiki pages.>

## Reasoning

<The argument for the opinion. Reference specific wiki pages where relevant.>

## Counterarguments

<Steelman the opposing view. Note any cases where the opinion may not hold.>

## See Also

- [Related Page](../concepts/related.md) — one-line description
```

Opinions represent the editor's personal views and are not required to be derived from wiki content — they may go beyond or even contradict the current consensus captured elsewhere in the wiki.

## Conventions

- All pages use standard markdown with wiki-style links (`[Tool Use](concepts/tool-use.md)`).
- Every non-index, non-log, non-overview page ends with a `## See Also` section listing related pages.
- The `overview.md` is rewritten (not appended) when significant new information arrives; the log records what changed.
- Page titles match filenames: `tool-use.md` → `# Tool Use`.
- `log.md` is append-only — never edit past entries.

## What Belongs in Concepts vs. Tools

- **Concepts**: Ideas, patterns, techniques, and mechanisms — things that exist independent of any specific implementation. Examples: `tool-use.md`, `memory.md`, `multi-agent.md`.
- **Tools**: Specific frameworks, libraries, SDKs, platforms, or protocols. Examples: `langgraph.md`, `mcp.md`, `openai-agents-sdk.md`.

When in doubt: if you could describe it without naming a product, it's a concept.

## Mission

The wiki exists to track **significant, durable developments** in AI agents: new techniques, architectural patterns, frameworks, and capability advances that matter to someone building or thinking seriously about agents.

It is not a news feed. It should not grow unboundedly. A smaller wiki with high-signal entries is better than a comprehensive one diluted by noise.

### What belongs

- New agent architectures, patterns, or techniques that represent a genuine advance
- Frameworks, SDKs, and tools that meaningfully change how agents are built
- Research results that shift understanding of what agents can or can't do
- Model releases, but **only** if the model represents a significant capability jump relevant to agents (e.g., substantially better tool use, reasoning, or context handling) — not routine version bumps or benchmark improvements

### What does not belong

- Personality-driven content: profiles, interviews, takes on individuals, org drama
- Routine model announcements, version releases, or incremental benchmark improvements
- News that is primarily business/hype (funding rounds, partnerships, market share) without technical substance
- Ephemeral events: conference recaps, product launches without novel technical content

When in doubt, ask: *would someone building an agent in six months still care about this?* If yes, it belongs. If it's likely to be forgotten or superseded quickly, it does not.

## Quality Bar

- Be concise. Each page should be readable in a few minutes.
- Prefer accurate and current over exhaustive.
- Link generously between pages — that's what makes this a wiki.
- Do not repeat information already on a linked page; reference it instead.
