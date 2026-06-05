# Codex Skills

Personal Codex skills for reuse across machines.

## Skills

### codex-claude-tech-lead

Strict tech-lead workflow for Codex plus Claude Code in large repositories.

Use it when Codex should keep architecture, planning, review, and validation context, while Claude Code performs scoped implementation work.

Key ideas:

- Codex is the tech lead.
- Claude Code is the implementation worker.
- Use repository memory and CodeGraph before broad exploration.
- Delegate with compact Context Capsules.
- Keep Claude Code inside explicit file and symbol boundaries.
- Review evidence with diff, impact analysis, build, and tests.

Skill path:

```text
skills/codex-claude-tech-lead
```

## Install On A New Machine

Run from PowerShell after Codex is installed:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" --repo Gasuo/codex-skills --path skills/codex-claude-tech-lead
```

Restart Codex after installation.

## Update This Repository

After editing the local installed skill, sync it back into this repo:

```powershell
Copy-Item -LiteralPath "$env:USERPROFILE\.codex\skills\codex-claude-tech-lead\SKILL.md" -Destination ".\skills\codex-claude-tech-lead\SKILL.md" -Force
Copy-Item -LiteralPath "$env:USERPROFILE\.codex\skills\codex-claude-tech-lead\agents" -Destination ".\skills\codex-claude-tech-lead\agents" -Recurse -Force
git status --short
git add skills/codex-claude-tech-lead README.md
git commit -m "update codex claude tech lead skill"
git push
```

## Validate

Use the Codex skill validation helper:

```powershell
$env:PYTHONUTF8='1'
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" ".\skills\codex-claude-tech-lead"
```

Expected output:

```text
Skill is valid!
```
