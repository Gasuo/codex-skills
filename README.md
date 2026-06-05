# Codex Skills / Codex 技能库

Personal Codex skills for reuse across machines.

个人 Codex 技能库，用于在多台电脑之间同步和复用自定义技能。

## Skills / 技能列表

### codex-claude-tech-lead

Strict tech-lead workflow for Codex plus Claude Code in large repositories.

面向大型代码仓库的 Codex + Claude Code 技术负责人工作流。

Use it when Codex should keep architecture, planning, review, and validation context, while Claude Code performs scoped implementation work.

适用于以下场景：Codex 负责架构判断、任务规划、上下文保护、代码复审和验证；Claude Code 只负责受控范围内的代码修改和新增。

Key ideas:

核心理念：

- Codex is the tech lead.
- Codex 是主程序员 / 技术负责人。
- Claude Code is the implementation worker.
- Claude Code 是受控实现者 / 码农。
- Use repository memory and CodeGraph before broad exploration.
- 在大范围探索前，优先使用仓库记忆和 CodeGraph。
- Delegate with compact Context Capsules.
- 使用紧凑的 Context Capsule 派工。
- Keep Claude Code inside explicit file and symbol boundaries.
- 用明确的文件和符号边界限制 Claude Code。
- Review evidence with diff, impact analysis, build, and tests.
- Codex 通过 diff、影响分析、构建和测试来复审结果。

Skill path:

技能路径：

```text
skills/codex-claude-tech-lead
```

## Install On A New Machine / 新电脑安装

Run from PowerShell after Codex is installed:

安装 Codex 后，在 PowerShell 中运行：

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" --repo Gasuo/codex-skills --path skills/codex-claude-tech-lead
```

Restart Codex after installation.

安装完成后重启 Codex。

## Update This Repository / 更新此仓库

After editing the local installed skill, sync it back into this repo:

本地已安装 skill 修改完成后，可以同步回此仓库：

```powershell
Copy-Item -LiteralPath "$env:USERPROFILE\.codex\skills\codex-claude-tech-lead\SKILL.md" -Destination ".\skills\codex-claude-tech-lead\SKILL.md" -Force
Copy-Item -LiteralPath "$env:USERPROFILE\.codex\skills\codex-claude-tech-lead\agents" -Destination ".\skills\codex-claude-tech-lead\agents" -Recurse -Force
git status --short
git add skills/codex-claude-tech-lead README.md
git commit -m "update codex claude tech lead skill"
git push
```

## Validate / 校验

Use the Codex skill validation helper:

使用 Codex skill 校验工具：

```powershell
$env:PYTHONUTF8='1'
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" ".\skills\codex-claude-tech-lead"
```

Expected output:

预期输出：

```text
Skill is valid!
```
