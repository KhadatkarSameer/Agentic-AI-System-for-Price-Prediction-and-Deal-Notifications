# 🧠 Deal Intel: Agentic AI System for Price Prediction and Deal Notifications

An end-to-end **agent-based AI system** that autonomously scans online product deals, predicts accurate prices using an ensemble of intelligent models (including LLMs and ML models), and notifies users about lucrative discounts via messaging services.

---

## 🚀 Features

- 🕵️‍♂️ **Scanner Agent**: Collects live product listings and deal metadata.
- 🧠 **Price Prediction Agents**:
  - **Specialist Agent**: Fine-tuned LLaMA model using QLoRA.
  - **Frontier Agent**: GPT‑based RAG (Retrieval-Augmented Generation) with ChromaDB.
  - **Random Forest Agent**: Lightweight ML-based price estimator.
  - **Gradient Boosting Agent** 🆕: `GradientBoostingRegressor` for more robust regression.
- 🧮 **Ensemble Agent**: Combines predictions using linear regression or weighted averaging.
- 📡 **Planning Agent**: Orchestrates agent flow, deduplication, and scheduling.
- 🔔 **Messaging Agent**: Sends real-time alerts using Pushover or Twilio.
- 🌐 **Gradio UI**: Optional interface for visualization and interaction.

---

## 🏗️ Architecture Overview

```plaintext
            ┌────────────┐
            │  Scanner   │──────┐
            └────────────┘      │
                                ▼
                       ┌────────────────┐
                       │ Planning Agent │
                       └────────────────┘
                                ▼
         ┌──────────────┬─────────────┬──────────────┬
         ▼              ▼             ▼              ▼
    Specialist     Frontier      Random Forest    Gradient Boosting
     (LLaMA)         (GPT‑RAG)        (Sklearn)        (Sklearn)
         └──────────────┴─────────────┴──────────────┴
                                ▼
                         ┌──────────────┐
                         │  Ensemble    │
                         └──────────────┘
                                ▼
                           ┌────────────┐
                           │ Messaging  │───► Pushover
                           └────────────┘
```

---

## 📦 Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/KhadatkarSameer/Agentic-AI-System-for-Price-Prediction-and-Deal-Notifications.git
   cd Agentic-AI-System-for-Price-Prediction-and-Deal-Notifications
   ```

2. **Create conda environment**  
   ```bash
   conda env create -f environment.yml
   ```

3. **Activate the Environment**  
   ```bash
   conda activate llms
   ```

4. **Set environment variables**  
   Create a `.env` file with:
   ```env
   OPENAI_API_KEY=your_key
   PUSHOVER_USER_KEY=your_key
   PUSHOVER_APP_TOKEN=your_token
   CHROMA_DB_PATH=./chroma_db
   ```

---

## 🤖 Usage

Run the full agent pipeline:

```bash
python price_is_right_final.py
```

---

## 🧪 Model Details

| Model               | Description                                 | Library          |
|--------------------|---------------------------------------------|------------------|
| LLaMA              | Fine-tuned using QLoRA                      | Hugging Face     |
| GPT (Frontier)     | GPT-4 (via OpenAI API) + RAG                | OpenAI, ChromaDB |
| Random Forest      | Embedding-based estimator                   | scikit-learn     |
| Gradient Boosting  | `GradientBoostingRegressor` for regression  | scikit-learn     |

---

## 📊 Ensemble Strategy

The **Ensemble Agent** combines predictions from all four models using **Linear Regression** model.

Configure strategy in `ensemble_agent.py`.

---

## 📤 Notifications

Supported providers:
- **Pushover**

Set alert thresholds and frequency in `planner_agent.py`.

---

## 📁 Project Structure

```
├── agents/
│   ├── scanner_agent.py
│   ├── specialist_agent.py
│   ├── frontier_agent.py
│   ├── random_forest_agent.py
│   ├── gradient_boosting_agent.py
│   └── ensemble_agent.py
├── items.py
├── log_utils.py
├── deal_agent_framework.py
├── price_is_right_final.py
├── pricer_service.py
├── testing.py
├── environment.yml
└── README.md
```

---
## 📁 Project Files
[Google Drive Link](https://drive.google.com/drive/folders/1U5jDbqdbwjM2Rf-GmmT_wnB-Hs_cB-QA?usp=drive_link)
---

## 📚 Future Enhancements

- 🧵 WebSocket streaming for live deal updates
- ☁️ Modal or AWS Lambda deployment
- 🧠 Fine-tuned reward models for personalized deal filtering
- 🧩 Vector search optimization for RAG

---

## 👨‍💻 Author

**Sameer Khadatkar**  
GitHub: [@KhadatkarSameer](https://github.com/KhadatkarSameer)
