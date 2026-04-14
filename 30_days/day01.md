# SOC roles and incident lifecycle

## SOC Roles:

| Mission    | Roles             | Tools | Organisation |
|------------|-------------------|-------|--------------|
| Prevention | SOC manager       | SIEM  |              |
| Detection  | SOC Analyst       | UBA   |              |
| Response   | Security Enginner | XDR   |              |
|            |                   | SOAR  |              |

This table maps the main **SOC missions** to the **key roles** and **tools** typically involved in each phase. For prevention, the **SOC manager** uses a **SIEM** to establish visibility, policies, and monitoring foundations before incidents happen. For **detection**, the **SOC analyst** relies on **UBA** to spot abnormal user/entity behavior and identify suspicious activity early. For response, the security engineer uses **XDR** to investigate and contain threats across endpoints and environments, while **SOAR** supports automation and orchestration of repetitive response actions to improve speed and consistency.

The conclude is in the next term **PPT**, which refers to **People, Process, Technology**. All these elements works together for enabling SOC to offers the suitable solutions that we need.

## SOC responsibilities 

### SOC Roles : 
- SOC manager
- SOC analyst 
- Security Engineering 
- Threat hunter
- Vulnerability mananger
- Threat intelligence analyst 
- Incident response nd forensic analyst 

### SIEM Tools :
- LogRthym
- Qradar
- Splunk
- Micosoft Sentinel
- ArcSight

![SIEM TOOLs](/Images/siem-tools.png)

## Incident Response Lifecycle  :

![Incident lifecycle](/Images/incident-lifecycle.png)

The main focus of the discussion is the **Incident Response Life Cycle**—a fundamental process in cybersecurity for managing and mitigating security incidents.

The outlines the incident response life cycle as a **six-step process** and provides detailed explanations for each phase. it also reflects on the quality and delivery of his response in the interview setting, offering suggestions for improvement to make answers more interactive and insightful.

### Key Concepts: Incident Response Life Cycle

| Step Number | Step Name       | Description                                                                                             | Key Actions                                                                                        |
|-------------|-----------------|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| 1           | Preparation     | Foundation of incident response; activities before an incident occurs.                                  | Setting up alerts, triaging and tuning alerts, establishing response procedures                    |
| 2           | Identification  | Detecting and confirming that an incident has occurred.                                                 | Using alerts, anomaly detection tools, or user reports (emails, calls)                             |
| 3           | Containment     | Damage control stage to isolate affected systems and prevent spread to other parts of the organization. | Isolating systems, long-term containment measures like resetting compromised accounts, segregation |
| 4           | Eradication     | Removing the root cause of the incident to clean the environment.                                       | Removing malware, backdoors, fixing misconfigurations                                              |
| 5           | Recovery        | Restoring systems to normal operation while monitoring for reinfection or recurring issues.             | Bringing systems online carefully (e.g., one-by-one), ongoing monitoring                           |
| 6           | Lessons Learned | Analyzing the incident to improve future responses and prevent recurrence.                              | Documenting events, evaluating response effectiveness, updating incident response plans            |

### Detailed Explanation of Each Step

- **Preparation:** This is the groundwork for incident response. It includes all proactive measures such as configuring and fine-tuning alerting systems to quickly detect anomalies or threats. The goal is to be ready to act efficiently when an incident occurs.

- **Identification:** At this stage, the organization confirms an incident’s occurrence. Detection can come from automated alerts, anomaly detection mechanisms in security tools, or through manual reports like user emails and calls.

- **Containment:** After confirming an incident, containment focuses on limiting the damage. The immediate goal is to isolate affected assets to stop the attack from spreading. This can include short-term measures like isolating a compromised machine and long-term strategies such as account resets or network segmentation.

- **Eradication:** Once contained, the root cause (e.g., malware, backdoors, or misconfigurations) is identified and removed. The environment is cleansed to prevent attackers from regaining access.

- **Recovery:** Systems are carefully restored to normal operation. This may be done incrementally to ensure stability and continuous monitoring is essential to detect any signs of reinfection or lingering threats.

- **Lessons Learned:** This critical final step involves a thorough review of the incident and the response. Documentation helps identify what worked and what didn’t, enabling organizations to update their strategies and prevent similar incidents in the future. The life cycle is cyclic, with this step feeding back into preparation.

### Core Insights and Best Practices

- The incident response life cycle is **fundamental to cybersecurity operations** and involves continuous, iterative actions rather than a one-off checklist.
- **Preparation is critical** because it sets the stage for effective detection and response.
- **Identification must be accurate and timely** to avoid delays in containing threats.
- **Containment and eradication are about damage control and cleanup**, ensuring no further harm or repeated attacks occur.
- **Recovery requires careful system restoration and monitoring** to resume normal operations safely.
- The **lessons learned phase drives improvements** in organizational defenses and response procedures, making the cycle a continuous loop.
- In interviews, demonstrating **deep understanding through dialogue and examples** is more compelling than reciting memorized processes.


### Summary Table: Incident Response Life Cycle Overview

| Step            | Purpose                       | Key Activities                                          | Outcome                                 |
|-----------------|-------------------------------|---------------------------------------------------------|-----------------------------------------|
| Preparation     | Ready the organization        | Set alerts, tune systems, establish protocols           | Effective and timely incident detection |
| Identification  | Detect and confirm incidents  | Use tools, alerts, user reports                         | Confirmed incident for response         |
| Containment     | Prevent incident spread       | Isolate systems, reset accounts, segment network        | Minimized damage and isolated threat    |
| Eradication     | Remove root cause and threats | Remove malware, backdoors, fix misconfigurations        | Clean, secure environment               |
| Recovery        | Restore normal operations     | Bring systems online carefully, monitor for reinfection | Business continuity maintained          |
| Lessons Learned | Analyze response and improve  | Document findings, update plans                         | Enhanced future readiness and defenses  |
