# Matrix-NLU Student-4-v2 — Research Baseline

Status: **RESEARCH BASELINE / NOT PRODUCTION APPROVED**

Source run: `33826815562`
Source commit: `f04b069d8c989d7894d6028367987c2baf79bbfb`
Workflow: `Matrix-NLU Student-4 V2 Checkpoint`
Failure classification: `DEV_GATE_FAILURE` (not training failure)
Frozen status: **FROZEN NOT TOUCHED**

## Preserved checkpoint identity

- Early stop: epoch 6/8
- Best model: epoch 4
- bestDevScore: `0.9590511996891526`
- Parameters: 58,599,411 total; 58,412,544 encoder; 186,867 heads; 4 student layers
- `latest.pt` SHA-256: `c003f19ea4f7e2c0b800a1e2758c07357856a24ed98460b67e1816d09c8ef30d`
- best `model-state.pt` SHA-256: `a4897d74970c6f16db4025d6df2b54e34dd34fbe8976b526976d9fd04e75b20f`

## Last valid metrics

- Epoch 6 train loss: `0.00944543`
- Matrix dev loss: `0.26068120`
- Matrix macro-head accuracy: `0.96818663`
- P0.5 dev loss: `0.36911422`
- P0.5 macro-head accuracy: `0.94871543`

Threshold-zero Matrix dev:
- claim-count exact: `0.997354`
- exact-set: `0.560847`
- claim exact: `0.619342`
- field exact: `0.970736`
- span F1: `0.927804`
- entity F1: `0.982728`
- coverage: `1.0`
- ownership corruption: `0`
- invented World Truth: `0`

Exact-set by language:
- EN: `0.785714`
- ES: `0.547619`
- IT: `0.349206`

Threshold-zero P0.5 dev:
- claim-count exact: `0.983333`
- exact-set: `0.483333`
- claim exact: `0.630952`
- field exact: `0.916667`
- span F1: `0.968394`
- entity F1: `0.972851`
- ownership corruption: `2`
- invented World Truth: `0`

Per-head epoch 6 Matrix:
- claim-kind: `1.0`
- dialogue-act: `0.989712`
- predicate: `0.952675`
- polarity: `0.870370`
- temporal: `0.969136`
- subject/owner/perspective: `1.0`
- target: `0.962963`
- boundary: `0.986904`
- entity: `0.987964`
- negation: `0.873621`
- object: `0.943497`
- subject-token: `1.0`
- temporal-token: `0.985958`

## Artifact identities

- Report artifact ID: `9922954442`; SHA-256 `f28f3d8e0ac33dd7fb84b22f382fc4e7024469f544502456fdd1ea4bae2892e9`
- Bundle artifact ID: `9922957297`; SHA-256 `28af0eb9300f70f9f6f1f8846aadacb87f57a5ad300f6d87570386185714a6ef`
- Resume artifact ID: `9922965503`; SHA-256 `6bb7f268a8c9a2931261dddd2f9566aef16eb3fe71a8684a798c2eb33a4cc02f`
- Training result SHA-256: `d0e046642383182a6e55504171abddba8ac6826396a6888f21a321973d1e82ff`
- Dev error analysis SHA-256: `ae085cf4cfd2c7428920f0c10469cfcda08e735290bd7aa785d6859e4592e716`
- Threshold selection SHA-256: `3dcbdac5f437bf551383a3ac1dae4eadfc761307c76cf24e2dee412b8b268e6b`

GitHub Actions artifacts from the source run expire after 30 days. This document preserves their identities/checksums, not the binary artifacts themselves.

## Known gaps / reason for preservation

Student-4-v2 is retained as the immutable comparison baseline for the next targeted iteration. It learned the broad Matrix structure well but did not satisfy the strict development gate. The main residual areas identified from the development error analysis are structured-output exactness, span decoding, negation, temporal handling, referents/third-party reports, correction/goal/request cases, multilingual robustness (especially Italian exact-set), and ownership safety on P0.5.

Do not lower the canonical production gate merely to promote this checkpoint. Do not evaluate this baseline on frozen data. Future V2.1/V3 work should be compared against this baseline using development-only evidence until the development gate is passed.
