# A Multi-Task Evaluation of Preverbed Motion Verbs and Spatial Relation Detection

This repository contains code for using OpenAI's **GPT-4** model to perform complex Latin linguistic annotation tasks involving **verb form identification** and **spatial relation detection** in sentences.

> **Note:**  
> While this code is designed for use with OpenAI's GPT-4 API, the logic and structure are basically the same when working with other large language models like **LLaMA** and **Mistral**.  
> For those models, **Google Colab** environments were used, so users should follow the official **Hugging Face** guidelines for model installation and setup.

---

## Tasks

### Verb Identification

Determine whether a given Latin sentence contains a preverbed motion verb.

### Spatial Relation Detection and Classification

Detect the presence of place expressions in sentences associated with motion verbs, classifying them as **Source**, **Goal**, or **Path** relations.

### Spatial Relation Type Disambiguation

Given a sentence and detected spatial relation, identify the exact token expressing the spatial relation and classify it as an **adverb**, **common noun**, or **proper noun**.

---

## Requirements

- Python 3.x
- `openai` Python client library (or the relevant OpenAI client you use)
- `pandas`
- `re` (regular expressions)
