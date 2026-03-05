# Personalized Writing Assistant with LoRA and RAG

![AI Assistant copy](https://github.com/user-attachments/assets/7cef349b-009f-4fff-9568-c9e7656a696d)

An **LLM-based writing assistant that mimics a user’s writing style** by fine-tuning open-source language models using **LoRA (Low-Rank Adaptation)** and enhancing generation with **Retrieval-Augmented Generation (RAG)**.

The system learns stylistic patterns from a user’s writing samples and generates new text that reflects the same tone, structure, and vocabulary. The entire pipeline is designed to run **locally using open-source models and quantization**, allowing users to personalize models with their own data without requiring large-scale compute.

---

## Overview

The system works in three stages:

1. **Dataset Generation**
   - User writing samples are collected.
   - Instruction–response training pairs are generated from those samples using a base LLM.

2. **Parameter-Efficient Fine-Tuning**
   - A pretrained open-source LLM (LLaMA or Mistral) is fine-tuned using **LoRA adapters**.
   - This allows stylistic adaptation with minimal training parameters.

3. **Inference with Retrieval-Augmented Generation**
   - A **RAG pipeline** retrieves relevant user text using embeddings.
   - Retrieved context is injected into prompts to improve stylistic alignment and contextual relevance.

The result is a **personalized writing agent** that produces text closely aligned with a user's tone and linguistic patterns.

---

## Key Features

- **Personalized Text Generation**  
  Generates text in the style of a specific user.

- **Parameter Efficient Training**  
  Uses LoRA adapters to fine-tune models with far fewer trainable parameters.
  - LoRA adapters applied to attention layers
  - Small learning rates and batch sizes

- **Local Training Support**  
  Quantization allows training on consumer GPUs or even high-end local machines.
  - 4-bit model loading
  - Reduced GPU memory usage

- **Retrieval-Augmented Generation (RAG)**  
  Improves contextual accuracy by retrieving similar past text samples.
  - SentenceTransformer embeddings
  - FAISS similarity search
  - Top-k retrieval integrated into prompts

- **Open Source Models**  
  Works with models like:
  - Mistral-7B
  - LLaMA-3-8B
  Embedding model: `all-MiniLM-L6-v2` (SentenceTransformers)

---

## Example Use Cases

- Personalized email drafting
- Social media content generation
- Writing assistants
- Creative writing support
- Marketing copy generation
- Customer service responses

---

## Tech Stack

- Python
- PyTorch
- Hugging Face Transformers
- PEFT (LoRA)
- FAISS
- SentenceTransformers
- Quantization (4-bit)
- Google Colab GPU

---

## Authors

- Shagufta Anjum  
- Trisha Choudhary  

CS 598 – LLMs Post-Pretraining  
University of Illinois Urbana-Champaign
