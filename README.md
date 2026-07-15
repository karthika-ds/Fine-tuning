# Fine-Tuning Qwen2.5-3B for an AI Astrology Chatbot using LoRA and vLLM

## Project Overview

This project demonstrates the complete workflow of adapting the **Qwen2.5-3B-Instruct** Large Language Model for an AI Astrology Assistant.

The model was fine-tuned using **Parameter-Efficient Fine-Tuning (LoRA)** on a domain-specific astrology conversation dataset and prepared for deployment using **vLLM**, enabling an OpenAI-compatible API.

---

## Project Architecture

```
Dataset
      │
      ▼
Google Colab (GPU)
      │
      ▼
LoRA Fine-Tuning
      │
      ▼
Save Adapter
      │
      ▼
Merge Model (Optional)
      │
      ▼
Ubuntu VPS
      │
      ▼
vLLM Server
      │
      ▼
OpenAI Compatible REST API
```

---

## Technologies Used

| Category | Technology |
|----------|------------|
| Programming | Python |
| LLM | Qwen2.5-3B-Instruct |
| Fine-Tuning | LoRA (PEFT) |
| Framework | Hugging Face Transformers |
| Trainer | TRL SFTTrainer |
| Dataset | JSON Chat Format |
| Environment | Google Colab |
| Deployment | vLLM |
| API | OpenAI Compatible |
| Version Control | Git & GitHub |

---

## Project Structure

```text
├── notebooks/
├── scripts/
├── deployment/
├── report/
├── images/
├── README.md
```

---

## Fine-Tuning Workflow

1. Prepare the dataset.
2. Load the Qwen2.5 model.
3. Apply LoRA.
4. Fine-tune using SFTTrainer.
5. Save the adapter.
6. Test inference.
7. Deploy using vLLM.

---

## Running the Notebook

Install dependencies:

```bash
pip install transformers datasets peft trl accelerate bitsandbytes
```

Open:

```
notebooks/Fine_Tuning_Qwen2_5_Colab.ipynb
```

Run all cells.

---

## Deployment

Install vLLM:

```bash
pip install vllm
```

Run:

```bash
python -m vllm.entrypoints.openai.api_server \
--model /home/ubuntu/Vedaz-Qwen \
--host 0.0.0.0 \
--port 8000
```

Test:

```bash
curl http://localhost:8000/v1/chat/completions
```

---

## Results

- Fine-tuned Qwen2.5-3B-Instruct using LoRA
- Reduced GPU memory usage
- OpenAI-compatible inference using vLLM
- Domain-specific astrology responses

---

## Future Improvements

- Upload the merged model to Hugging Face Hub.
- Containerize deployment with Docker.
- Add FastAPI frontend.
- Deploy behind Nginx with HTTPS.
- Implement model monitoring and logging.

---

## Author

**Karthika M**

Data Science | Machine Learning | Generative AI | NLP

GitHub: https://github.com/karthika-ds

LinkedIn: https://linkedin.com/in/karthika-murugaraj-7b044a257
