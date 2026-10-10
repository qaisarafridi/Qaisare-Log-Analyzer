# 🛡️ QAISARE EVENT LOG ANALYZER## 🖥️ Application Screenshots

### 1. Main Dashboard

![QAISARE Event Log Analyzer Dashboard](https://github.com/qaisarafridi/Qaisare-Log-Analyzer/blob/main/aaa.png)

### 2. Application Startup Screen

![QAISARE Event Log Analyzer Startup Screen](https://github.com/qaisarafridi/Qaisare-Log-Analyzer/blob/main/aaaa.png)


**AI-Powered Windows Event Log Forensics, SIEM Correlation & Digital Forensics and Incident Response (DFIR)**

**Version:** 1.0.0
**Developer:** Qaisare
**Platform:** Windows
**Technology:** C# / .NET
**License:** Specify your chosen license

QAISARE EVENT LOG ANALYZER is a Windows-focused security investigation platform designed to help security analysts investigate event logs, correlate suspicious activity, identify potential indicators of compromise (IOCs), and generate structured forensic reports.

The platform combines deterministic forensic analysis, AI-assisted investigation, Windows event decoding, real-time event monitoring, Sigma rule testing, and evidence-integrity verification in a unified workflow.

> **Project objective:** Transform raw Windows event data into structured, explainable, and actionable security investigation findings.

---

## ✨ Key Features

### 📥 1. Multi-Source Event Log Ingestion

Import and analyze event data from multiple sources:

* Native Windows Event Log (`.evtx`) files
* JSON, CSV, and XML event datasets
* Local Windows event channels
* Security, System, Application, PowerShell, and Sysmon logs

Batch ingestion is designed to support investigations involving multiple log files and event sources.

### 🔬 2. Windows Event Decoding & Forensic Analysis

Decode Windows event fields into analyst-readable information.

* Logon type interpretation
* Windows status and substatus code decoding
* Security Identifier (SID) interpretation
* Event ID and provider identification
* Timestamp normalization
* Event field extraction and structured presentation

### 🤖 3. Hybrid AI Analysis Engine

The platform is designed to support three analysis modes:

* **Google Gemini:** AI-assisted event investigation
* **Anthropic Claude:** Contextual forensic analysis and explanation
* **Offline forensic engine:** Deterministic detection and correlation without external AI services

A multi-stage verification workflow is intended to reduce false positives by validating candidate findings against available event evidence and detection criteria.

**Important:** AI-generated conclusions are investigative assistance, not proof of compromise. Findings should be validated against the original event records and other available evidence.

### 📊 4. SIEM Correlation & Incident Timeline

Correlate related events to help identify suspicious activity across a defined investigation window.

Potential investigation scenarios include:

* Repeated failed logon attempts
* Successful logons following suspicious authentication activity
* Account creation and group membership changes
* Privilege escalation indicators
* PowerShell execution patterns
* Suspicious process and network activity
* Related events occurring across multiple log sources

The usefulness of each scenario depends on available telemetry, enabled auditing, and implemented detection rules.

### 📄 5. Professional DFIR PDF Reports

Generate structured investigation reports using QuestPDF.

The planned 13-section report format includes:

1. Cover Page & Case Metadata
2. Executive Summary
3. Investigation Scope & Methodology
4. Data Sources & Collection Details
5. Event Reference Matrix
6. Incident Timeline
7. Detailed Findings
8. Indicators of Compromise (IOCs)
9. MITRE ATT&CK Mapping
10. Risk Assessment
11. Evidence Integrity & SHA-256 Manifest
12. Remediation Recommendations
13. Conclusion & Technical Appendix

Reports are intended for SOC investigations, security assessments, incident documentation, and technical review.

**Evidence-integrity note:** SHA-256 hashes can help verify whether collected evidence has changed since hashing. A hash alone does not establish authenticity, acquisition provenance, or legal admissibility.

### 👁️ 6. Real-Time Windows Event Monitoring

A live monitoring workflow is designed to periodically collect new events from selected local Windows channels.

* Configurable monitoring scope
* Periodic event polling
* New-event processing
* Suspicious activity highlighting
* Integration with the investigation workflow

The proposed default polling interval is 30 seconds. Actual monitoring coverage depends on channel access, collection implementation, event volume, and system permissions.

### 🌐 7. OSINT, GeoIP & ASN Enrichment

Enrich eligible public source IP addresses with contextual network intelligence, including:

* Country and city
* Internet service provider
* Autonomous System Number (ASN)
* Proxy or hosting classification, where supported

Enrichment depends on the configured provider and available data. IP geolocation and hosting classifications are estimates and must not be treated as proof of an attacker's physical location or identity.

### 🧪 8. Sigma Rule Studio

Support investigation and detection engineering through Sigma rule testing.

* YAML rule loading and validation
* Rule syntax and structure inspection
* Event matching against supported fields
* Detection-result review
* Iterative rule development

Rule compatibility depends on the supported Sigma features and the implemented matching or conversion engine.

### 🖥️ 9. Safe PowerShell Host Verification

Provide read-only checks for selected local Windows security information, subject to operating-system permissions.

Examples include:

* Local user enumeration
* Local group membership inspection
* TCP connection inspection
* Windows service enumeration
* Running process enumeration

Example commands include `Get-LocalUser`, `Get-LocalGroupMember`, `Get-NetTCPConnection`, `Get-Service`, and `Get-Process`.

These checks are intended for defensive verification. Read-only behavior should be enforced and tested by the implementation.

### 🗃️ 10. Persistent Case History

Maintain an investigation history to help analysts resume previous cases.

* Save investigation metadata and findings
* Archive case sessions
* Reload previously saved investigations
* Review prior analysis results
* Support repeatable investigation workflows

Case storage should include appropriate access controls, retention policies, and protection for potentially sensitive security data.

---

## 🏗️ Architecture Overview

The intended high-level processing pipeline is:

```text
Windows Event Sources
        |
        v
Event Log Ingestion
        |
        v
Parsing & Normalization
        |
        v
Windows Event Decoder
        |
        v
Deterministic Detection Engine
        |
        v
Event Correlation & Timeline
        |
        +-----------------------+
        |                       |
        v                       v
AI-Assisted Analysis      Sigma Rule Testing
        |                       |
        +-----------+-----------+
                    |
                    v
             Finding Validation
                    |
                    v
          IOC & ATT&CK Enrichment
                    |
                    v
          Risk Assessment & Findings
                    |
                    v
         SHA-256 Evidence Manifest
                    |
                    v
             QuestPDF Reports
                    |
                    v
           Persistent Case History
```

This diagram represents the intended architecture. Actual module boundaries and data flows should match the released implementation.

---

## 🛠️ Technology Stack

| Component             | Technology                                      |
| --------------------- | ----------------------------------------------- |
| Primary language      | C#                                              |
| Application framework | .NET                                            |
| PDF reporting         | QuestPDF                                        |
| AI integration        | Google Gemini and Anthropic Claude              |
| Local analysis        | Deterministic forensic engine                   |
| Event formats         | EVTX, JSON, CSV, XML                            |
| Detection content     | Sigma YAML                                      |
| Threat classification | MITRE ATT&CK                                    |
| Evidence integrity    | SHA-256                                         |
| Host verification     | Windows PowerShell                              |
| Case persistence      | Specify the database used by the implementation |

---

## 🚀 Getting Started

### Prerequisites

Before running the application, verify that you have:

* A supported Windows operating system
* The .NET SDK version required by the project
* Access to sample event logs or authorized local Windows event channels
* API credentials if using cloud AI providers
* Network access if using external OSINT enrichment
* Required permissions for the selected event channels

### Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/QAISARE-EVENT-LOG-ANALYZER.git
cd QAISARE-EVENT-LOG-ANALYZER
```

Inspect the solution and restore dependencies:

```bash
dotnet --info
dotnet restore
```

Build the solution:

```bash
dotnet build --configuration Release
```

Run the application using the appropriate project path:

```bash
dotnet run --project path/to/YourApplication.csproj
```

Replace the repository URL and project path with the actual published values.

### Configuration

Store API credentials outside source control using environment variables, .NET user secrets, or a dedicated secrets manager.

Example PowerShell configuration:

```powershell
$env:GEMINI_API_KEY = "your-api-key"
$env:ANTHROPIC_API_KEY = "your-api-key"
```

Use your application's actual configuration variable names. Never commit real credentials, private logs, or sensitive investigation data to GitHub.

---

## 🔎 Example Investigation Workflow

A typical investigation can follow these steps:

1. Create a new investigation case.
2. Import one or more Windows event log files.
3. Parse and normalize the event records.
4. Review authentication, account-management, process, and network-related activity.
5. Run deterministic detections and supported Sigma rules.
6. Correlate related events into a timeline.
7. Use an AI provider for additional context, if enabled.
8. Validate findings against original event evidence.
9. Review severity, relevant IOCs, and ATT&CK mappings.
10. Generate a PDF report and record evidence hashes.
11. Save the case for future review.

### Illustrative detection scenarios

| Scenario                | Relevant telemetry                           | Investigation objective                                      |
| ----------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| Repeated failed logons  | Security Event ID 4625                       | Identify possible password guessing                          |
| Successful logon        | Security Event ID 4624                       | Establish authentication context                             |
| New user account        | Security Event ID 4720                       | Investigate unexpected account creation                      |
| Privileged group change | Security Event IDs 4728, 4732, 4756          | Investigate group membership changes                         |
| PowerShell activity     | PowerShell logs and relevant Security events | Examine potentially suspicious command execution             |
| Process creation        | Sysmon Event ID 1, if enabled                | Investigate process execution and parent-child relationships |
| Network connection      | Sysmon Event ID 3, if enabled                | Investigate process-associated network activity              |

Event IDs alone do not prove malicious activity. Interpretation requires context, event fields, audit configuration, and correlation with related evidence.

---

## 🔐 Security & Privacy

The platform is intended for authorized defensive security operations and forensic investigations.

Recommended safeguards:

* Keep AI provider keys outside source control.
* Clearly disclose when data is sent to external AI or enrichment services.
* Offer offline analysis when external processing is not permitted.
* Restrict access to case databases and exported reports.
* Preserve original event records and document transformations.
* Record evidence hashes and acquisition metadata.
* Avoid automatically executing commands or modifying the investigated host.
* Sanitize imported content before displaying or passing it to AI systems.
* Treat event data, command lines, and log messages as untrusted input.
* Apply retention and deletion policies to sensitive case data.

**Offline mode:** Offline analysis should not require external AI or OSINT calls. Verify this behavior through network-isolation testing before describing the mode as fully offline.

---

## 🧪 Testing & Validation

Before declaring a feature production-ready, validate it with controlled test datasets.

* [ ] Parse representative EVTX files successfully.
* [ ] Handle malformed or unsupported input safely.
* [ ] Preserve timestamps, provider names, event IDs, and original evidence.
* [ ] Validate status, substatus, logon type, and SID decoding.
* [ ] Test detections against positive and negative cases.
* [ ] Measure false positives and false negatives.
* [ ] Verify Sigma rule compatibility.
* [ ] Confirm that offline mode makes no external requests.
* [ ] Verify API errors, rate limits, and missing credentials.
* [ ] Test live polling for duplicate and missed events.
* [ ] Recalculate exported evidence hashes independently.
* [ ] Confirm that PDF findings match the underlying case data.
* [ ] Test case persistence, access restrictions, and error recovery.

---

## 🗺️ Roadmap

Potential future enhancements include:

* [ ] Expanded Windows event detection coverage
* [ ] Additional Sigma rule compatibility
* [ ] Custom correlation rules and detection thresholds
* [ ] Improved case search and investigation filtering
* [ ] MITRE ATT&CK technique coverage reporting
* [ ] Configurable evidence retention and export controls
* [ ] Automated regression testing with curated EVTX datasets
* [ ] Detection quality metrics and analyst feedback
* [ ] Additional log-source integrations
* [ ] Reproducible deployment and packaging

Roadmap items should be marked complete only after implementation and testing.

---

## 👨‍💻 Author

**Qaisare**

Cybersecurity | Digital Forensics | Threat Detection | Security Automation

Building practical security tools focused on Windows event analysis, forensic investigations, and incident response.

---

## ⚖️ Disclaimer

QAISARE EVENT LOG ANALYZER is intended for authorized security monitoring, defensive investigation, digital forensics, and educational purposes.

Users are responsible for obtaining appropriate authorization before accessing event logs, investigating systems, or collecting security evidence. AI-generated findings and automated detections require appropriate human validation.

---

## ⭐ Support the Project

If you find this project useful:

* Star the repository.
* Report reproducible bugs through GitHub Issues.
* Suggest detection improvements.
* Contribute test datasets that do not contain sensitive information.
* Submit improvements through pull requests.

**Turning Windows event data into meaningful security intelligence.**


