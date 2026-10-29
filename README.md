# Overly Complex Skill

Keep coding tasks from growing through speculative robustness.

A cross-harness skill for Codex, Claude Code, and other Agent Skills-compatible tools. The skill is in [`overly-complex/`](./overly-complex/SKILL.md).

Before adding complexity for an unlikely race condition or security edge case, explain the concrete failure mode, likelihood, and complexity cost, and get the user's buy-in. The skill keeps the highlighted instruction from the [source image](https://pbs.twimg.com/media/HVQsdjnXUAAmjMf?format=jpg&name=large) verbatim.

## Explicit Invocation Only

This skill runs only when you explicitly invoke it. Codex uses `policy.allow_implicit_invocation: false` in `agents/openai.yaml`; Claude Code uses `disable-model-invocation: true` in the skill frontmatter. Other harnesses must support an equivalent policy to enforce this behavior.

## Install With skills.sh

If the repository is private, authenticate to GitHub with an account that can read it before installing.

```bash
npx skills@latest add ekeric13/overly-complex-skill
```

## Install For Codex

From a local clone:

```bash
mkdir -p ~/.codex/skills/overly-complex
rsync -a overly-complex/ ~/.codex/skills/overly-complex/
```

Start a new session and invoke it:

```text
Use $overly-complex while implementing this change. Explain the failure mode, likelihood, and complexity cost before adding speculative robustness, and get my buy-in.
```

## Install For Claude Code As A Plugin

```text
/plugin marketplace add https://github.com/ekeric13/overly-complex-skill
/plugin install overly-complex@overly-complex
```

Invoke the namespaced skill with `/overly-complex:overly-complex`.

## Install For Claude Code As A Personal Skill

```bash
mkdir -p ~/.claude/skills/overly-complex
rsync -a overly-complex/ ~/.claude/skills/overly-complex/
```

Then use `/overly-complex`.

## Verify The Skill

With Python and PyYAML installed:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py ./overly-complex
```
