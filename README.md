# ForensicNexus Ultra v5.0

**National-Security Grade Digital Forensics Platform**

[![Status](https://img.shields.io/badge/status-OPERATIONAL-00ff88?style=flat-square&labelColor=020509)](https://forensicnexus.company)
[![Version](https://img.shields.io/badge/version-5.0.0-00c8ff?style=flat-square&labelColor=020509)](https://github.com/adailtoncunha32/forensicnexus-frontend)
[![Lines](https://img.shields.io/badge/lines_of_code-111%2C703-cc44ff?style=flat-square&labelColor=020509)](#codebase)
[![Files](https://img.shields.io/badge/source_files-487-ffab00?style=flat-square&labelColor=020509)](#codebase)
[![Billing](https://img.shields.io/badge/billing-Stripe_Live-00ff88?style=flat-square&labelColor=020509)](#subscription-plans)

**Live platform:** https://https://forensicnexus.company
**API documentation:** https://forensicnexus-backend-production.up.railway.app/docs  
**Features overview:** https://forensicnexus-frontend.vercel.app/features  
**Plans & pricing:** https://forensicnexus-frontend.vercel.app/plans

---

## What is ForensicNexus Ultra?

ForensicNexus Ultra is a production-grade digital forensics platform built for law enforcement forensic laboratories, intelligence agencies, and enterprise security operations centres.

It consolidates 16 investigative modules into a single unified interface — from the moment a device is seized, through extraction, AI-powered analysis, criminal network mapping, and court-admissible documentation. Every action is logged immutably. Every file is SHA-256 verified. Every report satisfies ISO 27037 and NIST SP 800-86.

---

## Codebase

```
Frontend   React 18 + TypeScript + Vite     29,003 lines    79 files
Backend    Python 3.11 + FastAPI            81,523 lines   215 files
Native     Workers + Bridge Layer              255 lines   190 files
Docs                                           822 lines     2 files
─────────────────────────────────────────────────────────────────────
Total                                      111,703 lines   487 files
```

---

## Investigation Workflow

A complete forensic investigation follows this sequence — each module feeds the next:

```
1.  Case Management        →  create case, register judicial warrant
2.  Device Operations      →  register seized device (auto-detected via USB)
3.  Device Access Hub      →  unlock device (16 methods: Android + iOS)
4.  Acquisition Ops        →  extract data (logical / filesystem / physical)
5.  Recovery Ops           →  recover deleted data (messages, media, contacts)
6.  Deep Forensics         →  file carving, SQLite WAL, EXIF/GPS extraction
7.  Evidence Registry      →  SHA-256 chain of custody, court documentation
8.  Intelligence Ops       →  OSINT enrichment of IPs, phones, identifiers
9.  Threat Operations      →  cross-reference with threat intelligence
10. ML Engine              →  behavioural analysis, anomaly detection
11. NEXUS Graph            →  criminal network mapping
12. Export & Reports       →  court-admissible PDF with full custody log
```

---

## 16 Modules

### CORE Plan — from €79/month

#### Deep Forensics
Binary-level analysis of storage media and file systems. File carving recovers files by binary signature (magic bytes) even without a filesystem. SQLite WAL reconstruction rebuilds uncommitted database transactions from WhatsApp, Signal, and Telegram. EXIF/GPS extraction pulls precise geolocation and timestamps from image metadata. Entropy analysis detects encrypted or hidden compressed files. Every output carries a SHA-256 integrity hash and is compliant with ISO/IEC 27037:2012.

#### OSINT Intelligence
Parallel intelligence aggregation from open sources. Given an IP address, phone number, IMEI, MAC address, email, or domain — the engine queries Shodan, HaveIBeenPwned, GreyNoise, AbuseIPDB, DNS/WHOIS, and HTTP headers simultaneously. Returns a complete enriched profile in seconds: geolocation, organisation, reputation score, breach membership, exposed services, and associated devices.

#### Evidence Registry & Case Management
Complete digital evidence management with cryptographic verification at every access point. Every evidence item carries a SHA-256 hash, operator identity, timestamp, and custody transfer history. Generates court-ready documentation compliant with ISO 27037 and NIST SP 800-86 on demand.

#### Cryptographic Operations
Algorithm identification in binary files, bulk SHA-256/SHA-512 hash verification, password entropy analysis, SSL/TLS certificate forensics, and HMAC computation for evidence integrity attestation.

#### Analysis Center & Export
Unified timeline reconstruction aggregating events from all modules keyed to a case ID. Identifies temporal relationships between device activity, communications, locations, and network events. Exports to court-admissible PDF with full operator identification, legal authority reference, evidence hashes, and timestamped action logs.

---

### INTELLIGENCE Plan — from €249/month
*Includes everything in CORE, plus:*

#### ML Engine — 11 Specialised Pipelines
Machine learning inference with SHAP feature attribution for court-defensible, explainable predictions. Covers fraud detection, behavioural analysis, anomaly identification, driver risk monitoring, medical data analysis from seized wearables, industrial predictive maintenance, retail loss prevention, network intrusion detection, document classification, image recognition, and communication sentiment analysis. Models are trained on operator-supplied datasets, persisted to disk, and hot-loaded on restart without retraining.

#### Vision AI with Reinforcement Learning
YOLOv8 object detection runs against live camera feeds, recorded footage, and extracted device media simultaneously. A Q-Learning reinforcement agent adapts detection thresholds based on operator feedback — labelling results as correct or false positive. The agent continuously improves accuracy without manual retraining cycles. Real-time alerts stream to the browser via Server-Sent Events.

#### Threat Operations
Real-time cyberattack detection and IOC management. Detects DDoS patterns, command-and-control communication, brute-force credential attacks, and man-in-the-middle interception. All incidents are automatically mapped to the MITRE ATT&CK framework. IOCs are extracted and propagated across the platform.

#### Malware Engine
Static and behavioural analysis of Windows PE executables, Android APKs, Office documents with VBA macros, PDFs, and scripts. YARA pattern matching, entropy-based packing detection, VBA macro deobfuscation, and VirusTotal 72-engine reputation scoring. Identified IOCs are automatically added to Threat Operations.

#### Aviation ADS-B Intelligence
Live ADS-B transponder data ingestion for real-time aircraft tracking. Emergency squawk code detection — hijack (7500), radio failure (7600), general emergency (7700) — with alert latency under 30 seconds from transponder transmission. Configurable monitoring regions across nine global areas. Historical track replay and flight path anomaly detection.

#### NEXUS Criminal Graph Intelligence
Criminal network mapping using PageRank centrality to identify key operatives, Louvain community detection to uncover criminal sub-groups, and shortest-path analysis to reveal hidden connections between apparently unrelated subjects. Graphs from multiple investigations can be merged and cross-referenced. All nodes are enriched with OSINT data.

#### PHANTOM Steganography Detection
Ten simultaneous detection methods applied in parallel: LSB, DCT coefficient analysis, chi-squared statistical testing, RS analysis, histogram analysis, audio steganography, video frame analysis, document embedding, whitespace analysis, and palette manipulation. Returns a confidence score, estimated hidden payload capacity, and detected embedding technique per method.

---

### FIELD Plan — from €549/month
*Includes everything in INTELLIGENCE, plus:*

#### Device Acquisition
Full logical and physical extraction for Android and iOS with eight methods each.

Android: cascade auto, ADB logical, ADB backup, root extraction, Fastboot Recovery, app sandbox, EDL/BROM chipset detection (Qualcomm/MTK/Exynos/Kirin), chip-off NAND.

iOS: cascade auto, pymobiledevice3 full backup, AFC media, House Arrest app containers, crash logs, jailbreak filesystem via AFC2, libimobiledevice fallback, DFU mode.

Every extraction generates a SHA-256 manifest and an immutable custody event.

#### Data Recovery
Reconstructs deleted messages, media, contacts, and call logs from SQLite journals, unallocated storage, and fragmented database records. Supports WhatsApp, Telegram, Signal, iMessage, and SMS with full timestamp preservation. Recovery window extends up to 30 days post-deletion.

#### SPECTRE Cloud Forensics
Evidence extraction from iCloud, Google Drive, OneDrive, WhatsApp, and Telegram using OAuth tokens obtained from the seized device under lawful authorisation. Decrypts WhatsApp AES-256-GCM encrypted backup containers. Reconstructs deleted items within the cloud provider's retention window. All artefacts carry SHA-256 hashes and full chain-of-custody documentation.

---

### SOVEREIGN Plan — from €1,199/month
*Includes everything in FIELD, plus:*

#### 16 Hardware Unlock Methods
Advanced physical access for locked devices. Requires signed Legal Use Agreement.

Android: ADB unlock, Fastboot custom recovery, EDL mode, TWRP bypass, FRP bypass, MDM removal, PIN/pattern brute force, chip-off NAND.

iOS: DFU mode, Recovery mode, pymobiledevice3 deep access, MDM bypass, Face ID/Touch ID bypass, NAND mirroring passcode brute force, iCloud Activation Lock bypass, JTAG chip-level access.

#### GHOST Volatile Memory Forensics
RAM dump analysis to extract AES encryption keys, OAuth session tokens, and active credentials without requiring a live system. Detects rootkits through DKOM manipulation, SSDT hook analysis, process hollowing identification, and reflective DLL injection signatures. Supports `.raw`, `.mem`, `.lime`, `.vmem`, and Windows `hiberfil.sys` formats.

#### ORACLE Predictive Criminal Intelligence
Re-offending risk scoring from 0 to 100, method-of-operation pattern matching against known profiles, cross-case statistical correlation to find links between apparently unrelated investigations, temporal prediction of likely future criminal activity, and digital behavioural signature profiling.

---

### GOVERNMENT Plan — from €1,999/month
*Includes everything in SOVEREIGN, plus:*

Air-gapped on-premise deployment, classified environment support, 1-hour SLA, dedicated forensics engineer, volume licensing, and custom legal framework documentation for jurisdiction-specific court submission requirements.

---

## How modules connect — real investigation example

**Operation: Drug trafficking network**

```
Case Management      →  creates CASE-2026-047 "Operation Delta"
Device Operations    →  registers seized iPhone 15 Pro via USB (serial auto-detected)
Device Access Hub    →  pymobiledevice3 deep access unlocks the device
Acquisition Ops      →  physical extraction: 8.2 GB, SHA-256 manifest generated
Recovery Ops         →  recovers 847 deleted WhatsApp messages from last 30 days
SPECTRE Cloud        →  OAuth token from iPhone accesses iCloud, recovers deleted photos with GPS
Deep Forensics       →  photo analysis: 23 with GPS coordinates in Lisbon, 8 in Madrid
Intelligence Ops     →  IPs from messages → Shodan identifies suspicious VPN server
Malware Engine       →  binary found on device → identified as Cobalt Strike beacon
Threat Operations    →  C2 communication active → IOCs added to threat database
NEXUS Graph          →  constructs graph: suspect linked to 4 phones, 2 IPs, 3 locations
ORACLE Predict       →  re-offending score 87/100, MO matches 2 prior cases
Evidence Registry    →  all evidence registered with complete chain of custody
Export               →  47-page court-ready PDF for prosecution
```

---

## Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│                     FORENSICNEXUS ULTRA v5.0                         │
├──────────────────────────────┬───────────────────────────────────────┤
│  FRONTEND                    │  BACKEND                              │
│  React 18 + TypeScript       │  Python 3.11 + FastAPI                │
│  Vercel Global CDN           │  Railway (Europe West)                │
│  JWT auth + role guards      │  20+ async API routers                │
│  Real-time SSE streams       │  SQLAlchemy async + PostgreSQL        │
│  Stripe Live billing         │  Background job executor              │
├──────────────────────────────┴───────────────────────────────────────┤
│  NATIVE LAYER                                                        │
│  Compiled bridge workers — USB · Hash · Vision · Forensic           │
├──────────────────────────────────────────────────────────────────────┤
│  EXTERNAL INTEGRATIONS                                               │
│  Stripe · Shodan · VirusTotal · HaveIBeenPwned                      │
│  GreyNoise · AbuseIPDB · OpenSky ADS-B                             │
├──────────────────────────────────────────────────────────────────────┤
│  COMPLIANCE                                                          │
│  ISO/IEC 27037 · NIST SP 800-86 · SHA-256 Chain of Custody         │
│  Immutable audit trail · MITRE ATT&CK mapping                       │
└──────────────────────────────────────────────────────────────────────┘
```

---

## Subscription Plans

| Plan | Monthly | Annual (−20%) |
|---|---|---|
| CORE | €79 | €759 |
| INTELLIGENCE | €249 | €2,390 |
| FIELD | €549 | €5,270 |
| SOVEREIGN | €1,199 | €11,510 |
| GOVERNMENT | €1,999 | €19,190 |

Payments via Stripe Live. Plan activation is automatic on payment confirmation.

---

## Compliance

| Standard | Coverage |
|---|---|
| ISO/IEC 27037:2012 | Digital evidence identification, collection, acquisition and preservation |
| NIST SP 800-86 | Integrating forensic techniques into incident response |
| SHA-256 chain of custody | Cryptographic integrity from acquisition to court submission |
| Immutable audit trail | Every action logged with operator identity, timestamp, and IP |
| MITRE ATT&CK | All detected threats mapped to the framework |

SOVEREIGN and GOVERNMENT tiers require a signed Legal Use Agreement confirming lawful authorisation for hardware-level acquisition methods.

---

## Legal Notice

This platform is designed exclusively for lawful forensic investigation under judicial authorisation. All device access operations require a valid judicial warrant ID registered in the system. Every operation is logged with operator identity, timestamp, SHA-256 hashes, and full chain of custody. Unauthorised use is a criminal offence in all jurisdictions.

---

## Contact

Enterprise, government, and investment enquiries: contact@forensicnexus.io

---

*ForensicNexus Ultra v5.0 — Proprietary Software*  
*© 2026 ForensicNexus. All rights reserved.*
<div align="center">

<br>

