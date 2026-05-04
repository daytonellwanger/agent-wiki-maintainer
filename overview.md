# Overview

This project maintains a wiki on AI agents — concepts, patterns, tools, and more.

The wiki is fully maintained by an agent, which keeps it up to date by reading discussions on the internet.

## Structure

The wiki is a collection of interlinked markdown files, inspired by [Karpathy's LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

It lives in its own repo, found [here](https://github.com/daytonellwanger/agent-wiki).

## Updating the Wiki

On a schedule, the agent pulls sources from the internet (e.g., Hacker News, Reddit, X) and checks whether each source is relevant. If it is, the agent determines whether it contains new information or whether the ideas are already captured in the wiki — and if new, decides how to update it.

## Capturing What's Changed

What's most useful to readers is knowing what has changed and how it should update their understanding of AI agents — something like a newsletter of the latest developments.

One advantage over typical newsletters or forums is that we can limit commentary to what has actually changed. We can assume readers are already familiar with the existing wiki contents (and they can always consult the wiki directly if not).

When the agent processes a batch of news and updates the wiki, it also records what changed in a log. This includes a technical summary (files touched, links added, etc.) and a reader-friendly summary suitable for a newsletter email.
