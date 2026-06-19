<h1 align="center">Hi, I'm Ademo</h1>

<p align="center">
  <strong>AI engineer · model compression, RAG pipelines, edge deployment.</strong>
  <br>
  I build small, readable, measurable open-source tools — both shipped to PyPI.
</p>

<p align="center">
  <a href="https://github.com/Ademo93"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-Ademo93-181717?logo=github&logoColor=white"></a>
  <a href="https://pypi.org/user/Ademo93/"><img alt="PyPI" src="https://img.shields.io/badge/PyPI-Ademo93-3775A9?logo=pypi&logoColor=white"></a>
</p>

---

### What I'm working on

I'm building a small open-source AI stack around one idea:
**take a large open model → shrink it → serve it locally → measure it.**

Two pip-installable libraries that compose together:

<table>
<tr>
<td width="50%" valign="top">

#### [TurboQuant](https://github.com/Ademo93/turboquant)
**Model quantization & optimization toolkit.**
INT4 · INT8 · FP16 · GPTQ · AWQ · BitsAndBytes · structured pruning · ONNX / TensorRT export.

```bash
pip install turboquant-ml
```
```python
from turboquant import quantize
qmodel = quantize(model, method="bnb-nf4")
```

[![PyPI](https://img.shields.io/pypi/v/turboquant-ml?label=turboquant-ml)](https://pypi.org/project/turboquant-ml/)
[![Docs](https://img.shields.io/badge/docs-mkdocs--material-blue)](https://Ademo93.github.io/turboquant/)
[![CI](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml)

</td>
<td width="50%" valign="top">

#### [RAGforge](https://github.com/Ademo93/ragforge)
**Local-first RAG pipeline with an eval harness.**
PDF / Markdown ingestion · Qdrant retrieval · bge reranking · `context_recall` / `faithfulness` / `answer_relevance` metrics.

```bash
pip install ragforge-ml
```
```python
from ragforge import Pipeline
rag = Pipeline.from_defaults(model_id="Qwen/Qwen2.5-3B-Instruct")
rag.ingest(["docs/"]); rag.ask("...")
```

[![PyPI](https://img.shields.io/pypi/v/ragforge-ml?label=ragforge-ml)](https://pypi.org/project/ragforge-ml/)
[![Docs](https://img.shields.io/badge/docs-mkdocs--material-blue)](https://Ademo93.github.io/ragforge/)
[![CI](https://github.com/Ademo93/ragforge/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/ragforge/actions/workflows/ci.yml)

</td>
</tr>
</table>

The two stack: `ragforge-ml[quantized]` uses `turboquant-ml` to serve any HuggingFace LLM in NF4 / GPTQ / AWQ so the whole RAG fits on a single consumer GPU.

---

### Stack

| Area | Tools |
|---|---|
| **Model compression** | PyTorch · BitsAndBytes · GPTQ · AWQ · ONNX · TensorRT |
| **RAG / retrieval** | sentence-transformers · BGE · Qdrant · FastAPI |
| **LLMs** | HuggingFace Transformers · Llama · Qwen · SmolLM |
| **Tooling** | GitHub Actions · MkDocs Material · pytest · ruff · twine |
| **Languages** | Python (primary) · C / C++ · Lua |

### What I care about

- **Shrinking large open-source models** so they run on the hardware people actually have.
- **Local-first, no-API-key tooling** — projects you can clone, install, and reproduce in 5 minutes.
- **Measurable** — every compression / retrieval change should answer "did it get better?", not "does it run?".
- **Readable algorithms** — each technique is one short module that doubles as a reference for *how* it works.

### Get in touch

Open an issue on [TurboQuant](https://github.com/Ademo93/turboquant/issues) or [RAGforge](https://github.com/Ademo93/ragforge/issues) — or DM via GitHub.

<!--
README profil pour Ademo93/Ademo93.
Pour activer : crée un repo public nommé exactement "Ademo93",
ajoute ce fichier en README.md, push. GitHub le détecte automatiquement.
-->
