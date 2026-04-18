# Transformer Project

A development environment for Transformer models, embeddings, and LLM integrations. This project leverages [uv](https://github.com/astral-sh/uv) for high-performance dependency management.

## 🚀 Quick Start

### Prerequisites
Ensure you have `uv` installed:
```bash
curl -LsSf https://astral-sh.uv/install.sh | sh
```

### Installation
Sync the environment and install all dependencies:
```bash
uv sync
```

## 🛠 Project Stack
- **Transformers & Tokenizers**: Hugging Face libraries for NLP.
- **LangChain**: Integrations for OpenAI and Google GenAI.
- **MTEB**: Benchmarking for text embeddings.
- **Sentence-Transformers**: Simplified embedding generation.
- **PyTorch**: Deep learning backend.

## ⚠️ Critical Security Notice: CVE-2025-32434

A serious vulnerability exists in `torch.load` for PyTorch versions prior to **v2.6.0**. This vulnerability allows for arbitrary code execution when loading untrusted `.pt` or `.bin` files.

**Action Required:**
The project dependencies have been updated to require `torch >= 2.6.0`. 

If you must work with older checkpoints, ensure you use the `safetensors` format, which is immune to this vulnerability:
```python
from transformers import AutoModel
model = AutoModel.from_pretrained("model_name", use_safetensors=True)
```

