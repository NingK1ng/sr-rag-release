---
language:
  - en
license: cc-by-4.0
tags:
  - knowledge-graph
  - graph-rag
  - sports-medicine
  - evidence-based-medicine
task_categories:
  - graph-ml
size_categories:
  - 100K<n<1M
---

# SR-RAG Knowledge Graph

This repository provides the knowledge graph described in our manuscript:
*From Evidence-Based Medicine to Knowledge Graph: Retrieval-Augmented Generation for Sports Rehabilitation and a Domain Benchmark*.

The original graph was constructed with the Youtu-GraphRAG pipeline and exported from NetworkX.

## Files

- `nodes.jsonl.gz`: node table (one JSON object per line).
- `edges.jsonl.gz`: edge table (one JSON object per line).
- `meta.json`: counts and top relation/type statistics.

## Node schema (`nodes.jsonl.gz`)

Each line includes:
- `id`: node id (string, e.g., `entity_123` / `attr_456`).
- `label`: high-level node label (`entity` or `attribute`).
- `level`: hierarchy level (integer).
- `name`: node surface name.
- `chunk_id`: provenance identifier used during graph construction.
- `schema_type`: fine-grained type (e.g., `population`, `intervention`, `outcome`, ...).

## Edge schema (`edges.jsonl.gz`)

Each line includes:
- `source`: source node id.
- `target`: target node id.
- `key`: edge key (integer; NetworkX `MultiDiGraph`).
- `relation`: relation type (string).

## Quick load example

```python
import gzip, json

with gzip.open("nodes.jsonl.gz", "rt", encoding="utf-8") as f:
    first_node = json.loads(next(f))

with gzip.open("edges.jsonl.gz", "rt", encoding="utf-8") as f:
    first_edge = json.loads(next(f))

print(first_node)
print(first_edge)
```

## License & citation

TBD by the authors. Please fill in the license and citation before making the dataset public.
