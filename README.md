<h1 align="center">Hi, I'm Ademo</h1>

<p align="center">
  <strong>AI engineer · model compression, RAG, agents.</strong>
  <br>
  I build a small open-source AI stack: <em>quantize → retrieve → reason</em>.
  Three pip-installable libraries, all live on PyPI.
</p>

<p align="center">
  <a href="https://github.com/Ademo93"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-Ademo93-181717?logo=github&logoColor=white"></a>
  <a href="https://pypi.org/user/Ademo93/"><img alt="PyPI" src="https://img.shields.io/badge/PyPI-Ademo93-3775A9?logo=pypi&logoColor=white"></a>
</p>

---

### The stack — three layers, one idea

I'm building a small, readable, fully-open-source AI stack around one
question: **how do we take a large open model, shrink it, serve it locally,
and make it actually reason about your data — without an API key?**

<table>
<tr>
<td width="33%" valign="top">

#### 1. [TurboQuant](https://github.com/Ademo93/turboquant)
**Shrink the model.**
INT4 · INT8 · FP16 · GPTQ · AWQ · BitsAndBytes · structured pruning · ONNX / TensorRT.

```bash
pip install turboquant-ml
```
```python
from turboquant import quantize
qmodel = quantize(model, method="bnb-nf4")
```

[![PyPI](https://img.shields.io/pypi/v/turboquant-ml?label=turboquant-ml)](https://pypi.org/project/turboquant-ml/)
[![Docs](https://img.shields.io/badge/docs-online-blue)](https://Ademo93.github.io/turboquant/)
[![CI](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml)

</td>
<td width="33%" valign="top">

#### 2. [RAGforge](https://github.com/Ademo93/ragforge)
**Retrieve over your docs.**
PDF / Markdown ingestion · Qdrant (embedded) · bge reranking · `context_recall` / `faithfulness` metrics.

```bash
pip install ragforge-ml
```
```python
from ragforge import Pipeline
rag = Pipeline.from_defaults(model_id="...")
rag.ingest(["docs/"])
rag.ask("...")
```

[![PyPI](https://img.shields.io/pypi/v/ragforge-ml?label=ragforge-ml)](https://pypi.org/project/ragforge-ml/)
[![Docs](https://img.shields.io/badge/docs-online-blue)](https://Ademo93.github.io/ragforge/)
[![CI](https://github.com/Ademo93/ragforge/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/ragforge/actions/workflows/ci.yml)

</td>
<td width="33%" valign="top">

#### 3. [AgentForge](https://github.com/Ademo93/agentforge)
**Reason and use tools.**
ReAct loop · calculator · sandboxed Python REPL · web search · SQL · RAG · `tool_accuracy` eval.

```bash
pip install agentforge-ml
```
```python
from agentforge import Agent
agent = Agent.from_defaults(
    model_id="...",
    tools=[Calculator(), RAGTool(rag)],
)
agent.run("...")
```

[![PyPI](https://img.shields.io/pypi/v/agentforge-ml?label=agentforge-ml)](https://pypi.org/project/agentforge-ml/)
[![Docs](https://img.shields.io/badge/docs-online-blue)](https://Ademo93.github.io/agentforge/)
[![CI](https://github.com/Ademo93/agentforge/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/agentforge/actions/workflows/ci.yml)

</td>
</tr>
</table>

The three compose: an `agentforge.Agent` uses an `agentforge.tools.RAGTool`
that wraps a `ragforge.Pipeline`, both running on an `agentforge.llm.QuantizedHFLLM`
that delegates to `turboquant.quantize(method="bnb-nf4")`. **Open models, local
indexes, no API key required.**

---

### Stack

| Area | Tools |
|---|---|
| **Model compression** | PyTorch · BitsAndBytes · GPTQ · AWQ · ONNX · TensorRT |
| **RAG / retrieval** | sentence-transformers · BGE · Qdrant · FastAPI |
| **Agents** | ReAct · tool use · sandboxed exec · SQLite memory |
| **LLMs** | HuggingFace Transformers · Llama · Qwen · Mistral · SmolLM |
| **Tooling** | GitHub Actions · MkDocs Material · pytest · ruff · twine |
| **Languages** | Python (primary) · C / C++ · Lua |

### What I care about

- **Shrinking large open models** so they run on the hardware people actually have.
- **Local-first, no-API-key tooling** — projects you can clone, install, and reproduce in 5 minutes.
- **Measurable** — every change should answer "did it get better?", not "does it run?".
- **Readable algorithms** — each technique is one short module that doubles as a reference for *how* it works.

### Get in touch

Open an issue on any of the three repos — or DM via GitHub.

<!--
README profil pour Ademo93/Ademo93.
Pour activer : crée un repo public nommé exactement "Ademo93",
mets ce fichier en README.md, push. GitHub le détecte automatiquement.
-->
