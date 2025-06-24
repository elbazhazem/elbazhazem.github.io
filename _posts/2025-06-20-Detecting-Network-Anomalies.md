---
title: "Detecting Network Anomalies with XGBoost and SMOTE"
layout: post
date: 2025-06-20
---

### ✍️ **Blog Title:**

**Detecting Network Anomalies with XGBoost and SMOTE: From Cybersecurity Logs to AI Models**

---

### 🧠 **Introduction**

As someone transitioning from a cybersecurity background into AI, I recently challenged myself to turn raw network traffic into intelligent insights. The result? A complete machine learning pipeline that detects DoS (Denial-of-Service) attacks with **99.9%+ accuracy and AUC**, built on top of real-world IoT traffic.

This project marks a key milestone in my journey — transforming my hands-on experience with logs and network security into a practical AI application.

---

### 🔍 **What Problem Are We Solving?**

Traditional intrusion detection systems (IDS) often fail to detect sophisticated or low-rate DoS attacks. Moreover, the volume of network logs and the class imbalance between normal and malicious traffic make this task even harder.

So I asked myself:

> *Can we use modern machine learning to detect anomalies directly from network logs?*

---

### 💾 **Dataset: IoTID20-Extended (2024)**

We used the **IoTID20-Extended dataset**, a recent and comprehensive collection of real IoT network traffic. It includes labeled flows representing normal and various attack types — including DoS and DDoS.

📌 Dataset link: [Kaggle – IoTID20 Dataset](https://www.kaggle.com/datasets/rohulaminlabid/iotid20-dataset)

---

### 🛠️ **Approach Overview**

We designed an end-to-end pipeline with the following stages:

1. **Data Preprocessing**

   * Handle missing values, encode categorical features, scale numerical ones.
2. **Feature Selection**

   * Used `SelectKBest` to extract top predictive features.
3. **Class Balancing**

   * Applied `SMOTE` to synthetically oversample underrepresented attack traffic.
4. **Model Training**

   * Used `XGBoost`, known for performance on tabular datasets.
5. **Evaluation**

   * 10-Fold Cross-Validation using `F1-score` and `ROC-AUC`.

---

### 📈 **Results**

The model achieved:

* ✅ **Accuracy**: 100%
* ✅ **F1 Score**: 1.00
* ✅ **ROC-AUC**: 1.00

> These results are exceptional, but they reflect a balanced, clean dataset. In real-world deployments, we'd expect slightly lower but still strong performance.

📊 Confusion Matrix and ROC Curve plots were also generated (see GitHub).

---

### 💡 **Why This Matters**

This project proves that AI can effectively augment traditional network security — not just by detecting anomalies, but by **learning from raw or semi-structured data** like logs. It's a step toward **AI-driven intrusion detection systems**.

As a cybersecurity expert now stepping into AI, this fusion of domains is exactly where I plan to build next.

---

### 📂 **Try It Yourself**

Full project code, notebook, and results are available on GitHub:

🔗 [GitHub Repo – Log Anomaly Detection](https://github.com/elbazhazem/log-anomaly-detection)

Includes:

* Notebook with all steps
* Visual results
* Cleaned dataset path
* `README.md` + `requirements.txt`

---

### 🚀 **Next Steps**

This is just the beginning. My roadmap includes:

* Applying LLMs to raw `.log` files
* Integrating SHAP/LIME for model explainability
* Deploying real-time log anomaly detectors
* Combining clustering + classification in hybrid models

---

### 👨‍💻 About Me

I’m **Hazem Elbaz**, a cybersecurity researcher shifting toward applied AI and intelligent automation in network defense.

🧭 Follow my journey of building real-world AI from the ground up at:
🔗 [elbazhazem.github.io](https://elbazhazem.github.io)

---

### ❓Question for You

Have you tried using ML or AI in log analysis or cybersecurity? What tools or datasets worked for you?

👇 Let’s discuss in the comments.

