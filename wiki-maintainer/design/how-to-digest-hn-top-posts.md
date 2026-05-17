# How to Digest Today's HN Top Posts

When the user asks you to digest today's HN top posts, follow these steps.

## Step 1: Fetch the Top Story IDs

Call the HN API:

```
GET https://hacker-news.firebaseio.com/v0/topstories.json
```

This returns an array of up to 500 story IDs ranked by HN's algorithm. Take the first 50.

## Step 2: Fetch Metadata for Each Post

For each of the 50 IDs, fetch:

```
GET https://hacker-news.firebaseio.com/v0/item/{id}.json
```

Collect: `id`, `title`, `url`, `time`, `score`, `descendants` (comment count), and `type`.

Skip any item whose `type` is not `story`.

## Step 3: Filter to Posts from Today

Keep only posts where the `time` field (a Unix timestamp) falls on today's date. Discard the rest.

## Step 4: Identify Agent-Relevant Posts

For each post from today, decide whether it is relevant to AI agents based solely on its title and URL — do not fetch article content at this stage.

A post is relevant if it primarily concerns:
- AI agents, autonomous agents, or multi-agent systems
- LLMs, language models, or AI reasoning and planning
- Agent frameworks, tools, or infrastructure (e.g., memory, orchestration, sandboxing)
- Agent evaluation, safety, or alignment
- Notable AI labs, products, or research in the agent space

When in doubt, err on the side of including the post — the `hn-post-digester` will determine whether it contains anything new worth adding to the wiki.

## Step 5: Process Each Relevant Post

For each relevant post identified in Step 4, delegate to the `hn-post-digester` sub-agent, passing the full HN post URL:

```
https://news.ycombinator.com/item?id={id}
```

Process posts sequentially, not in parallel, so wiki updates don't conflict.

## Step 6: Summarize

After all posts have been processed, give the user a brief summary: how many of the 50 posts were from today, how many were agent-relevant, and what the notable updates to the wiki were.
