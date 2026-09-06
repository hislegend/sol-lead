# Astra Lead

Codex skill for an `Astra lead → Luna / Terra / Sol implementation` workflow. Formerly **Sol Lead**; repository URL remains `hislegend/sol-lead`.

Astra owns planning, architecture, coordination, verification, and final judgment. Workers receive bounded tasks in fresh contexts, with model and effort chosen by the work.

## Routing

| Work | Route |
|---|---|
| Structural search and symbol discovery | Luna low explorer |
| Mechanical work and localized edits | Luna high |
| Standard feature implementation | Terra high |
| Difficult work within a clear design | Terra max |
| Complex features, cross-module integration, difficult bugs | Sol high; xhigh when deeper reasoning is needed |
| Architecture, work allocation, final verdict | Astra lead |

Start at the appropriate tier. Complex work can go straight to Sol. Failure may escalate through `Luna high → Terra high → Terra max → Sol high → Sol xhigh`; repeated failures of the same specification return to Astra for replanning.

Parallel implementation workers use separate worktrees and feature branches. Lead inspects actual changes and verification evidence before integration.

## Install

```bash
git clone https://github.com/hislegend/sol-lead.git astra-lead
mkdir -p ~/.codex/skills
cp -R astra-lead/skills/astra-lead ~/.codex/skills/astra-lead
```

For pull-based updates, link the skill instead of copying it:

```bash
git clone https://github.com/hislegend/sol-lead.git ~/src/astra-lead
mkdir -p ~/.codex/skills
ln -s ~/src/astra-lead/skills/astra-lead ~/.codex/skills/astra-lead
```

For an existing installation, back up the old `sol-lead` folder outside the scanned skills directory before installing `astra-lead`. If the old installation was a symlink, update that installation deliberately; do not overwrite its target. The repository skill path changed from `skills/sol-lead` to `skills/astra-lead`.

Select GPT-6 Astra for the lead session and start a new session after installation. Invoke `$astra-lead`, “아스트라리드”, or “Astra 리드”. Legacy wording “sol-lead” is recognized in the description, but the installed skill identifier is now `astra-lead`.

## Cost and verification

Delegation can add task-packet, review, and retry overhead. Lower total cost or latency is not guaranteed. Measure comparable tasks using per-model input, cached input, output, elapsed time, retries, and verification results. See [comparison guidance](skills/astra-lead/references/token-comparison.md).

The skill cannot change the main-session model or grant permissions. Worker model availability depends on the current runtime. Final verification and acceptance remain Astra's responsibility; repository and user rules govern publication and deployment.

## License

MIT
