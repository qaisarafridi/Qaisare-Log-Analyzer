# 🛡️ QAISARE EVENT LOG ANALYZER v1.0.0

First public release of **QAISARE EVENT LOG ANALYZER** — an AI-powered Windows Event Log Forensics, SIEM Correlation, and DFIR Reporting Platform engineered by **Qaisare**.

### ✨ Highlights in v1.0.0
- **Multi-Source & Batch Log Ingestion**: Native binary `.evtx`, `.json`, `.csv`, `.xml`, and Live Local Windows Channel streaming (`Security`, `System`, `Application`, `PowerShell`, `Sysmon`).
- **Deep Windows XML & Hex Decoder**: Automatic translation of `LogonType`, `Status`/`SubStatus` (`NTSTATUS` codes), and Windows Security Identifiers (`SID`).
- **Hybrid AI Backend Forensics**: Integrated **Google Gemini 3 Flash**, **Anthropic Claude**, and a **100% Offline Deterministic SOC Forensic Engine** with 5-stage false-positive verification.
- **13-Section White-Page DFIR PDF Report**: Court-ready PDF generation powered by QuestPDF, including Executive Summary, Event Reference Matrix, Incident Timeline, IOCs, MITRE ATT&CK v15 Mapping, Risk Assessment, and SHA-256 Evidence Chain of Custody.
- **Real-Time SIEM Live Watch**: Continuous 30-second auto-polling for live Windows threat monitoring.
- **Live OSINT GeoIP & ASN Enrichment**: Real-time Country, City, ISP, ASN, and Proxy/Hosting classification for public source IPs.
- **Sigma Rule Studio & 1-Click Safe PowerShell Verifier**: Interactive Sigma YAML rule testing and read-only local host verification (`Get-LocalUser`, `Get-LocalGroupMember`, `Get-NetTCPConnection`, `Get-Service`, `Get-Process`).
- **Persistent Case History Database**: Automatic archiving and instant reload of past forensic sessions.
