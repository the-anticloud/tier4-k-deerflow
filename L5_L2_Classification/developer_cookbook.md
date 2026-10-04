# Developer Cookbook — K_DEERFLOW
**Stack:** Python 3.11, asyncio, PAX 27B, KAMELOT_SEARCH, KANTOR_K5, AIOSS_FORMAT
**Domain:** Multi-agent deep research workflow: agentic synthesis over the Anticloud corpus

## Deep research query
```python
from k_deerflow import DeerFlow

flow = DeerFlow(
    pax_model="./pax-27b-q4.gguf",
    kamelot_index="./kamelot_index/",
    kantor_db="./kantor_k5.db",
    aioss_chain="./deerflow.aioss"
)

import asyncio
result = asyncio.run(flow.research(
    query="Which TIER_7 biosignal projects are HIPAA compliant and what is the evidence?",
    depth="deep", max_sources=20
))
print(result.answer)
print(f"Sources: {len(result.citations)}, Confidence: {result.confidence:.2f}")
```

## Inspect workflow trace
```python
for step in result.trace:
    print(f"[{step.agent}] {step.action}: {step.result_summary}")
# [PLANNER] decompose: 3 sub-queries
# [RETRIEVER] kamelot_search: 12 chunks from TIER_7 docs
# [RETRIEVER] kantor_k5: 8 regulatory facts
# [SYNTHESIZER] pax_27b: 847 tokens
# [VALIDATOR] consistency_check: PASS
```

## Batch research
```python
queries = [
    "TRL levels for all TIER_4 inference projects",
    "Air-gap deployment requirements for TIER_8 RF projects"
]
results = asyncio.run(flow.batch_research(queries))
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
