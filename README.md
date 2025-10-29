# mallowsPO
Mallows' theory of preference ranking + DPO notebook (https://arxiv.org/abs/2405.14953)
It implements:

DPO (Direct Preference Optimization) and MallowsPO variants (θ and ϕ),

an entropy-based dispersion estimator consistent with the MallowsPO paper,

sequence-level log-prob computation for causal LMs,

a lightweight MallowsPOTrainer for fine-tuning on pairwise preference data,

Features

Unified notebook containing configuration, utilities, losses, dataset, trainer, and examples.

Losses: DPO, MallowsPO-θ (neg-log dispersion scaling), MallowsPO-ϕ (gϕ link).

Dispersion estimator: entropy-based proxy computed from model logits (practical implementation of the paper heuristic).

Trainer: easy to use — loads model(s), computes sequence log-probs, computes losses, and performs training + checkpointing.

Dataset: PreferencePairsDataset expects JSONL or in-memory list of pairs: {'prompt':..., 'winner':..., 'loser':...}.

Files in this project

- MallowsPO_unified_notebook.ipynb(1) — single notebook with all code cells (main deliverable).
- README.md — this file.

Quickstart — Run the notebook

Open the notebook MallowsPO_unified_notebook.ipynb(1) in JupyterLab / notebook environment.

If packages are missing, run the installation cell (uncomment the pip install lines).

Edit the example config cell to point to the model you want (e.g. gpt2, a finetuned local model, or a larger SFT model path).

Prepare a small JSONL dataset or an in-memory list with pairwise preference examples:

{"prompt":"Translate to French: Hello", "winner":"Bonjour", "loser":"Salut test"}


Run the training example cell. For quick tests, use gpt2 and small batch sizes.
