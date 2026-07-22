# Gemini

`@cinatra-ai/gemini-assistant` is the Gemini conversational assistant for the Cinatra platform, part of the multi-vendor Assistants epic (cinatra-ai/cinatra#1873). It is an agent-kind extension whose payload is the `cinatra/config.json` assistant declaration — not a compilable OpenAgentSpec flow. Chat with it under the lowercase tag `@gemini`: all assistant tags are lowercase per owner ruling 2026-07-22 (groganz), and the declaration validator rejects a non-normalized `preferredTag`. It is conversation-only today, carrying no tools and no MCP block until native-MCP activation lands (cinatra-ai/cinatra#1717). It handles no credentials of its own — Gemini API access resolves through the required `@cinatra-ai/gemini-connector` at runtime. Part of cinatra-ai/cinatra#1876.

## Works with

- `@cinatra-ai/gemini-connector` — required runtime dependency (`^0.1.4`); it resolves Gemini API credentials so this package never touches keys.

## Capabilities

- Answers questions, explains material, and reasons over information you bring to the conversation, powered by Google Gemini.
- Drafts, refines, summarizes, and rewrites text through the `chat-assistant-core` skill bundle.
- Runs locally on the host runtime and replies in-thread (launch `local`, delivery `host-runtime`) under the `@gemini` tag.
