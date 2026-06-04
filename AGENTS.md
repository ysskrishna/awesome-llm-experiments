# Agent guidelines

## Code

- Simple, minimal diffs; match conventions in the experiment folder.
- Naming: `EXPERIMENT_DIR`, `DATA_DIR`, `VECTOR_DB_PATH`, and `vector_db` for the store instance; library names (e.g. Chroma) only in imports and doc links.
- Comments only for non-obvious logic (prefixes, filters, chunking).
- Ingest: put filterable fields in metadata (`lang`, `article`, …).
- Parallel translations: align chunk ids; normalize numeral scripts in ids (e.g. Devanagari → ASCII).
- Model-specific embedding rules in code (e.g. E5 `query:` / `passage:` prefixes).

## Notebooks

- Canonical name: `experiments/<name>/notebook.ipynb`; resolve `EXPERIMENT_DIR` via `notebook.ipynb` when Jupyter cwd is repo root or the experiment folder.
- Beginner-friendly: goals, prerequisites (`uv sync`), run top-to-bottom.
- Sections: setup → ingest → search/demo → wrap-up; **headings state what happens and what to expect**, not labels only.
- Separate **define helpers** from **run ingest** so model load and indexing are obvious.
- Markdown for concepts, code for steps; link RAG, embeddings, vector DB, model card.
- HF embedding models: note first-run download size, cache path (`~/.cache/huggingface/hub/`), and slower first ingest in prerequisites and before the load cell.
- Known-answer demos: assert rank-1 metadata and a corpus snippet—not only filters; document corpus/model-specific limits.
- One small helper per repeated pattern; light checks (`assert`, `value_counts`).

## README

- Keep [README.md](README.md) in sync when adding or materially changing an experiment.

## New experiments

- Under `experiments/<name>/`; reuse `pyproject.toml` deps; extend existing metadata schema.
- Do not commit local indexes (`vector_db/`); Hugging Face hub cache stays on the user machine.
