## Overview
**Project Riya** is a specialized Fine-Tuned Large Language Model (LLM) designed to speak in natural, conversational **Banarasi Hinglish**. 

- **Profile:** 22-year-old BCA student from Varanasi (Banaras).
- **Tone:** Witty, slightly sarcastic, and friendly.
- **Language:** A natural mix of Hindi and English with local slang (e.g., *'Guru'*, *'Bhaiya'*, *'Mast'*).

This project adapts the powerful **Qwen-2.5 7B** model using a **Multi-Stage Fine-Tuning** pipeline on custom synthetically generated datasets.

## Methodology (The 2-Stage Training)
To achieve high-quality style transfer with limited resources, we employed a specific two-step approach:

### Stage 1: Non-Instruction Fine-Tuning (Continued Pre-training)
* **Objective:** To teach the model the *structure* and *vocabulary* of Hinglish before teaching it how to chat.
* **Data:** A corpus of **45,000+ words** of raw, unstructured Hinglish conversations.
* **Result:** The model learned to mix Hindi and English grammar naturally without breaking the flow.

### Stage 2: Instruction Fine-Tuning (SFT)
* **Objective:** To inject the specific "Riya" persona and manage dialogue flow.
* **Data:** **12,000 high-quality instruction-response samples**.
* **Result:** The model adopted the specific Banarasi tone, sarcasm, and identity of a BCA student.

*> **Note:** All datasets used in this project were synthetically generated and curated using AI assistance to ensure dialect accuracy and consistency.*

---

## Training Statistics
The model was fine-tuned on high-end hardware with the following metrics:

| Metric | Value |
| :--- | :--- |
| **Base Model** | Qwen/Qwen2.5-7B-Instruct |
| **Technique** | QLoRA (4-bit Quantization) |
| **Hardware** | **NVIDIA RTX 5090 (24GB)** |
| **Dataset Source** | Custom AI-Generated Synthetic Data |
| **Dataset Size** | 45k Words (Raw) + 12k Samples (Instruct) |
| **Final Loss** | **0.89** (Converged) |

---

## Model Performance
- **Strengths:** The model has achieved near-perfect **Style Transfer**. It captures the tone, sarcasm, and Hinglish grammar exceptionally well (Low Loss: 0.89).
- **Current Limitations:** Due to the dataset scale, the model occasionally hallucinates regarding **Identity Consistency** (e.g., confusing locations).
- **Future Roadmap:** Scaling the synthetic dataset to **50,000+ samples** will resolve these factual hallucinations and solidify the long-term memory.

---

## Installation & Usage
*Note: The model weights are saved locally. You need the fine-tuned adapter/merged model to run this.*

### Prerequisites
```bash
pip install transformers torch peft bitsandbytes accelerate
