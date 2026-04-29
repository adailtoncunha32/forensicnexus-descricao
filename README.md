# ForensicNexus Ultra v5.0

**National-Security Grade Digital Forensics Platform**

[![Status](https://img.shields.io/badge/status-OPERATIONAL-00ff88?style=flat-square&labelColor=020509)](https://forensicnexus-frontend.vercel.app)
[![Version](https://img.shields.io/badge/version-5.0.0-00c8ff?style=flat-square&labelColor=020509)](https://github.com/adailtoncunha32/forensicnexus-frontend)
[![Lines](https://img.shields.io/badge/lines_of_code-111%2C703-cc44ff?style=flat-square&labelColor=020509)](#codebase)
[![Files](https://img.shields.io/badge/source_files-487-ffab00?style=flat-square&labelColor=020509)](#codebase)
[![Billing](https://img.shields.io/badge/billing-Stripe_Live-00ff88?style=flat-square&labelColor=020509)](#subscription-plans)

**Live platform:** https://forensicnexus-frontend.vercel.app  
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

```
  ███████╗ ██████╗ ██████╗ ███████╗███╗   ██╗███████╗██╗ ██████╗
  ██╔════╝██╔═══██╗██╔══██╗██╔════╝████╗  ██║██╔════╝██║██╔════╝
  █████╗  ██║   ██║██████╔╝█████╗  ██╔██╗ ██║███████╗██║██║     
  ██╔══╝  ██║   ██║██╔══██╗██╔══╝  ██║╚██╗██║╚════██║██║██║     
  ██║     ╚██████╔╝██║  ██║███████╗██║ ╚████║███████║██║╚██████╗
  ╚═╝      ╚═════╝ ╚═╝  ╚═╝╚══════╝╚═╝  ╚═══╝╚══════╝╚═╝ ╚═════╝
```

<h2><code>NEXUS ULTRA v5.0</code></h2>

**The Operating System for Digital Truth**

*Government-grade digital forensics · AI surveillance · Predictive intelligence*

<br>

[![Live Platform](https://img.shields.io/badge/LIVE-forensicnexus--frontend.vercel.app-00c8ff?style=for-the-badge&logo=vercel&logoColor=white)](https://forensicnexus-frontend.vercel.app)
[![API Online](https://img.shields.io/badge/API-ONLINE-00c8ff?style=for-the-badge&logo=railway&logoColor=white)](https://forensicnexus-backend-production.up.railway.app/health)
[![GitHub](https://img.shields.io/badge/GitHub-adailtoncunha32-00c8ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/adailtoncunha32)

<br>

[![LOC](https://img.shields.io/badge/113%2C048-lines_of_code-00c8ff?style=flat-square&labelColor=020509)]()
[![Endpoints](https://img.shields.io/badge/241%2B-REST_endpoints-00c8ff?style=flat-square&labelColor=020509)]()
[![ML](https://img.shields.io/badge/10-ML_pipelines-00c8ff?style=flat-square&labelColor=020509)]()
[![Vision](https://img.shields.io/badge/13-Vision_AI_modules-00c8ff?style=flat-square&labelColor=020509)]()
[![Status](https://img.shields.io/badge/status-production-00ff88?style=flat-square&labelColor=020509)]()
[![License](https://img.shields.io/badge/license-Proprietary-ff2d55?style=flat-square&labelColor=020509)]()

<br>

> *"In an age where every crime leaves a digital trace, investigators are still using tools built for 2010.*
> *We built the platform for 2030."*

</div>

---

## 🌐 Live Deployment

| Service | URL | Status |
|---|---|---|
| **Platform** | [forensicnexus-frontend.vercel.app](https://forensicnexus-frontend.vercel.app) | 🟢 Online |
| **Backend API** | [forensicnexus-backend-production.up.railway.app](https://forensicnexus-backend-production.up.railway.app/health) | 🟢 Online |
| **API Docs** | [/docs](https://forensicnexus-backend-production.up.railway.app/docs) | 🟢 Online |

> 📧 **contact@forensicnexus.io** — Enterprise & Government inquiries welcome

---

## The Problem

The global digital forensics market is **$11.9 billion** growing at **14.5% CAGR**. Yet investigators, banks, hospitals, and critical infrastructure operators fight modern threats with fragmented toolchains built over decades of technical debt.

A homicide investigator needs **7 different tools** to analyse one phone. A hospital has cameras that record but no AI that understands. A bank processes millions of transactions but detects fraud hours later.

**Every tool speaks a different language. Every export breaks chain of custody.**

---

## The Solution

**ForensicNexus Ultra** unifies **13 operational domains** into a single, forensically-sound, evidentially-defensible platform.

One authentication. One chain of custody. One interface. One API.

---

## 📊 Auditable Metrics

```
╔══════════════════════════════════════════════════════════════════════╗
║                   LINES OF CODE — AUDITED                           ║
╠══════════════════════════════════════════════════════════════════════╣
║  Python Backend        39,141 lines   190 files · 26 modules        ║
║  TypeScript / React    22,218 lines    57 files · 41 pages          ║
║  Native C/C++ / Rust   38,009 lines    4 workers · high-perf core   ║
║  Config / Deploy       13,680 lines    Docker · TOML · YAML         ║
╠══════════════════════════════════════════════════════════════════════╣
║  TOTAL                113,048 LINES                                 ║
╚══════════════════════════════════════════════════════════════════════╝

  241+  REST endpoints        10   ML pipelines (PyTorch 2.6)
    41  frontend pages        13   Vision AI components (7,514 LOC)
    26  backend modules        4   native workers (Rust · C · C++)
    92  Python dependencies   6+   months solo engineering
```

---

## ⚡ Capabilities

### 🔒 Mobile Device Forensics & Unlocking

**Full-spectrum acquisition** — Android via ADB, Fastboot, EDL (Qualcomm). iOS via `pymobiledevice3`, lockdown protocol, DFU. Logical, file-system, and physical modes. Includes deleted messages, historical GPS, app data, and browser history.

**16 unlocking methods** — zero dependency on manufacturer cooperation:

| Android (8 methods) | iOS (8 methods) |
|---|---|
| ADB — USB debugging | DFU Mode — firmware level |
| Fastboot — bootloader | Recovery Mode — iTunes bypass |
| EDL — Qualcomm factory | Lockdown exploit — pymobiledevice3 |
| TWRP — custom recovery | MDM bypass — no data wipe |
| FRP bypass — Google account | Face ID / Touch ID bypass |
| MDM bypass — enterprise | Passcode brute force — NAND mirroring |
| Brute force — anti-throttle | iCloud lock bypass — via IMEI |
| Chip-Off — hardware level | JTAG — chip-level access |

### 🔬 Deep Forensics

| Feature | Description |
|---|---|
| **File Carving** | Magic byte recovery across corrupted filesystems and unallocated space |
| **SQLite WAL Recovery** | Extracts deleted WhatsApp/Signal/iMessage records from Write-Ahead Log |
| **EXIF/GPS Extraction** | Real location, camera model, real timestamps from images |
| **Binary String Analysis** | URLs, emails, credentials extracted from executables |
| **Message Reconstruction** | Deleted conversations rebuilt from fragmented app databases |
| **Chain of Custody** | SHA-256 per artifact · immutable audit trail · NIST 800-86 · ISO 27037 |

### 🦠 Threat Intelligence & Malware

- **YARA** pattern matching + **PE structural analysis** + Shannon entropy + **androguard**
- ML-based detection: DDoS, port scanning, brute force, C2 beaconing, MITM, lateral movement
- Real-time process monitoring with emergency network isolation
- **VirusTotal** + **Shodan** + **AbuseIPDB** + **GreyNoise** integration

### 🌐 OSINT Engine

Phone intelligence · Domain reputation · IP geolocation + ASN · IMEI analysis · MAC lookup · Email breach detection (HaveIBeenPwned) · Entity correlation across sources.

### ✈️ Aviation Intelligence (ADS-B)

Real-time tracking via OpenSky Network. ML anomaly detection. Squawk 7500/7600/7700 alerting. Classifies: Commercial · Military · Helicopter · Drone · Emergency.

---

## 🧠 Machine Learning — 10 Specialised Pipelines

| Pipeline | Domain | Technique |
|---|---|---|
| `financial_fraud_ml` | Banking · FinTech | IsolationForest + velocity rules + card testing |
| `industrial_analytics_ml` | Manufacturing · Energy | Predictive maintenance + OEE + failure forecasting |
| `medical_analytics_ml` | Hospitals · ICU | NEWS2 + Morse Fall Scale + nursing SLA |
| `driver_analytics_ml` | Fleet · Transport | Fatigue + EU Reg 561/2006 + distraction |
| `retail_analytics_ml` | Retail | Loss prevention + footfall + shrinkage |
| `aviation_pipeline` | Aviation · Defence | Random Forest + IsolationForest |
| `malware_pipeline` | Cybersecurity | PE + entropy + YARA ensemble |
| `identity_pipeline` | Intelligence | Sentence-BERT cross-corpus entity linking |
| `behavior_pipeline` | Legal · Forensics | NLP behavioural intent classification |
| `device_pipeline` | Forensics | Device fingerprinting + spoofing detection |

---

## 👁️ Vision AI — 6 Sector Modules

**YOLOv8 + Reinforcement Learning** — the system learns from operator feedback. Every ✅/❌ click feeds a Q-learning engine that adjusts per-rule thresholds automatically. After ~20 feedback events, false positives drop measurably without sacrificing recall.

| Module | Sector | Detects |
|---|---|---|
| `driver_monitoring` | Fleet · Trucks · Taxi | Fatigue · phone use · seatbelt · EU 561/2006 |
| `medical_vision` | Hospitals · ICU · Care homes | Falls · bed exits · immobility · agitation |
| `ppe_detection` | Factories · Construction | Helmet · hi-vis vest · safety boots · gloves |
| `agv_safety` | Warehouses · Logistics | Danger zones · human-robot proximity · collision |
| `robotics_quality` | Assembly lines | Product defects · assembly errors · dimensional QA |
| `financial_fraud` | Banks · ATMs | Skimmers · suspicious behaviour · robbery |

**Protocol support:** RTSP · MJPEG · USB · MQTT · ONVIF Profile S/T. Works air-gapped. Works on edge (NVIDIA Jetson).

---

## ⚙️ Native Workers — High Performance Core

```
Rust + PyO3 + Rayon      →  Parallel SHA256/Blake3: 20x faster than Python
C (pure, 811 LOC)         →  Raw disk forensics · magic byte carving · memory ops
C++ + OpenCV + pybind11   →  60+ FPS frame processing · multi-object tracking · CUDA-ready
C + libusb (158 LOC)      →  USB device enumeration at driver level
```

Native workers handle the performance-critical path while Python orchestrates ML inference and business logic.

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│  FRONTEND   React 18 · TypeScript 5.6 · Vite 6 · Zustand           │
│  22,218 LOC · 41 pages · Orbitron/Rajdhani · dark government theme  │
├──────────────────────────────────────────────────────────────────────┤
│  BACKEND    FastAPI 0.115 · Python 3.12 · SQLAlchemy 2.0 async      │
│  39,141 LOC · 26 modules · 241+ endpoints · RBAC 5 levels           │
├──────────────────────────────────────────────────────────────────────┤
│  ML ENGINE  PyTorch 2.6 · Transformers 4.49 · Scikit-learn          │
│  10 pipelines · YOLOv8 · Sentence-BERT · Q-Learning RL              │
├──────────────────────────────────────────────────────────────────────┤
│  NATIVE     Rust+PyO3 · C · C++/OpenCV                              │
│  38,009 LOC · 20x hashing · 60+ FPS vision · driver-level USB       │
├──────────────────────────────────────────────────────────────────────┤
│  SECURITY   Argon2id · JWT HS256 · AES-256 · TLS 1.3               │
│  SHA-256 chains · immutable audit trail · 5-level RBAC              │
├──────────────────────────────────────────────────────────────────────┤
│  INFRA      Railway (Docker) · Vercel (global CDN)                  │
│  SQLite (dev) → PostgreSQL (enterprise) · SSE · WebSocket           │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 🔐 Security & Compliance

| Layer | Implementation |
|---|---|
| **Authentication** | JWT HS256 · Argon2id · 5-level RBAC |
| **Data integrity** | SHA-256 per artifact · immutable audit log |
| **In transit** | TLS 1.3 enforced |
| **At rest** | AES-256 encryption |
| **Forensic standards** | NIST SP 800-86 · ISO/IEC 27037 |
| **Privacy** | GDPR · LGPD ready |
| **Government tier** | Air-gapped on-premise · SAML 2.0 / OIDC |
| **Roadmap** | FIPS 140-2 · ISO 27001 · FedRAMP |

---

## 💼 Target Markets

| Sector | Use Case |
|---|---|
| 🏛️ **Law Enforcement** | Mobile forensics · court-admissible evidence · device unlocking |
| 🏦 **Banking & FinTech** | Real-time fraud · AML · ATM video analytics |
| 🏥 **Healthcare** | Patient Vision AI · NEWS2 auto-scoring · fall detection |
| 🏭 **Industrial** | Predictive maintenance · OEE · PPE compliance · AGV safety |
| 🚚 **Fleet & Transport** | Driver fatigue · EU 561/2006 · route anomaly |
| 🏢 **Corporate Security** | Insider threat · DLP · incident response |

---

## 💰 Pricing

| Plan | Price | Includes |
|---|---|---|
| **Starter** | $99 / month | Forensics Core + OSINT |
| **Professional** | $299 / month | + ML Engine + Threat Intel |
| **Enterprise** | $799 / month | Full platform |
| **Enterprise+** | $1,299 / month | + Vision AI + Aviation |
| **Government** | Under evaluation | On-premise + SLA + audit support |

> Add-ons: Vision AI $199/mo · Aviation Intel $99/mo · Extra ML Pipelines $149/mo

---

## 🚀 Full Tech Stack

```
BACKEND
  FastAPI 0.115 · Python 3.12 · SQLAlchemy 2.0 · Pydantic v2 · Alembic
  PyTorch 2.6 · Transformers 4.49 · YOLOv8 · Scikit-learn
  pymobiledevice3 · YARA-python · pefile · androguard
  Argon2-cffi · python-jose · loguru · httpx · aiosqlite

FRONTEND
  React 18 · TypeScript 5.6 · Vite 6 · Zustand · React Router 6
  Recharts · Lucide React · Orbitron · Rajdhani · Share Tech Mono

NATIVE WORKERS
  Rust 1.80 + PyO3 + Rayon  →  parallel SHA256/Blake3
  C17 + libusb               →  USB driver level
  C++17 + OpenCV 4 + pybind11 → frame processing + CUDA

INFRASTRUCTURE
  Backend   →  Railway (Docker · python:3.12-slim)
  Frontend  →  Vercel (Vite · global CDN)
  Database  →  SQLite (dev) · PostgreSQL (enterprise)
```

---

## 🎨 Design Philosophy

Every pixel engineered for operators who work in high-stakes environments at 3 AM. We rejected cloud-SaaS aesthetics. We studied NASA mission control, military command centres, Bloomberg terminals.

**Typography:** Orbitron (command) · Rajdhani (body) · Share Tech Mono (data)  
**Palette:** `#020509` deep space · `#00c8ff` signal cyan · `#ff2d55` alert · `#00ff88` clear  
**Principles:** Keyboard-first · real-time streaming · dark-mode-only · information density without noise

---

## 📞 Contact

<div align="center">

| | |
|---|---|
| 📧 **Email** | contact@forensicnexus.io |
| 🌐 **Platform** | [forensicnexus-frontend.vercel.app](https://forensicnexus-frontend.vercel.app) |
| 🔗 **GitHub** | [github.com/adailtoncunha32](https://github.com/adailtoncunha32) |

**Adailton Cunha** — Founder · CEO · Principal Engineer · 🇵🇹 Lisbon, Portugal

*Open to: investment · enterprise licensing · government contracts · technical partnership*

<br>

[![Contact](https://img.shields.io/badge/Email-contact%40forensicnexus.io-00c8ff?style=for-the-badge)](mailto:contact@forensicnexus.io)
[![Live Demo](https://img.shields.io/badge/Live_Demo-Try_Now-00c8ff?style=for-the-badge)](https://forensicnexus-frontend.vercel.app)
[![Health](https://img.shields.io/badge/API-Health_Check-00c8ff?style=for-the-badge)](https://forensicnexus-backend-production.up.railway.app/health)

</div>

---

<div align="center">

**113,048 lines · 6 months · Solo · From first principles · Lisbon, Portugal 🇵🇹**

*Proprietary · All Rights Reserved · © 2026 ForensicNexus*  
*Source code in private repositories · Patents pending*

</div>
