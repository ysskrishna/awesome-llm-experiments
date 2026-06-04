# Agent guidelines

## Code

- Simple, minimal diffs; match conventions in the experiment folder.
- Naming: `VECTOR_DB_PATH` and `vector_db` for storage and the store instance; library names (e.g. Chroma) only in imports and doc links.
- Comments only for non-obvious logic (prefixes, filters, chunking).

## Notebooks

- Beginner-friendly: goals, prerequisites (`uv sync`), run top-to-bottom.
- Sections: setup → ingest → search/demo → wrap-up; markdown for concepts, code for steps.
- Link key concepts (RAG, embeddings, vector DB, model card).
- One small helper per repeated pattern; show expected outcome and light checks (`assert`, `value_counts`).

## RAG / multilingual

- Put filterable fields in metadata at ingest (`lang`, `article`, …).
- Filter at query time to restrict; omit filter for full / cross-lingual search.
- Align chunk ids across parallel translations; follow model embedding rules (e.g. E5 `query:` / `passage:`).

## New experiments

- Under `experiments/<name>/`; reuse `pyproject.toml` deps; extend existing metadata schema.
- Do not commit local indexes (`vector_db/`, caches).
