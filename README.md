You spend minutes each morning deciding what to work on. This is a tool to help.

# TaskLog.ai
A self-deployable, AI-assisted task prioritizer. It sorts your list.

---

## Why this exists
Productivity tools change, get acquired, or add paywalls. This is a static template you can deploy and own. It will only change if you change it.

## Try the demo
A live instance is running for testing. Nothing you enter is stored.
**https://tasklog-ai.casey-digennaro.workers.dev**

---

## What it is
- A single Cloudflare Worker. The entire application is in one file.
- Stateless. No database, logs, or history. Your list exists only for the request.
- Fork-first. You own your copy. There is no upstream service to depend on.
- Private. AI calls go directly from your deployment to your chosen provider.

## Features
*   **Priority Sorting:** Submit an unordered task list. It returns a ranked order with reasoning for each item.
*   **Context Injection:** You can attach notes or deadlines to inform the prioritization.
*   **Simple API:** A documented POST endpoint. No authentication.
*   **Fleet Compatible:** Optional integration with the open Cocapn protocol.
*   **One Limitation:** It does not store or recall your tasks between sessions. It is a processor, not a database.

---

## Quick Start
1.  Click "Deploy with Cloudflare Workers" from your fork of this repository.
2.  Set one environment variable: `AI_API_KEY` (your OpenAI, Anthropic, or compatible API key).
3.  It's live. Send a POST request to `/prioritize` with your tasks.

## How it Works
This is a stateless function. You send a JSON payload with a list of tasks and optional context. It forwards this to your configured AI model, formats the response, and sends the ranked list back. Nothing is written to disk or cached.

## Bring Your Own Keys
The code contains no embedded keys or proxies. All AI calls are made directly from your deployed Worker to your provider. You are not charged through any intermediary.

## Contributing
Improvements are welcome. Fork the repository, make your changes, and open a pull request to share them back.

## License
MIT License

Attribution: Superinstance & Lucineer (DiGennaro et al.)

---

<div align="center">
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> · 
  <a href="https://cocapn.ai">Cocapn</a>
</div>