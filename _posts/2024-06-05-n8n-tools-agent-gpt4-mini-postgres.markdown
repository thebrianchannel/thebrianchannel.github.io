---
layout: post
title: "n8n Chat Tools Agent with Postgres Memory"
date: 2024-06-05 00:00:00 -0000
categories: n8n workflow
---

This post shows a minimal n8n workflow that connects a basic chat trigger to a
Tools Agent powered by the `gpt-4.1-mini` model. Conversation memory is stored in
PostgreSQL so the agent can recall previous interactions.

Download the workflow JSON here:
[chat-to-tools-agent-postgres.json](/workflows/chat-to-tools-agent-postgres.json)

The workflow includes two nodes:

1. **Chat Trigger** — A Webhook node listening for `POST` requests on the path
   `chat-trigger`.
2. **Tools Agent** — Uses the OpenAI node to run the `gpt-4.1-mini` model with
   the memory strategy set to Postgres.

When a request hits the Webhook, the chat message is forwarded to the Tools
Agent. The agent processes the input with GPT‑4.1‑mini and keeps context in a
Postgres-backed memory.

Import the JSON file in n8n to try it out.
