# Biomedical Named Entity Recognition using BioBERT

This project implements Biomedical Named Entity Recognition (NER) using BioBERT on the BC5CDR dataset.

The objective is to compare Full Fine-Tuning (FFT) with Parameter-Efficient Fine-Tuning (PEFT) methods such as LoRA and Prompt Tuning, and evaluate their performance on chemical and disease entity extraction.

# Dataset

We use the BC5CDR dataset (loaded via tner/bc5cdr from Hugging Face).

The dataset contains PubMed abstracts annotated with:

- B-Chemical
- I-Chemical
- B-Disease
- I-Disease
- O (Outside entity)

# Task

- Token-level classification (BIO tagging format)

# Model

Base model used:

- DMIS Lab BioBERT-base-cased-v1.1
- 110M parameters
- Pre-trained on biomedical corpora (PubMed)

# Methods Implemented

Baseline Model

- Pretrained BioBERT without dataset-specific fine-tuning

Prompt tuning

- Tuned prompts based on the usecase
- Backbone frozen
- Trainable soft prompts added

LoRA (Low-Rank Adaptation)

- Parameter-efficient fine-tuning
- Only small low-rank matrices trained

# Results Summary
Method	Performance	Efficiency
Baseline	Very Low	High
Prompt Tuning	Moderate	Very High
LoRA	High	High
Full Fine-Tuning	Highest	Low

# Key finding:

LoRA achieves near full fine-tuning performance while training significantly fewer parameters.
