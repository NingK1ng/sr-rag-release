---
language:
  - en
license: cc-by-4.0
tags:
  - retrieval-augmented-generation
  - graph-rag
  - sports-medicine
  - evidence-based-medicine
  - benchmark
task_categories:
  - question-answering
size_categories:
  - 1K<n<10K
---

# SR-RAG Benchmark (n = 1,637)

This repository provides the benchmark dataset described in our manuscript:
*From Evidence-Based Medicine to Knowledge Graph: Retrieval-Augmented Generation for Sports Rehabilitation and a Domain Benchmark*.

## Files

- `benchmark_1637.jsonl`: all 1,637 benchmark questions (one JSON object per line).
- `summary_benchmark_full.json`: dataset summary statistics (global + per condition code).
- `meta.json`: lightweight metadata for the merged JSONL.

## JSONL schema (per line)

Per the paper, the public benchmark release contains:
- `question_en`: English clinical question.
- `ground_truth`: exact reference answer (short).
- `nuggets`: atomic fact units used for automated evaluation (grouped by importance).

## Notes

- Evidence window text is not included in this public benchmark. Retrieved evidence is represented by identifiers only, because some source documents are institutionally subscribed.

## License & citation

This dataset is released under CC BY 4.0. Please add the final citation before journal submission.
