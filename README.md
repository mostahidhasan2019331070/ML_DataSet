Islamic Question‑Answer Dataset

File: questions_cleaned_unique.csvSize: 7,544 rows × 3 columns (id, question, answer)

A lightweight, deduplicated collection of factual question–answer (QA) pairs covering core topics of Islamic studies – from ʿAqīdah and Qurʼānic exegesis to fiqh, ethics, and history.  It can be used to evaluate or fine‑tune large language models (LLMs), power flash‑card apps, or seed conversational chat‑bots.

Table of Contents

Dataset Preview

Column Schema

Quick Start

Use‑Cases

Data Generation & Cleaning

Limitations & Ethics

Contributing

License

Dataset Preview

id

question

answer

1

What is one key aspect of ʿAqīdah (Belief) in Islam?

Belief in the oneness of Allah (Tawḥīd) is a core component of ʿAqīdah.

•••

•••

•••

(Full dataset lives in the CSV.)

Column Schema

Column

Type

Description

id

int

Stable numeric identifier – useful for merges & indexing.

question

string

Natural‑language prompt posed to the model / learner.

answer

string

Ground‑truth response in plain English.

Quick Start

# clone & install (optional virtual‑env)
git clone https://github.com/<user>/<repo>.git
cd <repo>
python -m venv .venv && source .venv/bin/activate
pip install pandas jupyter

# inspect in a notebook
python - <<'PY'
import pandas as pd, textwrap as tw
qa = pd.read_csv('questions_cleaned_unique.csv')
print(f"Rows: {len(qa):,}")
print(qa.sample(3).to_markdown(index=False))
PY

Use‑Cases

1 ‒ LLM Evaluation

Feed the question as a prompt, capture model output, then compare to the reference answer with metrics like exact match, BLEU, ROUGE, or semantic similarity (e.g. OpenAI Embeddings + cosine).

2 ‒ Fine‑Tuning / RAG

The structured QA pairs can seed instruction‑tuning or populate a vector store for retrieval‑augmented generation.  Always keep a held‑out split for unbiased eval.

3 ‒ Learning Apps & Flash‑Cards

The CSV is small enough to load client‑side.  Pair with a spaced‑repetition library to build a quiz app for Islamic studies.

Data Generation & Cleaning

Source aggregation – Compiled from public Qurʼānic verses, authentic ḥadīth, and classical scholarship (public‑domain translations).

Deduplication – Near‑duplicate QAs removed with fuzzy matching (>95 % similarity).

Normalization – Unicode‑normalised (NFC), straight quotes ➝ curly, extra whitespace trimmed.

Manual spot‑checks – Random samples verified for accuracy & orthography.

Note: The dataset is educational and not intended as a substitute for qualified scholarship. Always cross‑check critical religious rulings.

Limitations & Ethics

Scope – Predominantly Sunni perspective; minor schools or contemporary scholarly disagreements may not be fully represented.

Translation nuance – English renderings may simplify Arabic terms.

Hallucination risk – When used to fine‑tune LLMs, biases or gaps in the data can propagate; maintain human review loops.

Contributing

Pull requests are welcome!  Please:

Open an issue to propose additions or corrections.

Ensure new rows are unique and cite reliable sources.

Run scripts/validate.py (coming soon) to pass lint & duplicates check.

License

Released under the Creative Commons Attribution‑ShareAlike 4.0 (CC BY‑SA 4.0) license.  You’re free to copy, remix, and adapt with attribution.

Citation

If you use this dataset in research, please cite:

Mostahid hasan (2025). *Islamic Question‑Answer Dataset* (Version 1.0) [Data set]. GitHub. https://github.com/<user>/<repo>

