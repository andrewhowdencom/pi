# pi.prompts

This repository stores [pi](https://github.com/badlogic/pi-mono) prompt templates. Templates are invoked in the pi editor by typing `/` followed by the filename without `.md`.

## Repository Structure

Prompt templates live in the **`prompts/` subfolder** as individual `.md` files. This prevents non-prompt markdown files (`README.md`, `AGENTS.md`) from appearing in the pi autocomplete.

```
pi.prompts/
├── AGENTS.md         # This file — repo conventions and structure
├── README.md         # Project overview
├── LICENSE
└── prompts/
    └── *.md          # Pi prompt templates
```

## Prompt Template Conventions

- **Filename becomes the command**: `create-prompt.md` is invoked as `/create-prompt`.
- **Frontmatter**: Each template uses YAML frontmatter with:
  - `description` (required): One-line summary shown in autocomplete.
  - `argument-hint` (optional): Expected arguments using `<required>` and `[optional]` notation.
- **Arguments**: Pi templates support positional arguments via `$1`, `$2`, `$@`, and `${@:N}`.
- **Design methodology**: Prompts are designed using structured agent design methodology adapted from OpenCode's agent-creator pipeline:
  1. Requirements analysis (task, archetype, inputs, outputs, tools, standards)
  2. Pi frontmatter design (`description`, `argument-hint`)
  3. Cognitive architecture (AskAct self-verification, tool boundaries, context management)
  4. Structured prompt body (`## Identity` → `## Operational Rules` → `## Methodology` → `## Tool Usage` → `## Output Format` → `## Examples` → `## Critical Reminders`)
  5. Process supervision (step-wise execution, no cascading errors)
  6. Security hardening (conditional, only when tool access is implied)
  7. Instruction-following countermeasures (if/then/else, explicit tool mandates, position bias mitigation)
  8. Self-verification via mental simulation (happy path, edge case, failure mode)

## Creating New Prompts

Use the `/create-prompt` template to generate new prompt templates following the rigorous 8-step methodology.

Example:
```
/create-prompt security-auditor "Review code for security vulnerabilities"
```

## Path and Git Conventions

The permission sandbox blocks operations that escape the project directory. Agents must use relative paths and `cd` to navigate.

- **Never use `git -C <path>`**: This option is blocked because it allows operating on repositories outside the sandbox. Use `cd <relative-path>` and then run git commands normally.
- **Navigate with `cd`**: Change into directories using relative paths before executing commands. This keeps all operations within the sandboxed working directory.
