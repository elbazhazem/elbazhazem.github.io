---
title: "Building a SOC Home Lab from Zero — Catching Real Attackers on Azure"
date: 2025-10-05
description: "A hands-on journey into building a functional Security Operations Center (SOC) using free Azure resources and Microsoft Sentinel — from honeypot setup to live attack visualization."
tags: ["Cybersecurity", "SOC", "Microsoft Sentinel", "Azure", "SIEM", "Practical Labs"]
image: "/assets/images/soc-home-lab-banner.png"
---

# 🧠 Building a SOC Home Lab from Zero — Catching Real Attackers on Azure

> *“Every attack is a lesson — the key is building systems that learn faster than attackers do.”*  
> — **Dr. Hazem A. Elbaz**

---

## 🚀 Introduction

In this post, I’ll walk you through one of my most exciting hands-on projects — building a **Security Operations Center (SOC) from scratch** using **Microsoft Azure’s free tier** and **Microsoft Sentinel**.  
This project is not just theoretical; it captures **real-world cyberattacks** and transforms them into **actionable intelligence** through dashboards and live maps.

Whether you’re a **cybersecurity student**, **SOC analyst**, or **researcher**, this lab is an ideal starting point to explore how professional SOC environments detect, collect, and analyze threats in real time.

---

## 🏗️ Why I Built This Project

After years of teaching and researching cybersecurity, I wanted to design a lab that:
- **Bridges theory and reality** — by exposing a honeypot to actual attackers.
- **Empowers learners** — to build and observe a functioning SOC environment.
- **Showcases portfolio-ready skills** — for anyone pursuing a cybersecurity career.

By using Azure’s free resources, anyone can replicate this setup safely and affordably.

---

## 🔍 Project Overview

Here’s what the home SOC includes:

| Component | Description |
|------------|-------------|
| **Azure Subscription (Free Tier)** | Deploys all resources at zero cost. |
| **Honeypot VM** | A Windows 10 machine deliberately exposed to attackers. |
| **Log Analytics Workspace (LAW)** | Centralized log storage and analysis engine. |
| **Microsoft Sentinel** | SIEM platform for correlation, alerting, and visualization. |
| **Live Attack Map** | Displays attack origins in real time. |

---

## ⚙️ Step-by-Step Highlights

### 1️⃣ Setting up Azure
Create a free Azure subscription and configure:
- Resource Group  
- Virtual Network (VNet)  
- Virtual Machine (Windows 10 Honeypot)

### 2️⃣ Deploying the Honeypot
Expose the VM intentionally:
- Delete RDP security rules.
- Allow all inbound traffic.
- Disable Windows Firewall to attract attacks.

⚠️ *This should be done only in an isolated lab environment.*

### 3️⃣ Observing Attacks
Within minutes, automated bots start brute-forcing your VM.

Monitor **Event ID 4625 (Failed Login)** using Windows Event Viewer:
- Username attempted
- IP address
- Failure reason

### 4️⃣ Integrating with Sentinel
Use the **Azure Monitor Agent** to forward logs to **Log Analytics Workspace**.  
Then, connect Sentinel to the workspace for correlation and visualization.

Sample KQL Query:
```kql
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Account, IpAddress = tostring(parse_json(AdditionalFields)["IpAddress"])
| sort by TimeGenerated desc
````

### 5️⃣ Enriching Data with GeoIP

Import `geoip-summarized.csv` as a **Sentinel Watchlist** to map attacks to their geographic origins.

### 6️⃣ Visualizing Attacks

Create a custom Sentinel **Workbook** using `map.json` to generate a **live global attack map**.
You’ll see where attackers are coming from — in real time.

---

## 📊 Results and Insights

Within hours of exposure, the honeypot began receiving:

* Hundreds of **failed login attempts**.
* Attack sources from **over 50 countries**.
* Common usernames like `admin`, `test`, and `employee`.

These logs reflect the **global nature of cyber threats** and demonstrate how SOCs continuously analyze suspicious activities to safeguard systems.

---

## 🧠 Lessons Learned

* **Attack simulation** is a powerful learning tool.
* Understanding **Event ID 4625** is essential for brute-force detection.
* **KQL** is a must-know language for any SOC analyst.
* Visual dashboards turn complex data into clear stories for decision-makers.

---

## 🧩 Next Steps

Future enhancements:

* Integrate **Sysmon** for deeper telemetry.
* Automate alerts with **Logic Apps**.
* Extend to **multi-cloud monitoring** (AWS / GCP).
* Apply **AI models or LLMs** to summarize log anomalies.

---

## 📖 Full Documentation

All setup instructions, queries, and diagrams are available in the public repository:
👉 [**GitHub: SOC Home Lab from Zero**](https://github.com/elbazhazem/SOC-Home-Lab-from-ZERO)

For a detailed tutorial and reflections, read the Medium article:
👉 [**Building a SOC Home Lab from Zero — Catching Real Attackers on Azure**](https://medium.com/@hazemelbaz/soc-home-lab-from-zero-catching-attackers) *(replace with your final post URL)*

---

## 🌐 About the Author

**Dr. Hazem A. Elbaz**
Assistant Professor of Cybersecurity | SOC Automation Researcher | AI-SOC Founder
[Website](https://elbazhazem.github.io) • [LinkedIn](https://www.linkedin.com/in/hazem-elbaz) • [GitHub](https://github.com/elbazhazem)

---

*If this project inspired you, share it or tag me on LinkedIn — let’s keep building secure, intelligent systems together.*

```

---

Would you like me to:
1. Create a **ready-to-upload Markdown file** (`soc-home-lab-post.md`) for your website’s `/archive/` directory, or  
2. Adjust it to match your site’s **Jekyll theme layout** (with front-matter fields aligned to your current blog style)?
```
