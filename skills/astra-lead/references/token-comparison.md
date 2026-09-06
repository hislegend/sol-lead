# Measure Accepted Work

Compare direct lead implementation with an economy or parallel route using the same acceptance criteria. Neither cheaper tokens nor fewer lead tokens proves a cheaper or faster accepted result.

Record task ID, starting revision, scope/risk, policy, models/efforts, start and finish, human/queue waiting separately, per-model token use, retries, first-pass gate outcome, integration repairs, and confirmed escaped defects over a stated observation window. Treat API estimates and subscription usage as separate metrics.

Use actual end-to-end elapsed time. Summed child durations double-count overlapping work and are not lead waiting time. Keep timeouts, failed runs, and blocked tasks in the comparison. Edit-call counts are not delivered features. Findings need stable defect identities, deduplication, acceptance, severity, and later outcomes; the same median list length does not establish review quality or convergence.

For API estimates, use the actual provider's rates and cache rules. Separate input, cache reads/writes, and output; handle missing usage explicitly. A child session's average total cost is not a universal fixed setup cost. Context isolation may reduce rereads but may also introduce new prefixes, output, and repairs. Do not transfer a cache-derived token threshold between vendors or models.

For a pilot, match tasks by scope and risk and randomize direct vs delegated runs. Hold effort fixed when testing delegation; hold route fixed when testing effort. Same-task repeats can benefit from familiarity and warm caches: isolate checkouts and counterbalance order. Five tasks per arm gives an initial signal, not proof. Report spread and failures alongside medians.

Choose the faster route only if acceptance and escaped-defect checks remain comparable; choose the cheaper route only after including verification and rework. Preserve an explicit user budget. Unknown model-specific subscription buckets remain unknown.
