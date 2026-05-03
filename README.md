# pi

Central container for the [Pi](https://github.com/badlogic/pi-mono) coding agent ecosystem — housing prompt templates, default configuration, and aggregated documentation.

---

## What This Repository Is

This repository serves three roles in the Pi ecosystem:

1. **[Prompt Templates](#prompts)** — Reusable `/<command>` prompt definitions invoked within the Pi editor.
2. **[Configuration Distribution](#configuration)** — `settings.json` that defines default provider, model, packages, and theme for Pi installations.
3. **[Documentation Hub](#documentation)** — Aggregated MkDocs site pulling docs from `pi.agents`, `pi.hitl`, and `pi.web` into a single searchable experience.

---

## Prompts

Prompt templates live in the [`prompts/`](prompts/) directory as individual `.md` files. They are invoked in the Pi editor by typing `/` followed by the filename without `.md`.

| Command | File | Description |
|---|---|---|
| `/create-new-prompt` | [`prompts/create-new-prompt.md`](prompts/create-new-prompt.md) | Generate a new prompt template following structured agent design methodology |

### Prompt Conventions

- **Filename becomes the command**: `create-new-prompt.md` is invoked as `/create-new-prompt`.
- **Frontmatter**: Each template uses YAML frontmatter with `description` (required) and `argument-hint` (optional).
- **Arguments**: Pi templates support positional arguments via `$1`, `$2`, `$@`, and `${@:N}`.

For the full convention specification, see [`AGENTS.md`](AGENTS.md).

---

## Configuration

[`agents/settings.json`](agents/settings.json) is the default configuration distributed to Pi installations. It specifies:

- **Default Provider & Model**: `fireworks` / `accounts/fireworks/models/kimi-k2p6`
- **Default Thinking Level**: `medium`
- **Packages**: External Pi extensions pulled from Git and npm (`pi.hitl`, `pi.agents`, `@tintinweb/pi-tasks`, etc.)
- **Theme**: `midnight-ocean`

This file is the source of truth for what capabilities and defaults are available out-of-the-box.

---

## Documentation

This repository builds the **Pi Documentation Hub** — a centralized, searchable documentation site aggregating extension docs from across the ecosystem.

**Published site**: [https://andrewhowdencom.github.io/pi/](https://andrewhowdencom.github.io/pi/)

The site uses [MkDocs](https://www.mkdocs.org/) with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) and the [multirepo plugin](https://github.com/jdoiro3/mkdocs-multirepo-plugin) to pull in documentation from:

- [`pi.agents`](https://github.com/andrewhowdencom/pi.agents) — Agent selection and switching
- [`pi.hitl`](https://github.com/andrewhowdencom/pi.hitl) — Human-in-the-loop permission sandbox
- [`pi.web`](https://github.com/andrewhowdencom/pi.web) — Web-based UI for Pi

Each extension maintains its own documentation; this site brings them together.

---

## Development

### Prerequisites

- Python 3.9+
- pip

### Local Documentation

Install dependencies and serve the docs locally:

```bash
pip install -r requirements.txt
mkdocs serve
```

Deploy to GitHub Pages (handled automatically by [`.github/workflows/docs.yml`](.github/workflows/docs.yml) on pushes to `main`):

```bash
mkdocs gh-deploy --force
```

---

## Repository Structure

```
pi/
├── agents/
│   ├── settings.json          # Default Pi configuration distribution
│   └── *.md                   # Subagent prompt definitions
├── docs/
│   ├── index.md               # Documentation hub landing page
│   └── stylesheets/           # Custom CSS
├── prompts/
│   └── *.md                   # Pi prompt templates (/<command>)
├── .github/workflows/
│   └── docs.yml               # GitHub Pages deployment
├── mkdocs.yml                 # Documentation site configuration
├── pyproject.toml             # Python project metadata
├── AGENTS.md                  # Agent context and prompt conventions
└── README.md                  # This file
```

---

## Related Repositories

- [`pi`](https://github.com/andrewhowdencom/pi) — This repository (prompts, config, docs hub)
- [`pi.agents`](https://github.com/andrewhowdencom/pi.agents) — Agent selection extension
- [`pi.hitl`](https://github.com/andrewhowdencom/pi.hitl) — Permission sandbox extension
- [`pi.web`](https://github.com/andrewhowdencom/pi.web) — Web UI extension
- [`pi-mono`](https://github.com/badlogic/pi-mono) — Upstream Pi project
