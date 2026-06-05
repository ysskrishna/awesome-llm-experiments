# Agent guidelines

## Code

- Simple, minimal diffs; match conventions in the experiment folder.
- Naming: `EXPERIMENT_DIR`, `DATA_DIR`, and clear constants for data/index paths; use `VECTOR_DB_PATH` and `vector_db` when the experiment persists a local vector index. Library names (e.g. Chroma) only in imports and doc links.
- Comments: generous inline comments so beginners can follow without external docs;
- At ingest, store anything you will filter or display later in document metadata (not only in text).
- Follow each embedding model's documented input format in code (see its model card).

## Notebooks

- Canonical name: `experiments/<name>/notebook.ipynb`; resolve `EXPERIMENT_DIR` via `notebook.ipynb` when Jupyter cwd is repo root or the experiment folder.
- Beginner-friendly: goals, prerequisites (`uv sync`), run top-to-bottom.
- Sections: setup → ingest → search/demo → wrap-up; **headings state what happens and what to expect**, not labels only.
- Separate **define helpers** from **run indexing / ingest** (when applicable) so model load and heavy steps are obvious.
- Markdown for concepts, code for steps; link RAG, embeddings, vector DB, model card.
- HF embedding models: note first-run download size, cache path (`~/.cache/huggingface/hub/`), and slower first run in prerequisites and before the load cell.
- Known-answer demos: assert rank-1 metadata and a corpus snippet—not only filters; document corpus/model-specific limits.
- One small helper per repeated pattern; light checks (`assert`, `value_counts`).

## README

- Keep [README.md](README.md) in sync when adding or materially changing an experiment.
- Per experiment: one-line purpose, path to `notebook.ipynb`, how to run (`uv sync`, jupyter command).

## New experiments

- Under `experiments/<name>/`; reuse `pyproject.toml` deps; match conventions in sibling experiments when relevant.
- Do not commit generated artifacts (local vector indexes such as `vector_db/`, run caches). Hugging Face hub cache stays on the user machine.
