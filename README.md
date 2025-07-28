# A Multi-Task Evaluation of Preverbed Motion Verbs and Spatial Relation Detection

This repository contains code for using OpenAI's **GPT-4** model to perform complex Latin linguistic annotation tasks involving **verb form identification** and **spatial relation detection** in sentences.

### Associated Paper:

Farina, A., Ballatore, A., & McGillivray, B. (2025). Mapping Meaning in Latin with Large Language Models: A Multi-Task Evaluation of Preverbed Motion Verbs and Spatial Relation Detection in LLMs.*CLiC-it 2025: Eleventh Italian Conference on Computational Linguistics, September 24 — 26, 2025, Cagliari, Italy*.

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

---
## Usage

Use the notebook: `Code_OpenAI.ipynb`
This notebook performs all three tasks (verb identification, spatial relation classification, and disambiguation) using OpenAI's GPT-4.

### Initialisation
Load the needed packages and add your OpenAI key.

### Load annotated data 
Place your CSV file in the project directory and load it using pandas. Your CSV file should include the following columns:
- `VERB TOKEN`: stores all verb occurrences.
- `goal`, `source`, `path`: include boolean flags for the presence (True) or absence (False) of that spatial relation with a specific verb occurrence.
- `SR_type`: disambiguates the type of spatial relations ('common noun', 'proper noun', 'adverb').

### Generate Prompts
Use the provided prompt generation functions (e.g., `make_prompts`, `make_prompts_3_shot`) to construct prompts in zero-shot, one-shot, or few-shot configurations.

### Run Inference
Send prompts to GPT-4 using the OpenAI API. The model returns:
- All identified verb forms in the sentence (`predicted`)
- Boolean flags for presence of Source, Goal, and Path (`predicted_source`, `predicted_goal`, `predicted_path`)
- The type of spatial relation (`predicted_SR_type`)

> **Note:**  
> To run this code with LLaMA or Mistral, use a Hugging Face-compatible model and modify the notebook to load and query it via Transformers.
> The code is modular: prompt design, GPT querying, and result parsing can be adapted to other languages.
