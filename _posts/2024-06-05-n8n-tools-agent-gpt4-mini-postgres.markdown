---
layout: post
title: "n8n Chat Tools Agent with Postgres Memory"
date: 2024-06-05 00:00:00 -0000
categories: n8n workflow
---

This post shows a minimal n8n workflow that connects the built‑in Chat Trigger
to the AI Agent node running in **Tools Agent** mode. Conversation memory is
stored in PostgreSQL so the agent can recall previous interactions.

Download the workflow JSON here:
[chat-to-tools-agent-postgres.json](/workflows/chat-to-tools-agent-postgres.json)

The workflow includes three nodes:

1. **Chat Trigger** — The standard Chat Trigger node that receives incoming chat
   messages.
2. **AI Agent** — Runs the `gpt-4.1-mini` model as a Tools Agent.
3. **Postgres Chat Memory** — Stores the conversation history in Postgres.

The Chat Trigger forwards each message to the AI Agent and connects to the
Postgres Chat Memory node so the agent keeps context across conversations.

Import the JSON file in n8n to try it out.
