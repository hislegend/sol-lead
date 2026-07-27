# Token Comparison

Planning example only. Not measured benchmark or price quote. Actual usage depends on repository size, task shape, caching, retries, and runtime accounting.

Assume task consumes 100,000 tokens when Sol performs discovery, implementation, and verification directly.

| Pattern | Sol tokens | Worker tokens | Total tokens | Sol-token change | Main tradeoff |
|---|---:|---:|---:|---:|---|
| Sol works directly | 100,000 | 0 | 100,000 | baseline | Simplest flow; all context stays with Sol |
| Sol lead + Luna high | 20,000 | 85,000 | 105,000 | -80% | Lowest worker tier; may need escalation |
| Sol lead + Terra high | 25,000 | 85,000 | 110,000 | -75% | Strong default for normal features |
| Sol lead + automatic Luna/Terra | 25,000 | 85,000 | 110,000 | -75% | Balanced route for mixed work |
| Sol lead + Terra max after retry | 30,000 | 105,000 | 135,000 | -70% | Retry overhead; use after real failure |

Interpretation:

- Total tokens may rise 5–35% through task packets, summaries, and retries.
- Sol tokens may fall 70–80% when bulk reading and editing stay in disposable worker contexts.
- Token counts alone do not prove monetary savings. Current per-model input, cached-input, and output rates are also required.

Estimate run with:

`cost = sum(model input tokens × input rate + cached tokens × cached rate + output tokens × output rate)`

For fair comparison, hold task boundary, cache state, verification, retry count, and final quality constant. Compare at least three similar tasks.
