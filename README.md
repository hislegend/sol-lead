# sol-lead

Codex skill for a `Sol lead → Luna/Terra implementation` workflow.

Sol keeps architecture, coordination, verification, and final judgment. Implementation and broad repository reading move to lower-cost worker contexts. Worker model and effort are selected automatically by task size.

## Routing

| Work | Route |
|---|---|
| Read-only discovery | Luna low |
| Localized edits and pattern work | Luna high |
| Standard features across a few files | Terra high |
| Complex implementation or escalation | Terra max |
| Design and final verdict | Sol lead |

Failed implementation escalates:

`Luna high → Terra high → Terra max`

## Install

### Clone and copy

```bash
git clone https://github.com/hislegend/sol-lead.git
mkdir -p ~/.codex/skills
cp -R sol-lead/skills/sol-lead ~/.codex/skills/sol-lead
```

### Clone and link

Use a symbolic link when you want `git pull` updates to apply immediately:

```bash
git clone https://github.com/hislegend/sol-lead.git ~/src/sol-lead
mkdir -p ~/.codex/skills
ln -s ~/src/sol-lead/skills/sol-lead ~/.codex/skills/sol-lead
```

Restart Codex after installation. Invoke with `$sol-lead`, or ask for “Sol 리드”, “자동 위임”, or “토큰 절약 모드”.

## Token comparison

Illustrative 100,000-token baseline:

| Pattern | Sol tokens | Total tokens |
|---|---:|---:|
| Sol works directly | 100,000 | 100,000 |
| Sol lead + Luna high | 20,000 | 105,000 |
| Sol lead + Terra high | 25,000 | 110,000 |
| Automatic Luna/Terra routing | 25,000 | 110,000 |

Delegation may raise total tokens through task packets and summaries. Goal: reduce expensive Sol-context usage, not guarantee lower raw token count. See [token comparison notes](skills/sol-lead/references/token-comparison.md).

## Limits

- Skill cannot change main-session model. Select Sol in Codex.
- Available worker roles and model overrides depend on current Codex runtime.
- Final verification remains lead responsibility.
- Push, deployment, migration, dependency changes, and irreversible actions still follow user and repository rules.

## License

MIT
