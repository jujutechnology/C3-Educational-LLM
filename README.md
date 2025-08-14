README.md# C3-LLM: An Open-Source Educational AI Coach
### *A Project by For The People Technology*

![Model](https://img.shields.io/badge/Model-Gemma--3--27B-blue)
![License](https://img.shields.io/badge/License-Apache_2.0-green)
[![GGUF Model](https://img.shields.io/badge/🤗%20Hugging%20Face-GGUF%20Repo-yellow)](https://huggingface.co/jujutechnology/gemma-3-27b-c3-finetuned-Q8-GGUF)
[![LoRA Adapter](https://img.shields.io/badge/🤗%20Hugging%20Face-LoRA%20Adapter-orange)](https://huggingface.co/jujutechnology/gemma-3-27b-c3-finetuned)

---

### Our Mission: AI for the Public Good
At **For The People Technology**, we are dedicated to leveraging emerging technologies to address critical challenges in education. We believe in the power of open-source AI to empower communities and create practical, ethical solutions. The **C3-LLM** project is a direct embodiment of this mission, designed to provide a powerful, curriculum-aware AI assistant for K-12 educators and students.

> This project showcases the complete, end-to-end process of fine-tuning a state-of-the-art 27-billion-parameter model for a specialized educational task, culminating in a portable GGUF model that can be run locally.

---

### About the Model
This model is a fine-tuned version of Google's powerful **Gemma-3-27B-IT**. It was trained to act as a "Master Teacher" or "Educational Coach," providing high-quality, pedagogically sound assistance for lesson planning, assessment generation, and student support.

*   **Base Model:** `google/gemma-3-27b-it`
*   **Fine-tuning Dataset:** A curated collection of over 500 high-quality educational dialogues and instructional materials, formatted for conversational fine-tuning.
*   **Fine-tuning Method:** LoRA (Low-Rank Adaptation) using the Unsloth library on an NVIDIA A100 GPU.

---

### 🌟 Model Capabilities: An Example
This model excels at generating detailed, structured, and pedagogically intelligent content.

**Prompt:**
> "What is a list of subjects in scaffolding order, that a 4th grade math student should learn?"

**Example Response Snippet:**
> Okay, here's a list of 4th grade math subjects, presented in a scaffolding order. This means I've tried to arrange them in a way that builds upon prior knowledge and concepts...
>
> **Unit 1: Numbers & Operations – Foundations (4-6 weeks)**
> *   **Place Value (1-2 weeks):**
>     *   Understanding place value to the millions place (1,000,000)
>     *   Expanded form...
>
> **Why this order?** A strong multiplication/division foundation is *essential* for later math. Understanding the relationship between multiplication and division is key...

---

### How to Use This Model

You have two primary ways to use this model, depending on your hardware and technical needs.

#### 1. The GGUF Version (for Local Use on PCs/Macs)
This is the recommended method for most users. The GGUF file is a portable, quantized version of the model that can be run on local machines using tools like **LM Studio**, **Ollama**, or **Jan**.

*   **Repository:** [**jujutechnology/gemma-3-27b-c3-finetuned-Q8-GGUF**](https://huggingface.co/jujutechnology/gemma-3-27b-c3-finetuned-Q8-GGUF)
*   **File to Download:** `model-Q8_0.gguf` (~27 GB)
*   **VRAM Required:** ~28 GB for full GPU acceleration. Can be partially offloaded to system RAM on machines with less VRAM (e.g., 24 GB).

#### 2. The LoRA Adapter (for Developers)
For developers who want to work with the raw adapter, you can load it on top of the base Gemma 3 model in a cloud or local environment with a powerful GPU (40GB+ VRAM recommended).

*   **Repository:** [**jujutechnology/gemma-3-27b-c3-finetuned**](https://huggingface.co/jujutechnology/gemma-3-27b-c3-finetuned)

---

### The Journey: A Case Study in Debugging
The path to this model was a real-world masterclass in debugging the challenges of working with massive LLMs in constrained environments. The key obstacles we navigated included:
*   **Model Format Errors:** Differentiating between trainable models and inference-only formats (`.gguf`).
*   **Software Incompatibility:** Overcoming `KeyError` and `ValueError` due to outdated `transformers` libraries in managed environments.
*   **Hardware Limits:** Hitting GPU VRAM limits (`ValueError: not enough GPU RAM`) and moving from free-tier to A100 GPUs.
*   **Data Handling Errors:** Correcting `AttributeError` and `KeyError` by correctly specifying dataset splits and column names.
*   **Disk Space Limits:** Hitting `RuntimeError: no disk space left` during the model merging process, requiring a multi-session workflow.
*   **Tooling Bugs:** Navigating `TypeError` and `RuntimeError` in the GGUF conversion scripts, ultimately requiring a robust, manual process.

This project is a testament to the persistence required to succeed in modern AI development.

---

### About Us
This project was developed by **For The People Technology**. We are committed to creating safe, open-source AI solutions to empower our communities.

**Learn more at our website: [forthepeople.technology](https://forthepeople.technology)**
