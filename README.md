# Cortex66 MCP server

Cortex66 connects the AIs you already use (ChatGPT, Claude, Gemini, Codex, Cursor and others) to one place: your work sessions, the tasks you give them, and the facts you confirmed. This repository describes the hosted MCP server. The server itself runs at Cortex66; there is nothing to install.

- **Server URL:** `https://cortex66.com/api/mcp` (streamable HTTP)
- **Sign-in:** OAuth. Your AI app opens the Cortex66 sign-in page the first time; no key to paste.
- **Registry name:** `io.github.yotke/cortex66` in the [Official MCP Registry](https://registry.modelcontextprotocol.io)
- **Website:** https://cortex66.com

## Connect

| App | How |
|---|---|
| Claude, ChatGPT, Gemini and other chat apps | add a custom connector (remote MCP server) with the URL above |
| Claude Code | `claude mcp add --transport http cortex66 https://cortex66.com/api/mcp` |
| Cursor, VS Code and other MCP apps | add a remote (HTTP) server with the URL above |
| Any app, from the terminal | `npx cortex66 connect` sets up the apps it finds on your computer |

Then say "connect to Cortex66" in the chat.

## Tools

Nothing here costs money. "Writes" means it adds to your own Cortex66 session, plan or memory for you to see, keep or discard; nothing is sent to anyone else without your approval in Cortex66.

| Tool | What it does | Kind |
|---|---|---|
| `ping` | Test the connection | read |
| `session_open` | Bind this conversation to a Cortex66 session | writes |
| `session_close` | Close the link to the bound session | writes |
| `session_report` | Report progress to the bound session | writes |
| `session_read` | Read the bound session | read |
| `memory_search` | Search your confirmed memories | read |
| `brain_plan` | Ask the Cortex66 brain for a plan | read |
| `consult_cortex` | Find your confirmed memories that fit a question | read |
| `task_list` | List the tasks you gave this conversation | read |
| `task_submit` | Submit the result of a task | writes |
| `pass_to_my_ai` | Pass a hand-over to another of your AIs | writes |
| `memory_propose` | Propose a memory for you to confirm | writes |
| `session_link` | Save this chat's link in Cortex66 | writes |
| `plan_split` | Split a request into its jobs before planning | read |
| `plan_skills` | List the planning skills | read |
| `plan_check` | Check a plan against the request | read |
| `plan_meeting` | Open a planning meeting for a complex request | writes |
| `my_ais_status` | Check which of your AIs are connected and ready | read |
| `team_open` | Open a multi-step team plan across your connected AIs | writes |
| `skill_find` | Find a skill that fits | read |
| `skill_check` | Check a skill before it is shared | read |
| `skill_export` | Get a skill as a SKILL.md | read |
| `project_tools` | List your hosted project tools | read |
| `project_call` | Run a tool of your hosted project | writes |

Coming in the next release: `tool_find` (find the right tool for a need) and `tool_call` (run it by its id), so an AI loads only the tools it needs.

## Safety and privacy

- Everything you connect stays inside your own workspace; nothing learned in one workspace is used in another.
- Tool results and descriptions are treated as data, never as instructions.
- Your AI cannot approve, pay or send for you: those steps stay with you in Cortex66.
- Privacy policy: https://cortex66.com/privacy · Terms: https://cortex66.com/terms

## About this repository

It holds the registry entry (`server.json`) and this page, so MCP directories can list the server. The Cortex66 product code is not here.
