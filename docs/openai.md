# OpenAI-Compatible Provider

[Pi extension](https://github.com/andrewhowdencom/pi.openai) that adds OpenAI-compatible model providers with support for **provider-specific sampling parameters** — such as `repetition_penalty`, `top_k`, `typical_p`, and `mirostat` — that standard OpenAI clients do not expose.

By default the extension registers [Fireworks AI](https://fireworks.ai) as a built-in endpoint, but you can configure any OpenAI-compatible API (Together, Anyscale, self-hosted vLLM, etc.).

## Installation

Install as a Pi package from git:

```bash
pi install github.com/andrewhowdencom/pi.openai
```

## Quick Start (Fireworks)

1. **Set your API key:**

    ```bash
    export FIREWORKS_API_KEY="fw_..."
    ```

2. **Select a model in Pi:**

    ```
    /model fireworks/accounts/fireworks/models/llama-v3p1-405b-instruct
    ```

3. **Send a prompt.** The model streams back a response just like any built-in Pi provider.

4. **Enable repetition penalty** for the current session:

    ```
    /openai set repetition_penalty 1.2
    ```

## Documentation

This documentation is organized following the [Diátaxis](https://diátaxis.fr/) framework. Full documentation will be imported from the [pi.openai repository](https://github.com/andrewhowdencom/pi.openai) once it is published there.

### Tutorials

- [ ] Getting Started with Fireworks AI — *Learn to configure and use the built-in Fireworks endpoint.*
- [ ] Adding a Custom vLLM Endpoint — *Connect Pi to a self-hosted OpenAI-compatible API.*

### How-To Guides

- [ ] Configure Sampling Parameters — *Set `repetition_penalty`, `top_k`, `mirostat`, and other provider-specific parameters.*
- [ ] Use Session Overrides — *Temporarily tweak sampling for the current session with `/openai set`.*
- [ ] Add Custom Models — *Override built-in models or register new ones via `.pi/openai-compatible.yaml`.*

### Reference

- [ ] Configuration Schema — *Complete reference for `settings.json` and `.pi/openai-compatible.yaml` fields.*
- [ ] Slash Commands — *`/openai set`, `/openai reset`, and all subcommands.*
- [ ] Sampling Parameter Reference — *All supported parameters, types, and defaults.*
- [ ] Model Definition Reference — *Fields for custom model registration.*

### Explanation

- [ ] Why Provider-Specific Sampling Matters — *The gap between OpenAI's standard API surface and what modern inference servers expose.*
- [ ] Configuration Layer Precedence — *How hardcoded defaults, global settings, project-local YAML, and session overrides interact.*

## Support

Report issues at [github.com/andrewhowdencom/pi.openai/issues](https://github.com/andrewhowdencom/pi.openai/issues).
