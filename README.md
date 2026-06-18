<h1 align="center">Hi, I'm Ademo 👋</h1>

<p align="center">
  AI engineer focused on <strong>model compression, quantization & edge deployment</strong>.
  <br>
  Author of <a href="https://github.com/Ademo93/turboquant">TurboQuant</a> — an open-source toolkit for INT4 / INT8 / GPTQ / AWQ.
</p>

<p align="center">
  <a href="https://github.com/Ademo93"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-Ademo93-181717?logo=github"></a>
  <a href="https://Ademo93.github.io/turboquant/"><img alt="Docs" src="https://img.shields.io/badge/docs-turboquant-blue"></a>
</p>

---

### 🚀 Currently building

**[TurboQuant](https://github.com/Ademo93/turboquant)** — Model quantization & optimization toolkit for edge and resource-constrained deployment.
INT4 · INT8 · FP16 · GPTQ · AWQ · BitsAndBytes · Structured pruning · ONNX & TensorRT.

```python
from turboquant import quantize, benchmark
qmodel = quantize(base, method="bnb-nf4")
benchmark.compare(base, qmodel, tokenizer=tok, prompts=[...]).as_table()
```

[![Docs](https://img.shields.io/badge/docs-mkdocs--material-blue)](https://Ademo93.github.io/turboquant/)
[![CI](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml/badge.svg)](https://github.com/Ademo93/turboquant/actions/workflows/ci.yml)

### 🧰 Stack

**ML / AI** &nbsp; PyTorch · Transformers · ONNX · TensorRT · bitsandbytes · GPTQ · AWQ
**Languages** &nbsp; Python · C/C++ · Lua
**Tooling** &nbsp; HuggingFace Hub · GitHub Actions · MkDocs Material · pytest · ruff

### 🎯 What I care about

- Shrinking large open-source models so they run on the hardware people actually have
- Clean, readable algorithm implementations — each compression technique should also be a reference for *how* it works
- Reproducible benchmarks: size, latency, peak memory, perplexity / accuracy

### 📫 Get in touch

Open an issue on [TurboQuant](https://github.com/Ademo93/turboquant/issues) — or DM via GitHub.

<!--
README profil pour Ademo93/Ademo93.
Pour activer : crée un repo public nommé exactement "Ademo93" sur ton compte,
ajoute ce fichier en README.md, push. GitHub le détectera automatiquement
et l'affichera sur ton profil.
-->
