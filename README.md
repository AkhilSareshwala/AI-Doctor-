# 🩺 AI Doctor — Clinical Reasoning LLM Fine-Tuning

---

## 📌 Overview
AI Doctor is a fine-tuning workflow for a **DeepSeek-R1-Distill-Llama-8B** model, specialized in **clinical reasoning, diagnostics, and treatment planning**.  
It uses:
- **Unsloth** for optimized LLM training
- **LoRA (Low-Rank Adaptation)** for parameter-efficient fine-tuning
- **HuggingFace datasets & trainer**
- **Prompt engineering** for medical reasoning
- **W&B** for experiment tracking

---

## 📜 Workflow Steps

### 1️⃣ Environment Setup
- 📦 Install **Unsloth**, HuggingFace libraries, and `wandb`.
- 🔑 Authenticate HuggingFace & Weights & Biases API tokens.
- ⚡ Verify GPU availability (CUDA).

### 2️⃣ Model Initialization
- 🦙 Load **DeepSeek-R1-Distill-Llama-8B** model.
- ⚙️ Enable **4-bit quantization** for efficiency.
- 📏 Set maximum sequence length to **2048 tokens**.

### 3️⃣ Prompt Engineering
- 🧠 Create **expert medical reasoning prompts** with Chain-of-Thought (CoT) design.
- ✏️ Format input-output examples for both inference and training.

### 4️⃣ Pre-Fine-Tuning Inference
- 🔍 Test baseline model responses using sample medical queries.
- 📊 Compare response quality before fine-tuning.

### 5️⃣ Dataset Preparation
- 📂 Load **FreedomIntelligence/medical-o1-reasoning-SFT** dataset.
- 🏥 Include **stepwise CoT reasoning** in each training prompt.
- 🔄 Map dataset into the expected text format.

### 6️⃣ Fine-Tuning (LoRA)
- 🟦 Apply **LoRA adapters** to attention & projection layers.
- 🛠 Configure training with:
  - Batch size: 2
  - Gradient accumulation: 4
  - Learning rate: 2e-4
  - Steps: 60
- 📈 Track training in Weights & Biases.

### 7️⃣ Post-Fine-Tuning Testing
- 🩺 Run inference with the fine-tuned LoRA model.
- 📌 Compare outputs to baseline for improved reasoning accuracy.

---

## ⚙️ Tech Stack
- **Programming Language:** Python
- **Framework:** PyTorch
- **Libraries:** Unsloth, HuggingFace Transformers, Datasets, TRL, WandB
- **Hardware:** NVIDIA T4 GPU (Colab)

---

## 📊 Results
✅ Improved step-by-step reasoning in medical diagnosis.  
✅ More accurate and context-aware treatment recommendations.  
✅ Reduced hallucination through structured CoT prompts.

