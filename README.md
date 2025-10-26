# ANNA-LIVIA-QNLP
> riverrun, past Bobcat’s parsing, down to qubit again.

**One-sentence**: A small, inspectable demo that maps *Finnegans Wake* sentences to **DisCoCat** string diagrams with **lambeq**, compiles them to parameterised (simulated) circuits, and trains simple classifiers/probes—so we can talk concretely about what “quantum NLP” looks like on literary text before anyone oversells it.

- Notebook: `riverrun2qpu.ipynb`
- Stack: Python 3.10+, `lambeq` (QNLP toolkit), PyTorch, NumPy/Matplotlib  
- Status: **prototype** (classical simulation backend); meant for teaching/methods and small-scale experiments, not performance claims.

---

## Why this exists

Joyce is a stress-test for NLP. This repo shows, in the smallest possible way, how a QNLP pipeline represents sentence structure (via **string diagrams**) and meaning (via **tensor factors / circuits**). The goal is **method clarity**: where diagrams come from, how parameters are trained, and what you can reasonably measure on tiny literary datasets. It’s a scaffold for future experiments, not a leaderboard bid.

---

## What’s inside

- **`riverrun2qpu.ipynb`**  
  Walk-through notebook:
  1) load a few Joyce lines;  
  2) parse → **pregroup types** → **string diagrams** (lambeq);  
  3) choose a simple ansatz → **parameterised circuits**;  
  4) train a tiny classifier/probe on a toy label (e.g., sentence “mood” buckets / handcrafted tags);  
  5) plot losses and a confusion table;  
  6) inspect where the diagram structure helps or fails.

- **`README.md`** (this file) with setup, usage, and caveats.

> lambeq is the QNLP toolkit used here (docs + code). :contentReference[oaicite:1]{index=1}

---

## Install

```bash
# Python 3.10+
python -m venv .venv && source .venv/bin/activate   # or use conda
pip install -U pip wheel
pip install lambeq torch numpy matplotlib
# If lambeq raises backend hints, see its docs for optional extras/backends.

