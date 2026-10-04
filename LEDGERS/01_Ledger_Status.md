# Ledger Status

**Project:** `K_DEERFLOW`  
**Tier:** TIER_4_INFERENCE_AGENTS  
**Identity:** Upstream `bytedance/deer-flow` @ `f75d89f39dd1` (MIT)

## Chain state

| Fact | Value |
| --- | --- |
| Upstream | `bytedance/deer-flow` |
| Commit | `f75d89f39dd152873bf2b6486052644a77e830fb` |
| Upstream licence | MIT |
| Licence class | permissive |
| Clone size | 58.77 MB |
| Ledger | 0 blocks, chain verified |
| Current TRL | NOT YET MEASURED |
| Post-optimisation TRL | NOT YET MEASURED |
| II budget cap | 1000.0 IIU |
| Verified upstream edits | 1 |

- Blocks: **0**
- Head digest: `None`
- Chain verification: **verified**

## Independent verification

The chain is verifiable without trusting this project's tooling:

```
anticloud ledger verify
anticloud ledger export > ledger.jsonl
```

Each block carries the previous block's digest, so removing or reordering an
entry invalidates every block after it. That property is the reason the
ledger can stand in for a claim of what happened.
