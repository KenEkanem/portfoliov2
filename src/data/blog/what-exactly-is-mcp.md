---
title: "What exactly is an MCP?"
description: "A plain-language explainer for the protocol that lets AI assistants actually do things, not just talk."
published: 2026-03-16
category: "AI"
readTime: "4 min read"
featured: false
tags: [mcp, ai, protocols]
---

![MCP connects one AI assistant to your calendar, files, databases and search](/images/blog/mcp-cover.webp)

Assistants like Claude or ChatGPT are good at conversation, but conversation alone can't check your calendar, read a file, or search the web on your behalf. They need a way to reach the tools and data that live outside the chat window. That's the gap the Model Context Protocol was built to close.

## Why MCP exists

Before a standard existed, every connection between an AI model and an outside tool was a one-off integration. Each calendar, each database, each API needed its own custom glue code, rebuilt for every assistant that wanted to use it. MCP replaces that patchwork with a single, shared way for AI to talk to other apps.

![Before MCP, every AI app needed custom glue for every tool. With MCP, each side connects once](/images/blog/mcp-integrations.webp)

## What it actually lets AI do

With MCP in place, an assistant can:

- Connect to your apps: calendars, files, databases
- Use tools: search engines, calculators, even 3D printers
- Take action instead of only describing what it would do

## How the pieces fit together

The AI app you use is the **host**. Inside it, an **MCP client** holds a connection to each **MCP server**, and every server is a small program that wraps one thing: your calendar, a folder of files, a search engine. Servers offer three kinds of things to the AI: **tools** it can call, **resources** it can read, and **prompts** it can reuse.

![The host app runs one MCP client per server, and each server wraps a real system](/images/blog/mcp-architecture.webp)

A server can be surprisingly small. The one below gives an AI a single calendar tool, and the config file tells a host like Claude Desktop how to start it.

![Write a server, plug it into the host, then just ask](/images/blog/mcp-snippet.webp)

## Why it's worth caring about

- One standard connection instead of a custom integration per tool
- Far less repeated work for developers building AI-powered products
- Assistants that are genuinely useful, not just conversational

## A concrete before-and-after

Without MCP, Claude can only talk with you. With it, Claude can read your calendar, check relevant emails, update a document, and remind you about a meeting closer to an assistant than a chatbot.

![The same request without MCP gets instructions. With MCP, it gets done](/images/blog/mcp-chat.webp)

**Fun fact:** MCP is open source, released by Anthropic, the creators of Claude.

**The short version:** think of MCP as USB-C for AI one standard plug that lets AI applications connect to the things you actually use, so they can help rather than just respond.

![USB-C lets one laptop plug into any device. MCP lets one AI assistant plug into any tool](/images/blog/mcp-usb-c.webp)
