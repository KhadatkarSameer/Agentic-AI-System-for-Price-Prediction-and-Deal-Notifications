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
     ┌──────────────┬─────────────┬──────────────┬────────────────────┐
     ▼              ▼             ▼              ▼
Specialist     Frontier      Random Forest    Gradient Boosting
 (LLaMA)         (GPT‑RAG)        (Sklearn)        (Sklearn)
     └──────────────┴─────────────┴──────────────┴────────────────────┘
                        ▼
               ┌──────────────┐
               │  Ensemble    │
               └──────────────┘
                        ▼
                 ┌────────────┐
                 │ Messaging  │───► Pushover
                 └────────────┘
