---
name: sol-lead
description: Keep GPT-5.6 Sol as lead for design, coordination, verification, and final judgment while automatically delegating implementation to Luna or Terra with independent effort. Use for coding tasks when the user says sol-lead, Sol 리드, 자동 위임, 토큰 절약 모드, Luna나 Terra로 개발, or asks the lead to choose worker models automatically.
---

# Sol Lead

Keep Sol focused on design, coordination, verification, and final judgment. Delegate implementation and broad repository reading to Luna or Terra workers.

## Runtime rule

- Treat explicit use of this skill as permission to spawn discovery and implementation agents for requested task.
- This skill cannot change main model. Mention it when lead is visibly not Sol.
- Inspect available agent roles and model overrides before routing.
- Use `fork_turns: "none"` for workers. Give each worker self-contained task packet. This keeps lead conversation out of worker context and permits independent effort.

## Automatic routing

Choose smallest worker likely to finish bounded work:

| Work unit | Preferred route |
|---|---|
| Read-only search, file map, symbol discovery | `explorer` (Luna low) |
| Localized fix, boilerplate, tests, pattern-following edit | `lazycodex-worker-low` (Luna high) |
| Standard feature across existing layers, a few files | `lazycodex-worker-medium` (Terra high) |
| Complex multi-file implementation or failed Terra-high attempt | `worker` with `model: "gpt-5.6-terra"`, `reasoning_effort: "max"`, `fork_turns: "none"` |

Keep Sol responsible for architecture, tradeoffs, write-set boundaries, verification choice, and final verdict. Answer-only work stays with lead.

Honor explicit user routing over this table. If requested route unavailable, state substitution and choose closest available route.

## Workflow

1. Read project instructions and record starting working-tree state.
2. Use read-only explorers for broad discovery. Request maps and relevant symbols, not file dumps.
3. Split implementation into bounded work units. Give each worker exclusive file or module ownership. Serialize shared config, schemas, migrations, barrels, and lockfiles.
4. Send each worker:
   - exact goal and observable completion condition;
   - owned files or modules;
   - relevant symbols, constraints, and existing patterns;
   - required focused checks;
   - notice that other agents share worktree, existing edits must remain, and edits outside ownership are forbidden;
   - instruction not to install dependencies, mutate package-manager files, commit, push, deploy, or migrate unless user authorized exact action.
5. Wait for every required result before judging or integrating.
6. Inspect actual status and diff. Check ownership, overlap, preservation of existing user changes, and unexpected files.
7. Run smallest proof covering requested behavior. Lead owns final verdict and manually exercises matching surface when applicable.
8. Report chosen routes, changed surfaces, observed proof, and remaining gaps. Never claim unobserved success.

## Escalation

Escalate implementation failure, incomplete work, or worker-caused verification failure:

`Luna high → Terra high → Terra max`

Inspect partial edits before escalation. Give next worker failure evidence and current working-tree state, not full lead conversation. Stop after Terra max fails and report concrete blocker.

Do not escalate environment failures, destructive approval boundaries, or unclear product decisions.

## Cost discipline

- Optimize expensive Sol-context use, not raw token count alone. Delegation may raise total tokens.
- Avoid duplicate reads and repeated unchanged checks.
- Require concise worker returns: changed files, rationale, proof summary, blockers.
- Read [references/token-comparison.md](references/token-comparison.md) when user asks about token or cost tradeoffs.

## Guardrails

- Worker report never overrides working-tree evidence.
- Follow user and repository rules above this skill.
- External publication or irreversible actions require exact user authorization.
