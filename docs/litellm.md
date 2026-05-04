# LiteLLM Provider

[Pi extension](https://github.com/andrewhowdencom/pi.litellm) that adds [LiteLLM](https://docs.litellm.ai/) as a first-class provider with **automatic model discovery**. Point it at your LiteLLM proxy and all configured models appear in Pi's `/model` selector — no manual enumeration required.

## Installation

Install as a Pi package from git:

```bash
pi install git:github.com/andrewhowdencom/pi.litellm
```

Or load temporarily for a single session:

```bash
pi -e git:github.com/andrewhowdencom/pi.litellm
```

## Quick Start

1. Configure your LiteLLM proxy URL in `~/.pi/agent/settings.json`:

    ```json
    {
      "github.com/andrewhowdencom/pi.litellm": {
        "baseUrl": "http://localhost:4000",
        "apiKey": "sk-..."
      }
    }
    ```

2. Start Pi and select a LiteLLM model with `/model`.

3. Search for models prefixed with `litellm/`.

## Documentation

This documentation is organized following the [Diátaxis](https://diátaxis.fr/) framework. Full documentation will be imported from the [pi.litellm repository](https://github.com/andrewhowdencom/pi.litellm) once it is published there.

### Tutorials

- [ ] Getting Started with LiteLLM Proxy — *Learn to connect Pi to a local LiteLLM instance and run your first prompt.*

### How-To Guides

- [ ] Configure Project-Local Overrides — *Set per-project base URLs and model overrides via `.pi/litellm.json`.*
- [ ] Add Custom Model Metadata — *Override discovered model capabilities, context windows, and pricing.*
- [ ] Use the Extension in Print Mode — *Run one-shot prompts via `--provider litellm --model <id>`.*

### Reference

- [ ] Configuration Schema — *Complete reference for `settings.json` and `.pi/litellm.json` fields.*
- [ ] Model Discovery API — *How the extension queries `/model/info` and `/v1/models`, and what defaults apply.*
- [ ] Override Field Reference — *All available fields in `modelOverrides` and their types.*

### Explanation

- [ ] How Autodiscovery Works — *The two-phase discovery process, fallback defaults, and heuristic model classification.*
- [ ] Cost and Context Window Defaults — *Why defaults are chosen and when to override them.*

## Support

Report issues at [github.com/andrewhowdencom/pi.litellm/issues](https://github.com/andrewhowdencom/pi.litellm/issues).
