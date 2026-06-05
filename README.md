# Awesome LLM Experiments

[![License: MIT](https://img.shields.io/github/license/ysskrishna/awesome-llm-experiments)](https://github.com/ysskrishna/awesome-llm-experiments/blob/main/LICENSE) [![Python](https://img.shields.io/badge/python-3.12+-3776AB?logo=python&logoColor=white)](https://www.python.org/) [![uv](https://img.shields.io/badge/uv-deps-DE5FE9)](https://docs.astral.sh/uv/) [![Jupyter](https://img.shields.io/badge/Jupyter-notebooks-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/) [![LLM](https://img.shields.io/badge/LLM-experiments-0A9396)](https://github.com/ysskrishna/awesome-llm-experiments) [![Author site](https://img.shields.io/badge/author-ysskrishna.space-informational)](https://ysskrishna.space)

Small, runnable notebooks that explore LLM-related patterns (RAG, embeddings, vector search, and more). Shared dependencies via [uv](https://docs.astral.sh/uv/) at the repo root.

## Setup

**Prerequisites**

- Python 3.12+ (see [pyproject.toml](pyproject.toml))
- [uv](https://docs.astral.sh/uv/) for install and run

**Install**

```bash
uv sync
```

Run a notebook from the repo root or the experiment folder (see each experiment’s notebook for `EXPERIMENT_DIR` resolution).

## Experiments

| Experiment | Description | Notebook |
|------------|-------------|----------|
| [multilingual-rag-retrieval](experiments/multilingual-rag-retrieval/) | Bilingual UDHR (English + Hindi): E5 embeddings, Chroma vector DB, optional `lang` filters and cross-lingual search | [notebook.ipynb](experiments/multilingual-rag-retrieval/notebook.ipynb) |
| [multimodal-text-image-vl-embeddings](experiments/multimodal-text-image-vl-embeddings/) | **Colab-only:** cross-modal text+image VL embeddings with Qwen3-VL (Sentence Transformers). Open from GitHub in [Colab](https://colab.research.google.com/), enable **GPU** runtime — not via `uv sync` | [notebook.ipynb](experiments/multimodal-text-image-vl-embeddings/notebook.ipynb) |

## Support

If you find this project helpful:

- ⭐ Star the repository
- 🐛 [Report issues](https://github.com/ysskrishna/awesome-llm-experiments/issues)
- 🔀 Submit pull requests
- 💝 [Sponsor on GitHub](https://github.com/sponsors/ysskrishna)

## License

MIT © [Y. Siva Sai Krishna](https://github.com/ysskrishna) — see [LICENSE](LICENSE) for details.

---

<p align="left">
  <a href="https://github.com/ysskrishna">Author's GitHub</a> •
  <a href="https://linkedin.com/in/ysskrishna">Author's LinkedIn</a> •
  <a href="https://ysskrishna.space">Author's site</a> •
  <a href="https://github.com/ysskrishna/awesome-llm-experiments/issues">Report Issues</a>
</p>
