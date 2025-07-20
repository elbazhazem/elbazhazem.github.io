---

title: "From Alert Fatigue to Smart Triage: Building an LLM-Powered SOC Agent"
date: 2025-07-01
tags: [LLM, SOC, Automation, Cybersecurity]
description: "How we cut Mean‑Time‑To‑Respond by 30 % with a lightweight LLM pipeline."
layout: post
------------

# From Alert Fatigue to Smart Triage: Building an LLM‑Powered SOC Agent

> *“Security teams drown in tens of thousands of alerts every day. What if a lightweight language model could triage them for you in real time?”*

## 1. The Pain: Alert Overload & MTTR

Security Operations Centers (SOCs) rely on SIEM and SOAR tools, but **rule‑based playbooks** often miss context, generating floods of false positives. Analysts spend hours weeding out noise, and **Mean‑Time‑To‑Respond (MTTR)** balloons.

## 2. Our Idea: Context‑Aware Enrichment With LLMs

We fine‑tuned **DistilRoBERTa** using LoRA adapters on a blended corpus of \_CIC‑IDS 2018\_ logs and our synthetic **SOC‑Sim** stream. The agent:

1. **Enriches** each alert with entity context (IP reputation, MITRE ATT\&CK techniques).
2. **Clusters** alerts that share root cause, shrinking queue length.
3. **Prioritises** by assigning a risk score using chain‑of‑thought prompting.

## 3. Architecture

```text
┌──────────┐      ┌────────────┐     ┌─────────────┐
│  Logs    │──►──▶│ Preprocess │──►──▶│ LLM Enrich  │
└──────────┘      └────────────┘     └─────┬───────┘
                                           │  Clusters
                                           ▼
                                     ┌─────────────┐
                                     │  Prioritise │
                                     └─────┬───────┘
                                           ▼
                                     Analyst Dashboard
```

*(A detailed diagram with component icons will be released in the repo’s `/docs`.)*

## 4. Dataset & Training Pipeline

| Dataset      | Records | Label Strategy          | Notes                    |
| ------------ | ------- | ----------------------- | ------------------------ |
| CIC‑IDS 2018 | 2.9 M   | Original attack labels  | Cleaned & deduped        |
| SOC‑Sim      | 1.2 M   | Synthetic MITRE mapping | Covers phish, ransomware |

Training lasted **4 h on a single RTX 4090**. LoRA reduced GPU memory to < 12 GB.

## 5. Early Results

| Metric                      | Rule‑based SOAR | LLM‑SOC‑Agent | Δ      |
| --------------------------- | --------------- | ------------- | ------ |
| MTTR (median)               | 47 min          | **32 min**    | ↓ 32 % |
| False positives             | 18 %            | **11 %**      | ↓ 7 pp |
| Analyst effort (alerts/day) | 1 200           | **820**       | ↓ 31 % |

## 6. What’s Next

* Real‑time Zeek telemetry ingest
* Adversarial robustness testing (IBM ART)
* Feedback loop to fine‑tune on analyst decisions

## 7. Call to Action

* ⭐ **Star** the repo: [https://github.com/ai-soc-automation/LLM-SOC-Agent](https://github.com/ai-soc-automation/LLM-SOC-Agent)
* 🐞 **File issues** or suggest datasets
* 💬 Join the discussion on [LinkedIn](https://www.linkedin.com/in/hazemelbaz).

---

> *This post is part of my ongoing series on **AI‑Driven SOC Automation**. Browse the entire journey on the [AI‑SOC page](/projects/ai-soc-automation/).*
