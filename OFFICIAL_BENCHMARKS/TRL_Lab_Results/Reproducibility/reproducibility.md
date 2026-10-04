# Reproducibility Record: TRL_Lab_Results

**Project:** `K_DEERFLOW`  
**Benchmark:** `TRL_Lab_Results`  
**Run:** `2026-09-30T15:11:19.033679+00:00`  
**Based on:** [HELM reproducibility principles](https://github.com/stanford-crfm/helm)

## Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| OS | `nt` |

## Inputs

| Field | Value |
| ----- | ----- |
| Slug | `bytedance/deer-flow` |
| Commit | `f75d89f39dd1` |
| Tracked files | `3383` |
| Source lines | `781617` |
| Licence | `MIT` |
| Inputs SHA256 | `f80f417a5e5c842c...` |

## Outputs

| Field | Value |
| ----- | ----- |
| Results file | `TIER_4_INFERENCE_AGENTS\K_DEERFLOW\OFFICIAL_BENCHMARKS\TRL_Lab_Results\results.json` |
| Results SHA256 | `64dbe63ba0be6690...` |

## Reproduction Steps

- 1. Clone Anticloud at commit HEAD
- 2. Ensure E:\fenta\Downloads\The Anticloud is present
- 3. Run: python run_benchmarks_comprehensive.py
- 4. Run: python write_benchmark_subfolders.py
- 5. Run: python write_ledgers_repro_extra_benchmarks.py
- 6. Verify results_sha256 matches sha256(OFFICIAL_BENCHMARKS/TRL_Lab_Results/results.json)

## Notes

TRL/OSINT/OWASP/SOC2/ISO27001/MITRE/NIST use static code analysis. HF uses live CPU inference.

---
_Anticloud Reproducibility Standard v1 — 2026-09-30T15:11:19.033679+00:00_