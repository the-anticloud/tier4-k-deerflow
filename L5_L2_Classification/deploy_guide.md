# Deploy Guide — K_DEERFLOW
**Tier:** TIER_4_INFERENCE_AGENTS | **Stack:** Python 3.11, asyncio, PAX 27B, KAMELOT_SEARCH, KANTOR_K5, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, asyncio (stdlib), PAX 27B weights, KAMELOT_SEARCH index (must be built first), KANTOR_K5 DB.

## Environment
16GB RAM. GPU for PAX synthesis. KAMELOT_SEARCH index and KANTOR_K5 must be populated.

## AIOSS Integration
```bash
aioss init --module K_DEERFLOW --output ./k_deerflow.aioss
aioss append --chain ./k_deerflow.aioss --payload ./output.bin --module K_DEERFLOW
aioss verify --chain ./k_deerflow.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="K_DEERFLOW",
    aioss_chain="./K_DEERFLOW.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./K_DEERFLOW.aioss --verbose
python -m K_DEERFLOW.tests.smoke
```
