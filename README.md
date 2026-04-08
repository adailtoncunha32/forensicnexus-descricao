# ForensicNexus Ultra

**Professional Digital Forensics Platform**

A full-stack digital forensics platform built for law enforcement, judicial investigators, and certified forensic analysts. Designed for court-admissible evidence collection with complete chain of custody.

---

## Overview

ForensicNexus Ultra is a comprehensive digital forensics platform that integrates multiple acquisition methods, AI-powered analysis, and immutable evidence chain of custody into a single unified interface.

The platform is built with a multi-language architecture where each language handles what it does best:

- **Python** — orchestration, business logic, API
- **Rust** — cryptographic integrity and forensic hashing
- **C** — low-level USB detection and filesystem parsing  
- **C++** — computer vision and object tracking
- **TypeScript/React** — professional investigator interface

---

## Key Capabilities

### Device Acquisition
- Android: logical extraction, ADB backup, root extraction, EDL/Qualcomm physical, MediaTek BROM, Samsung Download Mode
- iOS: AFC media, logical backup, crash logs, checkm8 (A5–A11), agent-based (A12+), palera1n, BFU extraction
- Workstations: live RAM capture, disk imaging, BitLocker/FileVault/LUKS analysis, live triage

### Vision AI
- Real-time camera monitoring with YOLOv8 object detection
- 10 composite threat scenarios (armed robbery, kidnapping, patient at risk, fire, crowd panic, etc.)
- Sector-specific profiles: Transport, Industrial, Financial, Healthcare, Retail, Government
- Cross-camera person re-identification (privacy-preserving, GDPR compliant)
- Webhook delivery with HMAC-SHA256 signatures

### Forensic Analysis
- OSINT: phone intelligence, IP analysis, domain/email investigation
- Malware analysis: YARA rules, PE analysis, sandbox integration
- Case management with evidence correlation
- Aviation surveillance (ADS-B/FlytRadar)
- Timeline reconstruction and correlation

### Chain of Custody
- BLAKE3 + SHA-512 + MD5 for every artifact
- Immutable custody chain via Rust native worker
- Cryptographically signed forensic reports
- Court-admissible output format

---

## Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    React Frontend (TypeScript)               │
│              Professional Government-Grade UI                │
└─────────────────────────┬───────────────────────────────────┘
                          │ REST API
┌─────────────────────────▼───────────────────────────────────┐
│                  FastAPI Backend (Python)                    │
│         Orchestration · Business Logic · Rules Engine        │
└──────┬──────────────┬──────────────┬────────────────────────┘
       │              │              │
┌──────▼──────┐ ┌─────▼──────┐ ┌───▼───────────┐
│ Rust Worker │ │  C Worker  │ │  C++ Worker   │
│  BLAKE3     │ │  libusb    │ │  YOLOv8 ONNX  │
│  SHA-512    │ │  USB raw   │ │  ByteTrack    │
│  CustodyChain│ │  EDL/DFU  │ │  Pose Est.   │
└─────────────┘ └────────────┘ └───────────────┘
```

---

## Technology Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python 3.13, FastAPI, SQLAlchemy async |
| Frontend | React 18, TypeScript, Vite, Zustand |
| Native — Integrity | Rust, PyO3, BLAKE3, Maturin |
| Native — USB | C, GCC, libusb |
| Native — Vision | C++, OpenCV, YOLOv8 ONNX |
| Database | PostgreSQL (Supabase) |
| Mobile Protocols | pymobiledevice3, ADB, adbutils |

---

## Project Structure

```
forensecnexus-ultra/
├── backend/
│   └── src/
│       ├── auth/           # JWT authentication, roles
│       ├── vision/         # Camera AI, alerts, webhooks
│       ├── device_access/  # Multi-platform acquisition
│       ├── ml/             # Machine learning engine
│       ├── osint/          # Open source intelligence
│       ├── forensics/      # Evidence analysis
│       ├── aviation/       # ADS-B surveillance
│       ├── cases/          # Case management
│       ├── evidence/       # Evidence registry
│       ├── analysis/       # Correlation engine
│       ├── malware/        # Malware analysis
│       ├── crypto/         # Cryptographic tools
│       ├── billing/        # Plans and entitlements
│       └── native/         # Native worker bridges
├── frontend/
│   └── src/
│       └── components/
│           ├── dashboard/  # Command center
│           ├── devices/    # Device acquisition hub
│           ├── ml/         # Vision AI interface
│           ├── forensics/  # Forensic analysis
│           ├── osint/      # OSINT interface
│           └── cases/      # Case management
└── native/
    ├── hash_worker/        # Rust — forensic hashing
    ├── usb_worker/         # C — USB detection
    ├── forensic_worker/    # C — filesystem parsing
    └── vision_worker/      # C++ — computer vision
```

---

## Codebase Size

| Layer | Files | Lines |
|-------|-------|-------|
| Backend (Python) | 182 | 35,335 |
| Frontend (TypeScript) | 52 | 18,889 |
| Native Workers (C/C++/Rust) | 17 | ~2,400 |
| **Total** | **251** | **~56,600** |

---

## Forensic Standards

- All extractions require a registered warrant ID
- Every artifact is hashed with BLAKE3 + SHA-512 + MD5
- Immutable custody chain generated for every acquisition
- Reports are cryptographically signed and timestamped
- READ_ONLY operations do not modify device data

---

## Plans

| Plan | Target |
|------|--------|
| Standard | Small agencies and private investigators |
| Professional | Law enforcement departments |
| Enterprise | National agencies |
| Government | Institutional deployment with evaluation process |

---

## License

Proprietary — All rights reserved.  
© 2026 ForensicNexus. Unauthorised use prohibited.

---

## Legal Notice

This platform is designed exclusively for lawful forensic investigations by authorised personnel. Use requires a valid judicial warrant or equivalent legal authorisation. Misuse is prohibited and may result in criminal liability.
