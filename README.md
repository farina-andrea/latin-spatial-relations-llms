# A Multi-Task Evaluation of Preverbed Motion Verbs and Spatial Relation Detection

This repository contains code for using OpenAI's **GPT-4** model to perform complex Latin linguistic annotation tasks involving **verb form identification** and **spatial relation detection** in sentences.

### Associated Paper:

Mapping Meaning in Latin with Large Language Models: A Multi-Task Evaluation of Preverbed Motion Verbs and Spatial Relation Detection in LLMs.
Authors: Andrea Farina<sup>a</sup><sup>1</sup>, Andrea Ballatore<sup>1</sup>, Barbara McGillivray<sup>1</sup>

<sup>a</sup>Corresponding author: andrea.farina[at]kcl.ac.uk; <sup>1</sup>King's College London, London, United Kingdom

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

---
## Usage

Use the notebook: `llm_spatial_relation_tasks.ipynb`
This notebook performs all three tasks (verb identification, spatial relation classification, and disambiguation) using OpenAI's GPT-4.

### Load annotated data
Place your CSV file in the project directory and load it using pandas.

### Generate Prompts
Use the provided prompt generation functions (e.g., `make_prompts`, `make_prompts_3_shot`) to construct prompts in zero-shot, one-shot, or few-shot configurations.

### Run Inference
Send prompts to GPT-4 using the OpenAI API. The model returns:
- All identified verb forms in the sentence
- Boolean flags for presence of Source, Goal, and Path

### Parse and Store Outputs
Model predictions are stored in the DataFrame under new columns:
- `predicted` (full response from GPT)
- `predicted_source`
- `predicted_goal`
- `predicted_path`
