# tasklog-ai
You spend time every morning staring at your todo list, rearranging lines instead of starting your work.

This tool helps you decide quickly. You send one request and receive a ranked task list with reasoning. No accounts. No tracking. ✨

A live instance is running at **https://tasklog-ai.casey-digennaro.workers.dev**. Nothing you enter is stored.

---

## Why This Exists
Many task apps add features without solving the core issue: choosing what matters *now*. This does not manage your entire workflow. It provides a clear priority order when you ask.

---

## Quick Start
1.  **Fork** this repository. This is a fork-first project.
2.  **Deploy** to Cloudflare Workers with the "Deploy with Workers" button.
3.  **Set** one environment variable: `AI_API_KEY` (your OpenAI, Anthropic, or compatible API key).
4.  **Use** the single POST endpoint.

**Example Request:**
```bash
curl -X POST https://your-deployment.workers.dev/prioritize \
  -H "Content-Type: application/json" \
  -d '{"tasks": ["Write project report", "Reply to client email"]}'
```

---

## How It Works
This is a single, stateless Cloudflare Worker. Your task list is sent directly from your deployment to your configured AI provider. The ranked list and reasoning are returned immediately. There is no caching, logging, or storage.

---

## Features
*   **Priority Sorting:** Submit an unordered list; receive a ranked order with reasoning for each item.
*   **Add Context:** Include deadlines, energy levels, or notes to influence the priority weighting.
*   **Simple API:** One POST endpoint (`/prioritize`). No authentication or SDK required.
*   **Direct & Private:** AI API calls go straight from your Worker to your provider.
*   **Fleet Compatible:** Works with the open Cocapn Fleet protocol.
*   **Specific Limitation:** Processes up to 15 tasks per request to ensure fast, consistent responses.

---

## License
MIT License.

Attribution: Superinstance and Lucineer (DiGennaro et al.).

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> &middot; <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>