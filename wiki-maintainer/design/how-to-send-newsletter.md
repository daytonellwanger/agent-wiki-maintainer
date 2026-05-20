# How to Send a Newsletter

When the user asks you to send a newsletter (or "write a newsletter", "generate a newsletter"), follow these steps.

## Step 1: Find the Last Newsletter

List the `newsletters/` directory in the wiki. Files are named `YYYY-MM-DD.md`. Find the most recent one — its date is the watermark for what's already been covered.

## Step 2: Read the Log Since Then

Read `log.md` in the wiki. Extract all entries dated after the last newsletter's date.

If there are no new log entries since the last newsletter, tell the user and stop — there's nothing to write about.

## Step 3: Apply Editor Steering

If the user provided guidance (e.g., "focus on memory", "skip the MCP updates"), apply it when deciding what to highlight. Otherwise use your judgment.

## Step 4: Draft the Newsletter

Draft a short newsletter based on the log entries:

- **Title**: `## Agent Wiki — [Month Day, Year]` (e.g., `## Agent Wiki — May 19, 2026`)
- **Body**: Cover the most notable updates. Link to the relevant wiki page for more detail. Include a small bit of context only if a reader unfamiliar with the topic would need it to understand why this matters

Do not try to cover everything in the log. Pick the updates with the most signal per the wiki's mission (see `design/wiki-structure.md`). The newsletter should be skimmable in under a minute.

Drafting principles:

- **No theme sentence.** Don't open with a sentence that tries to group all the updates into a single theme. Lead directly with the first item.
- **Lead with principles, not particulars.** When a log entry uses a specific project or company as an example, open with the general insight and name the example afterward — not the other way around.
- **Skip old news.** If a development was already widely known before the log entry was written, omit it.
- **Skip business news.** Company acquisitions, funding rounds, and similar corporate events are generally not of interest to the newsletter's audience (people building agents). Skip them unless there's a direct technical implication.
- **Skip wiki housekeeping.** Log entries that reflect the wiki catching up on existing knowledge (adding concept pages, tool pages, etc.) are not newsletter items — they are not new developments in the field.

## Step 5: Review with Editor

Show the draft to the user. Give them a chance to revise the content or ask for changes before saving.

If they do request changes, try to see if there's a general principle behind the ask and update these instructions to include it.

## Step 6: Save the Newsletter

Once the user approves, save the newsletter as `newsletters/YYYY-MM-DD.md` in the wiki (using today's date). This records what was covered and advances the watermark for the next newsletter.
