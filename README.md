# Customer Support LLaMA 3.2 Fine-Tuning Project  

This repository demonstrates a complete end-to-end machine learning workflow: fine-tuning a large language model (Meta LLaMA 3.2) for a **customer support chatbot use case**, exporting it, and preparing it for local deployment in efficient GGUF format.  

It highlights key applied ML skills:  
- **Data preparation & training** - Jupyter notebook includes the fine-tuning pipeline and experiment setup.  
- **Model adaptation** - Base model adapted for domain-specific customer support conversations.  
- **Deployment readiness** - Model exported to GGUF for efficient inference with [llama.cpp](https://github.com/ggerganov/llama.cpp).  
- **Reproducibility** - Clear usage steps included for local testing and integration.  

---

## Contents  

- **`customer_support_llama_fine_tuning.ipynb`** - Full fine-tuning notebook (data loading, training loop, evaluation).  
- **`llama-3.2-3b-it-ecommerce-chatbot-q4_k_m.gguf`** - Final optimized checkpoint (GGUF format).  
- **`README.md`** - Documentation & usage guide.  

---

## Project Workflow  

1. **Base Model Selection**  
   Started from [`Llama-3.2-3B-Instruct`](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct).  

2. **Fine-Tuning**  
   - Used the Hugging Face `transformers` library.  
   - Trained in a Jupyter environment (Kaggle/Colab compatible).  
   - Domain focus: e-commerce customer support queries.  

3. **Export & Conversion**  
   - Model saved and uploaded to Hugging Face Hub.  
   - Converted to GGUF using [ggml.ai tooling](https://huggingface.co/spaces/ggml-org/gguf-my-repo).  

4. **Deployment**  
   - Optimized for inference with `llama.cpp` (supports Mac, Linux, Windows with GPU acceleration).  
   - Usable via CLI or server modes.  

---

## Running the Model  
The model checkpoint can also be accessed directly on Hugging Face: [CustomerSupportLlama GGUF](https://huggingface.co/josephcawthorne/CustomerSupportLlama)  

### Install llama.cpp  
```bash
brew install llama.cpp   # Mac/Linux
```

### Run via CLI  
```bash
llama-cli --hf-repo Joeschmo4/llama-3.2-3b-it-Ecommerce-ChatBot-Q4_K_M-GGUF   --hf-file llama-3.2-3b-it-ecommerce-chatbot-q4_k_m.gguf   -p "How can I track my order?"
```

### Run via Server  
```bash
llama-server --hf-repo Joeschmo4/llama-3.2-3b-it-Ecommerce-ChatBot-Q4_K_M-GGUF   --hf-file llama-3.2-3b-it-ecommerce-chatbot-q4_k_m.gguf -c 2048
```

