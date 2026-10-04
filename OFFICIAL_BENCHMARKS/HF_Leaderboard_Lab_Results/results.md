# HF_Leaderboard_Lab_Results

**Project:** `K_DEERFLOW`  
**Tier:** `TIER_4_INFERENCE_AGENTS`  
**Slug:** `bytedance/deer-flow`  
**Commit:** `f75d89f39dd1`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **53.02 ms** |
| Min latency | 46.03 ms |
| Max latency | 64.99 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **35** |
| Tokenization latency | 0.0 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5872 |
| Classification latency | 74.52 ms |
| Status | **PASS** |

**Input text tokenized:**
```
K_DEERFLOW (bytedance/deer-flow) — 3383 files, 781617 source lines, licence MIT, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'k', '_', 'deer', '##flow', '(', 'byte', '##dance', '/', 'deer', '-', 'flow', ')', '—', '338', '##3', 'files', ',', '78', '##16']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_