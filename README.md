# TaskLog.ai

You don't need another todo list. You need a tool that tracks your actual work.

This is a minimal, AI-assisted task logger built as a stateless vessel for the Cocapn Fleet. No database, no tracking, no subscription. You deploy it. You control it.

---

## Why this exists

Modern task managers are often bloated or lock you into their ecosystem. This is built to be the opposite: a single-file script that does one job. It is auditable, self-contained, and has zero runtime dependencies. It does not phone home.

**Live instance:** https://tasklog-ai.casey-digennaro.workers.dev

---

## What it does

*   **Zero Dependencies.** The entire application is one file. It deploys in seconds to Cloudflare Workers.
*   **Fork-First.** You own your copy. No central service can alter or sunset it for you.
*   **Bring Your Own AI.** Configure your own API keys for any LLM provider. No defaults.
*   **Fleet Native.** It speaks the Cocapn protocol and can interact with other vessels you run.

## Features

*   **AI Task Sorting.** Pass a list of tasks and receive them ordered by suggested priority.
*   **Basic Contextual Recall.** Provide previous task notes for more relevant AI suggestions.
*   **Stateless API.** A simple REST endpoint you can call from any script, CLI, or client.
*   **No Accounts.** No mandatory frontend. Use it as a private API for your own systems.

**One Limitation:** As a stateless worker, it does not store your task history. It processes input and returns output. Persistence is up to your client.

## Quick Start

1.  **Fork** this repository.
2.  Deploy it to Cloudflare Workers.
3.  Add your `AI_API_KEY` as an environment variable.
4.  Start sending POST requests.

## Architecture

It runs as a single Cloudflare Worker (`worker.ts`). It follows Cocapn Fleet protocol conventions. All state is managed in the request/response cycle. Your API keys exist only in your deployment environment.

## Bring Your Own Keys

You must provide your own AI API key. No keys are bundled, logged, or proxied. You can use OpenAI, Anthropic, or any compatible provider.

## Contributing

Improvements are welcome. Fork, make your changes, and open a pull request.

## License

MIT License

Attribution: Superinstance & Lucineer (DiGennaro et al.)

---

<div align="center">
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> · 
  <a href="https://cocapn.ai">Cocapn</a>
</div>