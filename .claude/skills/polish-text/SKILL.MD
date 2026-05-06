---
name: polish-text
description: >
  Use this skill whenever the user wants to clean up, polish, edit, or improve a draft text file or piece of writing. Triggers include phrases like "clean this up", "edit this", "improve this draft", "revise for clarity", "make this clearer", "organize this better", or any request to refine written content. Also use when the user uploads or pastes a text file and asks for edits, improvements, or feedback. Even if the user just says "can you improve this?" about a piece of text, use this skill.
---

# Polish Text Skill

## Purpose

Edit draft text for **organization and clarity** while preserving the author's voice and existing structure.

## Core Editing Principles

1. **Clarity first** — Rewrite sentences that are confusing, wordy, or ambiguous. Prefer plain language. Cut filler.
2. **Preserve tone** — Match the author's register (formal, casual, technical, conversational). Do not make the text sound more "AI-like" or generic.
3. **Respect existing structure** — The structure is assumed to be mostly correct. Only reorganize sections if there is a clear, obvious improvement (e.g., a point is buried that clearly belongs earlier, or a section is duplicated).
4. **Minimal footprint** — Prefer the smallest edit that achieves the goal. Don't rewrite what doesn't need rewriting.

## What to Edit

- **Clarity**: Untangle complex or run-on sentences. Replace vague language with specific language.
- **Conciseness**: Cut redundant words, phrases, or sentences that repeat points already made.
- **Flow**: Smooth transitions between ideas. Ensure paragraphs have a clear focus.
- **Consistency**: Fix inconsistent terminology, tense, or formatting style.
- **Organization** (only when clearly needed): Move misplaced content. Merge or split sections if it substantially helps the reader.

## What NOT to Edit

- Do not change the author's voice or style.
- Do not add new content, ideas, or sections unless explicitly asked.
- Do not remove content that is substantive (only cut true redundancy).
- Do not restructure the document if the existing structure is reasonable.

## Output Format

- Return the full edited text, ready to use.
- If the file is long (500+ words), briefly note the main changes made at the end (2–4 bullet points max), so the user understands what was changed and why.
- If you moved or removed something significant, flag it so the user can confirm it was intentional.

## Edge Cases

- **Multiple files**: Edit each file separately, label outputs clearly.
- **Structured formats** (e.g., bullet lists, numbered steps): Preserve the format. Edit within each item for clarity.
- **Technical writing**: Preserve technical terminology exactly. Do not simplify domain-specific terms.
- **Short texts** (< 100 words): Just return the edited version with no summary notes needed.
