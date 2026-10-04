# L5 Narrow / L2 General Classification — K_DEERFLOW
**Platform:** Anticloud | **Tier:** TIER_4_INFERENCE_AGENTS | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
K_DEERFLOW implements a deep research workflow with specialized agents: query planner, KAMELOT_SEARCH retriever, PAX 27B synthesizer, AIOSS auditor, result validator. Narrow scope: Anticloud corpus research only — no web browsing, no external APIs.

## L2 General
L2 General: any tier's complex multi-source question routes through K_DEERFLOW. Clinical staff asking about HIPAA status of TIER_7 projects and robotics engineers asking about ROS2 Nav2 compatibility use the same workflow engine.

## PAX 27B Integration
PAX 27B is the synthesis agent: after retrieval from KAMELOT_SEARCH and KANTOR_K5, PAX synthesizes grounded answers. Each retrieval and synthesis step is individually AIOSS-chained for full workflow auditability.

## AIOSS Audit Chain
Every research workflow (query hash + retrieval plan + synthesis hash + citations hash + confidence) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
NIST AI RMF 1.0 (multi-agent accountability), ISO/IEC 42001 (AI governance).
