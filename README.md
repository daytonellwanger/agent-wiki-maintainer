# Agent News

This project is an AI agent that maintains a wiki on AI agents.

You can see technical details of how it works and is structured in [wiki-maintainer-overview.md](wiki-maintainer-overview.md).

Everything the agent needs to run - instructions, design docs, and agent definitions - is in the `wiki-maintainer/` directory. This is the product.

Everything else is meta-code for building and improving `wiki-maintainer/`. For example, instructions on how to update the wiki belong in `wiki-maintainer/`; instructions on how to update those instructions belong outside it.

The wiki itself lives in a separate repo. See `wiki-maintainer/wiki-location.txt` for its location.

## Examples

You can open Claude Code in this directory and say things like:

"I'd like to add a new section to the wiki for my opinions on topics. Can you do that for me?"

"When adding a new tool to the wiki, we should search for all direct competitors and add pages for them too."
