---
title: "Before You Build Detection… Make Sure You Have Collection"
subtitle: "Why every SOC should prioritize telemetry and data collection before writing a single detection rule"
description: "A deep dive into the critical role of data collection in SOC operations — why 'no collection, no detection' should guide your entire detection engineering process."
tags: [CyberSecurity, SOC, SIEM, DetectionEngineering, ThreatDetection, MicrosoftSentinel, CloudSecurity]
canonical_url: "https://medium.com/@hazemelbaz/before-you-build-detection-make-sure-you-have-collection"
cover_image: "/assets/collection-vs-detection-banner.png"
date: 2025-11-10
author: "Hazem Elbaz"
---

# Before You Build Detection… Make Sure You Have Collection  

> “There’s no detection without collection.”  
This simple truth is one of the most overlooked principles in modern SOC operations.  

---

## 🧠 Introduction  

In every SOC I’ve seen, teams are eager to start writing *use cases*, mapping them to *MITRE ATT&CK*, creating *SIEM rules*, and claiming, “We’re ready to detect any attack.”  

But too often, they skip the step that makes all of this possible: **data collection**.  

Before your detection rules can work, your SOC must have a solid foundation of telemetry — without it, even the best detection logic will fail silently.  

---

## ⚙️ Collection Comes Before Detection  

A Security Operations Center is an engineered system. The **detection layer** can’t function if the **foundation layer** (Telemetry & Collection) is unstable.  

You can have the most advanced correlation engine in the world, but if your critical systems aren’t generating or forwarding enough logs, your SOC will see nothing.  

Every detection depends on *observable facts* from your **sensors, agents, and integrations**.  
Missing even one essential source — such as Windows Security Event Logs, EDR process telemetry, or DNS traffic — can create massive blind spots.  

This becomes critical during **lateral movement** or **privilege escalation** attempts, where visibility gaps can completely hide attacker activity.  

---

## 🔍 Step One: Log Source Review  

Before writing any detection rules, conduct a **comprehensive log source review** — not a superficial checklist, but a technical validation that answers:  

1. Is the source actually enabled and sending logs to the SIEM?  
2. Are the events complete, or are they truncated?  
3. Do the logs cover all necessary audit categories (authentication, file access, process creation, etc.)?  
4. Are the fields properly parsed and normalized?  

This gives you a **true view of data coverage**, not the assumed one.  
Only then can you safely connect your detection use cases to the log sources that actually support them.  

---

## 🗺️ When There’s No Asset Inventory or Network Diagram  

This is one of the most common challenges for new SOC teams.  
You enter an environment with thousands of devices and servers — but no updated CMDB, and no clear network map.  

In that case, use a **Bottom-Up Visibility Mapping** approach: build visibility from the telemetry you already have.  

Start from your existing logs in the SIEM or EDR and gradually reconstruct the environment:  

1. Identify active devices from endpoint data (`DeviceName`, `Hostname`, or `AgentID`).  
2. Map communication patterns from firewall or proxy logs.  
3. Extract user-to-device associations from Active Directory sign-ins.  
4. Analyze outbound connections to spot systems exposed to the internet.  

By doing this, you build a **real-world inventory** based on evidence — not assumptions — which becomes the backbone of your detection strategy.  

---

## 📡 Are You Collecting the Right Data?  

The more **diverse your telemetry**, the stronger your detection capabilities.  

Examples:  
- **Endpoint logs** → reveal process executions and local activity.  
- **Network telemetry** → exposes lateral movements.  
- **Identity logs** → highlight suspicious access behavior.  
- **Cloud audit logs** → track privileged operations in SaaS or IaaS.  

Regularly review your **schema coverage**:  
Make sure critical fields like `UserPrincipalName`, `DeviceId`, `IPAddress`, and `Timestamp` exist and are normalized.  

Such consistency allows your correlation logic to connect dots accurately — the difference between catching an incident or missing an attack entirely.  

---

## 🧩 Key Takeaways  

- Visibility is the foundation of detection.  
- Build your telemetry coverage before your rules.  
- Review log sources as rigorously as you test detections.  
- Correlate across data types to see the full attack surface.  

> **No Collection, No Detection.**  
> Every SOC’s power begins with what it can see.  

---

## 🔗 Read Next  

If you’re building your own SOC or starting your journey into SIEM and detection engineering, check out:  
👉 [**Microsoft Sentinel Home Lab Setup | Step-by-Step Guide**](https://medium.com/p/microsoft-sentinel-home-lab-setup-step-by-step-guide-c8a2677f34e0?source=social.tw)  
A complete hands-on tutorial to deploy Microsoft Sentinel, connect data sources, and simulate real detections.  

---

## 🏷️ Recommended Tags  

`#CyberSecurity` `#SIEM` `#SOC` `#ThreatDetection` `#SecurityOperations`  
`#MicrosoftSentinel` `#IncidentResponse` `#DetectionEngineering` `#CloudSecurity` `#SOCAnalysis`
