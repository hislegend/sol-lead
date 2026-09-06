# Astra Lead

A small Codex skill for choosing direct implementation or bounded delegation. Astra can plan, code, debug, and verify. Luna, Terra, and Sol are available workers when delegation earns its setup and integration cost.

Formerly Sol Lead; repository URL remains `hislegend/sol-lead`.

## Choose the outcome you want

| Policy | Default behavior |
|---|---|
| Economy (public default) | Finish small work directly; send worthwhile bounded work to a cheaper capable model |
| Speed | Lead implements the critical path; parallelize independent work only when it can shorten completion |
| Local/user override | Explicit preferences and project rules take precedence |

Examples:

- `$astra-lead economy: implement this feature within my budget.`
- `$astra-lead speed: finish this fix quickly; delegate only useful independent work.`

Economy starting points: Luna low/medium for deterministic work, Terra medium for ordinary bounded implementation, Sol high for complex integration. No forced ladder. Worker roles may pin their own model and effort.

## Install

```bash
git clone https://github.com/hislegend/sol-lead.git astra-lead
mkdir -p ~/.codex/skills
cp -R astra-lead/skills/astra-lead ~/.codex/skills/astra-lead
```

Select GPT-6 Astra for the lead session and start a new session after installation. The skill cannot change the main model.

For an existing installation, back up the old folder outside the scanned skills directory before replacement. Old `skills/sol-lead` links must migrate to `skills/astra-lead`. Legacy wording is recognized, but the current skill identifier is `astra-lead`.

## Operating policy

Ordinary changes use project checks and direct behavior verification without mandatory model-review loops. Material high-risk changes require a fresh capable reviewer before release, unless project rules require stronger checks. Confirmed blockers must be resolved. Nightly checks supplement this gate; they do not replace it.

Parallel implementation uses separate worktrees and feature branches. Role settings can restrict filesystem writes, but external tools require their own permissions. Preserve existing user approvals and repository rules.

Speed and cost benefits are hypotheses until measured. See [measurement guidance](skills/astra-lead/references/token-comparison.md). No benchmark multiplier or guaranteed savings is claimed.

## License

MIT
