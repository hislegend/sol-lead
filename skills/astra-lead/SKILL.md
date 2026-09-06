---
name: astra-lead
description: Choose direct implementation or bounded delegation under an Astra lead to fit the user's speed, cost, and quality priorities. Use when asked for astra-lead, 아스트라리드, automatic worker routing, or legacy sol-lead. Supports economy and speed policies; explicit user and project preferences take precedence.
---

# Astra Lead

Optimize accepted work, including verification and repair, rather than tokens per call. The lead may design, read, implement, debug, and verify directly. This skill cannot select the main-session model or grant permissions.

## Choose a policy

Respect the user's explicit preference and applicable local guidance first. With no preference, use **economy**. State the policy once; do not add a selection question to every task.

- **Economy:** finish small or tightly coupled tasks directly. Delegate a substantial, bounded unit to a cheaper capable worker only when saved work plausibly exceeds setup, repeated reading, integration, and repair. Use Luna for deterministic narrow work, Terra for ordinary implementation, and Sol for complex integration. Choose the entry tier from evidence; no mandatory model ladder.
- **Speed:** the lead implements the critical path. Delegate independent work only when it plausibly shortens elapsed time or supplies needed independent verification. Continue useful local work while workers run. Do not delegate merely to keep the lead from reading or coding.
- An explicit budget or unavailable model may constrain either policy. Report the constraint; do not promise unmeasured savings or assume API prices match subscription limits.

## When delegation earns its cost

Use workers for independent implementation, a bounded investigation whose source volume or repeated reading would crowd out relevant context, or a targeted independent review. Two independent file sets alone do not prove a speedup: consider task duration, shared contracts, setup, and integration.

Start with targeted search and direct reads. Do not use a universal token threshold such as 150,000; cache behavior, output size, latency, and completeness requirements differ. Keep design and causal judgments with a capable model.

Use only callable models, efforts, and roles. For Codex workers, use fresh context (`fork_turns: "none"` when supported). Suggested starting points, not forced escalation:

| Work | Economy starting point | Speed starting point |
|---|---|---|
| One small repair or tightly coupled change | Lead directly | Lead directly |
| Deterministic bulk transformation with independent expected IDs | Luna low/medium | Lead or Luna if it removes a bottleneck |
| Bounded standard feature | Terra medium | Lead; Sol high for worthwhile parallel work |
| Complex cross-module implementation | Sol high | Lead; capable parallel worker if independent |
| Independent high-risk review | Sol high or another capable reviewer | Astra high or another capable reviewer |

Model IDs when available: `gpt-5.6-luna`, `gpt-5.6-terra`, `gpt-5.6-sol`, `gpt-6-astra`. Runtime role configuration may pin model and effort; inspect it before claiming an override. Keep existing lead effort unless the task or measured results justify changing it.

## Work contract and integration

Honor project planning rules and prior user approvals. Give each worker the objective, acceptance criteria, owned paths, relevant contracts, and focused checks. State existing user changes and prohibited external actions. Parallel implementation uses separate worktrees and feature branches; serialize shared schemas, migrations, config, and lockfiles.

Wait only at dependency boundaries. Inspect the resulting diff, new files, ownership, and preservation of baseline changes. Stop on unattributable out-of-scope edits. Worker claims are not proof.

For exhaustive collection, derive expected IDs independently; compare exact ID sets and mappings, check duplicates and unexpected missing/default values, and inspect stratified samples. Count equality alone does not establish completeness. For media claims, retain source/timecode evidence and report uncertainty or conflicting modalities.

On failure, inspect partial work before retrying. Reuse a session when recovering an already-computed answer. Repeated substantive failure calls for a better spec, another route, or lead repair; do not keep climbing models automatically. Preserve permission boundaries on infrastructure failures.

## Verification and review

Run the required project checks and exercise the changed behavior. Workers run focused checks; avoid unchanged full-suite reruns. Repeat affected checks after repairs and the full gate when the repair changes its scope. A failed or unavailable required check is not a pass.

Ordinary changes need no default external model review unless project or user rules require it. For material changes to authentication/authorization, security, billing/payment, data schemas/migrations/access, deletion, or irreversible sending, use one fresh independent review before merge, deployment, or the irreversible action. Review may run alongside other work but must be resolved before that boundary.

Give the reviewer the diff, original spec, acceptance criteria, and relevant surrounding contracts, not the implementer's self-assessment. Require concrete failure scenarios with file or source evidence. No finding quota; zero findings is valid. Fix confirmed release-blocking defects; assess other findings by actual impact, not labels alone. A lower-severity finding that violates acceptance criteria still needs resolution.

Do not repeat full reviews by ritual. After a repair, rerun affected checks; obtain targeted re-review only for a materially new risk or an unresolved issue requiring independent judgment. If review is unavailable for a required high-risk gate, disclose the gap and obtain an authorized substitute; never silently waive it.

Nightly adversarial tests may reveal later regressions but cannot retroactively prevent data loss, permission exposure, wrong charges, or irreversible sends. They supplement pre-release gates. Do not create scheduled jobs without a request.

## Instructions versus enforcement

Prompts govern task scope and judgment. Role configuration can set model, effort, and `sandbox_mode` when supported; a file marked read-only in prose is not enforced. A read-only filesystem sandbox does not restrict every MCP or remote action. Use scoped credentials, connector permissions, and repository protections for external effects. Do not invent unsupported turn-limit or tool-allowlist fields.

Report result, relevant checks, and material gaps. For cost or speed comparisons, read [measurement guidance](references/token-comparison.md). Do not add benchmarking to routine development unless requested.
