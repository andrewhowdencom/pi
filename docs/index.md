# Pi Documentation

Welcome to the **Pi Documentation Hub** — a centralized resource for the [Pi coding agent](https://github.com/badlogic/pi-mono) ecosystem.

Pi is a terminal-based coding agent harness that integrates LLM reasoning with your development environment. This site aggregates documentation from across the Pi extension ecosystem so you can find everything in one place.

---

## Extensions

<div class="grid cards" markdown>

-   :material-account-switch-outline:{ .lg .middle } **Agents**

    ---

    Select and switch between specialized agent personas. The pi.agents extension adds visual agent selection and lightweight switching with full conversation history preservation.

    [:octicons-arrow-right-24: Go to Agents docs](agents/index.md)

-   :material-shield-check-outline:{ .lg .middle } **HITL**

    ---

    Human-in-the-loop permission sandbox. The pi.hitl extension uses CEL expressions to define fine-grained approval rules for tool calls, keeping you in control of what the agent can do.

    [:octicons-arrow-right-24: Go to HITL docs](hitl/index.md)

-   :material-web:{ .lg .middle } **Web**

    ---

    A web-based user interface for the pi coding agent. Provides a browser-based chat interface with real-time streaming, tool call visualization, and session management via WebSocket bridge.

    [:octicons-arrow-right-24: Go to Web docs](web/index.md)

-   :material-server-network:{ .lg .middle } **LiteLLM**

    ---

    Pi extension that adds LiteLLM as a first-class provider with automatic model discovery. Point it at your LiteLLM proxy and all configured models appear in Pi's `/model` selector.

    [:octicons-arrow-right-24: Go to LiteLLM docs](litellm.md)

-   :material-tune:{ .lg .middle } **OpenAI**

    ---

    Pi extension for OpenAI-compatible endpoints with provider-specific sampling parameters — `repetition_penalty`, `top_k`, `mirostat`, and more. Defaults to Fireworks AI, supports any OpenAI-compatible API.

    [:octicons-arrow-right-24: Go to OpenAI docs](openai.md)

</div>

---

## Getting Help

- **Search** — Use the search bar at the top of the page to find topics across all extensions.
- **Edit** — Click the :material-pencil: icon on any page to suggest edits via GitHub.
- **Repository** — Visit the [pi container project](https://github.com/andrewhowdencom/pi) on GitHub.

---

## About This Site

This documentation hub uses [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme, aggregating documentation from multiple repositories using the [mkdocs-multirepo-plugin](https://github.com/jdoiro3/mkdocs-multirepo-plugin). Each extension maintains its own documentation in its repository; this site brings them together into a single searchable experience.
