# How to Add an Opinion

When the user asks you to add an opinion to the wiki, follow this process.

## 1. Clarify the opinion

Before doing anything else, make sure the opinion is phrased as precisely as possible. Work with the user to sharpen the statement — a clear, declarative title makes the page easy to find and understand. Resolve any ambiguity before proceeding.

## 2. Check for related opinions

Read `index.md`. Identify any existing opinion pages that are closely related. Read those pages in full — they may provide context, share reasoning this opinion builds on, or represent a contrasting view worth acknowledging.

## 3. Create the opinion page

Create a new file at `opinions/<slug>.md` in the wiki. Follow the format defined in `design/wiki-structure.md`. Write the opinion, Context, Reasoning, and Counterarguments sections based on what the user has told you. Do not invent reasoning or positions the user hasn't expressed — ask if you need more detail.

Update `index.md` to add an entry under `## Opinions`.

## 4. Ensure coverage of referenced concepts and tools

Re-read the completed page. Enumerate every major concept and tool it mentions — these are the building blocks a reader would need to understand or follow up on the opinion.

For each one, check `index.md` to see whether a corresponding wiki page already exists. For any that are missing, follow `design/how-to-add-concept-or-tool.md` to create the page.

Do this for every missing page before moving on. The goal is that every concept and tool named on the page is a live link a reader can follow.

## 5. Update the log

Append a log entry noting the new opinion page and any other pages that were created or updated in the process.
