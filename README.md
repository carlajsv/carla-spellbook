# Carla’s Spellbook ✨

A personal spellbook of reusable AI skills and Codex plugins.

The repository is a catalog, not a single skill. Each installable entry is a Codex plugin, and each plugin can package one or more skills plus optional tools, apps, scripts, or assets.

## Structure

```text
carla-spellbook/
├── .agents/plugins/marketplace.json
├── plugins/
│   └── adhd-friendly-ai/
│       ├── .codex-plugin/plugin.json
│       └── skills/
│           └── adhd-friendly-ai/
│               ├── SKILL.md
│               ├── USER-PREFERENCES.md
│               ├── agents/openai.yaml
│               ├── prompts/
│               └── references/
└── README.md
```

## Available plugins

### ADHD-Friendly AI

An adaptive interaction layer that helps protect focus, externalize conversational memory, reduce unnecessary decision load, and make the next useful action visible.

- Plugin: [`plugins/adhd-friendly-ai`](plugins/adhd-friendly-ai)
- Skill: [`plugins/adhd-friendly-ai/skills/adhd-friendly-ai/SKILL.md`](plugins/adhd-friendly-ai/skills/adhd-friendly-ai/SKILL.md)
- Personal defaults: [`USER-PREFERENCES.md`](plugins/adhd-friendly-ai/skills/adhd-friendly-ai/USER-PREFERENCES.md)
- Universal prompt: [`universal-system-prompt.md`](plugins/adhd-friendly-ai/skills/adhd-friendly-ai/prompts/universal-system-prompt.md)

## Install the marketplace in Codex

Add the GitHub repository as a marketplace once:

```bash
codex plugin marketplace add carlajsv/carla-spellbook --ref main
```

Then install a plugin from the marketplace:

```bash
codex plugin add adhd-friendly-ai@carla-spellbook
```

Start a new task after installing or updating a plugin so Codex loads the current version.

For local marketplace development, register the checkout instead:

```bash
codex plugin marketplace add /absolute/path/to/carla-spellbook
```

## Use the skill outside Codex

Tools that support skill folders can load the directory containing `SKILL.md`. For other AI products, copy the included universal system prompt into custom, project, or system instructions.

## Add future skills

Create each marketplace entry as a plugin:

```text
plugins/<plugin-name>/
├── .codex-plugin/plugin.json
└── skills/
    └── <skill-name>/
        └── SKILL.md
```

Then append the plugin to `.agents/plugins/marketplace.json`. Keep the plugin folder name, manifest `name`, and marketplace entry name identical.

Before publishing, validate both layers:

```bash
python3 /path/to/plugin-creator/scripts/validate_plugin.py plugins/<plugin-name>
python3 /path/to/skill-creator/scripts/quick_validate.py plugins/<plugin-name>/skills/<skill-name>
```

The marketplace entry order determines the order shown in Codex.
