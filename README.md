# Detecting-Sexism-in-Text-Using-Prompt-Based-Language-Models

# 🧠 Sexism Classification with LLMs (Zero-/Few-Shot)

This project explores the use of open-source large language models (LLMs) to classify text as **sexist** or **non-sexist**, focusing on minimizing computational overhead and avoiding reliance on large labeled datasets.

## 🚀 Goal

Develop a lightweight, efficient text classification system that:
- Requires **no fine-tuning**
- Leverages **zero-shot** and **few-shot prompting**
- Uses **quantized models** to run on limited hardware

## 🏗️ Methodology

We evaluated two popular LLMs: **Mistral-7B-Instruct v0.3** and **Qwen2-7B-Instruct**, using the HuggingFace Transformers library. Each model was tested under:

- **Zero-shot prompting**: no training examples provided in the prompt.
- **Few-shot prompting**: 6 labeled examples (3 YES, 3 NO) included in the prompt.

All models were quantized to **4-bit** precision using `BitsAndBytesConfig` to reduce memory and inference time.

### 🧪 Pipeline Overview

1. **Model setup**: Load and quantize models from HuggingFace.
2. **Prompt design**: Format inputs as instruction prompts (with or without examples).
3. **Inference**: Generate outputs and extract binary labels.
4. **Evaluation**: Compute accuracy and confusion matrices.

## 📊 Results

- **Few-shot prompting improved Mistral’s accuracy** significantly (59% → 73%), demonstrating better adaptability with examples.
- **Qwen performed well in zero-shot** (73%) but slightly dropped with few-shot, likely due to prompt sensitivity and pretraining bias.

