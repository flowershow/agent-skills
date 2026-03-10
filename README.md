# Flowershow Agent Skills

A collection of skills for AI coding agents to use [Flowershow](https://flowershow.app). Skills are packaged instructions and scripts that extend agent capabilities, following the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### site-setup

Set up a Flowershow site's `config.json`: title, navbar, social links, footer, theme, and features.

**Use when:**
- Initializing a new Flowershow site configuration
- Adding or updating navbar links, logo, or social links
- Changing site theme, enabling "Edit this page" links, or configuring footer

## Installation

Add the skills to your project's agent configuration. For Claude Code, add to your `.claude/settings.json`:

```json
{
  "skills": ["../path/to/agent-skills/skills"]
}
```

## Skill Structure

Each skill is a directory containing a `SKILL.md` file:

```
skills/
└── site-setup/
    └── SKILL.md
```

See the [Agent Skills specification](https://agentskills.io/specification) for details on the format.
