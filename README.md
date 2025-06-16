# 🦙 Deal Intel: AI-Powered Top 5 Deal Finder

**Deal Intel** is an AI-driven autonomous agent system that scrapes product prices from RSS feeds and identifies the **top 5 best-value deals** using an ensemble of fine-tuned and frontier models. When the right opportunity is found, it sends **real-time push notifications** via [Pushover](https://pushover.net/).

---

## 🔍 Key Features

- **Multimodal Agent Framework** with:
  - 🧠 *Specialist LLaMA 3.1 model* fine-tuned using QLoRA + PEFT.
  - 📚 *RAG-based Frontier Model* for knowledge-enhanced price understanding.
  - 🌲 *Random Forest + XGBoost ensemble*, combined via Linear Regression.
- 📰 *RSS Feed Scraping* to monitor real-time product listings.
- 📈 *Vector Database Visualization* for embeddings & interpretability.
- 📲 *Push Notifications* via Pushover for top 5 deals.
- 🧩 Modular architecture with separate scanning, RAG, pricing, and messaging agents.
- 🖥️ *Gradio UI* for interactive monitoring and analysis.

---

## 🧠 System Architecture

                       +---------------------+
                       |  RSS Feed Scanner   |
                       +---------------------+
      +--------------------------↓-------------------------------------------------------------------+
      |     Price Prediction Ensemble (Specialist Agent + RAG Frontier Model + RF + GB + LR)         |
      +--------------------------↓-------------------------------------------------------------------+
                      +-----------------------+
                      |  Decision + Ranking    |
                      +-----------↓-----------+
                                  ↓
                      +-----------------------+
                      |   Top 5 Deals Output   |
                      +-----------------------+
                                  ↓
                      +-----------------------+
                      |  Push Notification     |
                      |   via Pushover API     |
                      +-----------------------+
