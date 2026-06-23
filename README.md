# ForensicNexus Ultra v5.0

**Digital forensics & cyber intelligence — one platform, pay for what you need.**

Device acquisition · OSINT · threat intelligence · malware analysis · authorized pentesting — in a single operator dashboard and a clean REST API. **Start with a 14-day free trial.**

[![Status](https://img.shields.io/badge/status-OPERATIONAL-00ff88?style=flat-square&labelColor=020509)](https://forensicnexus-frontend.vercel.app)
[![Live demo](https://img.shields.io/badge/live-demo-00c8ff?style=flat-square&labelColor=020509)](https://forensicnexus-frontend.vercel.app)
[![Free trial](https://img.shields.io/badge/free_trial-14_days-cc44ff?style=flat-square&labelColor=020509)](https://forensicnexus-frontend.vercel.app/plans)

[**▶ Start free trial**](https://forensicnexus-frontend.vercel.app/plans) · [**Live app**](https://forensicnexus-frontend.vercel.app) · [**API docs**](https://forensicnexus-backend-production.up.railway.app/docs) · [**Book a demo**](mailto:contact@forensicnexus.io?subject=ForensicNexus%20demo)

---

## The problem we solve

Serious forensics suites cost **€3,000–€35,000+ per year**, ship as heavyweight on-prem installs, and bundle far more than most teams use. Smaller investigators, MSSPs and law firms are priced out — or stitch together five disconnected tools.

**ForensicNexus Ultra is the alternative:** one platform, self-serve, where you subscribe to **only the modules you need** (from €39/month) — or take a full plan — and everything shares one case, one audit trail, one chain of custody.

## Who it's for

| | |
|---|---|
| 🔎 **Private investigators & small forensics labs** | Phone/IMEI/OSINT lookups, evidence registry, case timelines, defensible PDF reports. |
| 🛡️ **MSSPs & DFIR teams** | Global threat-intelligence feed, malware triage, authorized pentest recon, real-time alerting. |
| ⚖️ **Law firms & corporate security** | Insider-threat investigations, device acquisition, court-ready documentation. |
| 🏛️ **Government & law enforcement** | Full suite, on-premise / air-gapped deployment, dedicated support (contact us). |

## How an investigation flows

Each module feeds the next — one case ID ties it all together:

```
1.  Case Management     →  open case, register warrant reference
2.  Device Operations   →  register the seized device (USB auto-detect)
3.  Device Access       →  authorized unlock cascade (read-only where possible)
4.  Acquisition         →  logical / filesystem extraction with SHA-256 manifest
5.  Recovery            →  recover deleted messages, media, contacts
6.  Deep Forensics      →  file carving, SQLite/WAL, EXIF/GPS
7.  Evidence Registry   →  SHA-256 chain of custody, custody log
8.  OSINT               →  enrich IPs, phones, identifiers
9.  Threat Intelligence →  cross-reference against the global threat feed
10. ML / NEXUS Graph    →  anomaly detection, criminal-network mapping
11. Export              →  court-ready PDF with full custody trail
```

---

## Modules

### Forensics
- **Deep Forensics** — file carving by signature, SQLite/WAL reconstruction (WhatsApp/Signal/Telegram), EXIF/GPS, entropy analysis. Every output SHA-256 hashed.
- **Device Access & Unlock** — authorized Android/iOS profiling and unlock cascade. Read-only where possible; we attempt unlock **without wiping device data**. *Coverage varies by model and OS version.*
- **Acquisition & Recovery** — logical/filesystem extraction; recovery of deleted messages, media, contacts and call logs from journals and unallocated space.
- **Evidence Registry & Cases** — every item carries a SHA-256 hash, operator identity, timestamp and custody history.

### Intelligence
- **OSINT** — IP · phone · IMEI · MAC · email · domain · global geolocation, with optional Shodan/HIBP/GreyNoise/AbuseIPDB enrichment and **LLM-assisted deep investigation**.
- **Threat Intelligence** — a continuously-trained **global threat index** from open-source news (cyber attacks, conflicts, political events), category feed, **indicator ↔ feed correlation**, and automatic alerts when the index spikes.
- **Pentest** — **authorization-gated, scope-validated** nmap reconnaissance and a findings register. No auto-exploitation, no DoS. Built for companies to test **their own** systems under written authorization.
- **Malware** — PE/ELF + APK + Office/PDF analysis, YARA, packing detection, VirusTotal reputation; IOCs flow into Threat Intelligence.
- **ML / Vision / Aviation** — anomaly engines (network/behaviour/deep fusion), YOLOv8 vision with feedback learning, live ADS-B aviation intelligence with emergency-squawk alerts.

### Advanced
- **PHANTOM Steganography** — LSB chi-square (Pairs-of-Values) and RS analysis on **decoded pixels** (not raw bytes), real **LSB payload extraction**, JPEG scan-data heuristics, and **DNS-tunneling detection in PCAP**.
- **SPECTRE Cloud** · **NEXUS Graph** (PageRank/Louvain criminal-network mapping) · **GHOST Memory** · **ORACLE Predictive**.

### Platform
- **API Marketplace** — buy individual modules or combos, consume via `X-API-Key`, with per-module usage metering.
- **Crypto · Export · Billing · Audit** — hashing/entropy/cipher tools, court-ready exports, an append-only audit trail, and self-serve billing.

---

## Pricing — founder pricing · 14-day free trial

| Plan | Price | For |
|------|-------|-----|
| **Starter** | **€49/mo** | Investigators & freelancers |
| **Professional** | **€149/mo** | Growing agencies |
| **Business** | **€399/mo** | Professional teams |
| **Government** | **Contact** | Law enforcement, institutional |

**Prefer à la carte?** Buy single modules via API from **€39/mo**, or combos:
**Threat Suite €249** · **Forensics Suite €299** · **Intelligence Suite €219** · **Sovereign (all-access) €690**.

Every plan and module starts with a **14-day free trial**. Founder pricing for early customers.
→ Live pricing: [forensicnexus-frontend.vercel.app/plans](https://forensicnexus-frontend.vercel.app/plans)

---

## Accountability & authorized use

- **Tamper-evident chain of custody** — SHA-256 hashing, operator attribution, and an **append-only audit trail** that survives redeploys.
- **Authorized use only** — device-access operations require a registered warrant reference; the pentest module **validates and enforces engagement scope** and refuses out-of-scope targets. No auto-exploitation, no abuse tooling.
- **Standards** — designed around **ISO/IEC 27037** and **NIST SP 800-86** guidance. *Formal certification is a roadmap item, not a current claim.*

## Tech

React 18 · TypeScript · Vite frontend · FastAPI (Python) · SQLAlchemy async · Postgres/Supabase · Anthropic Claude for grounded case summaries. Optional native workers (Rust/C/C++) for hashing and USB.

**Repos:** [backend](https://github.com/adailtoncunha32/forensicnexus-backend) · [frontend](https://github.com/adailtoncunha32/forensicnexus-frontend)

---

## Get started

**[▶ Start your free trial](https://forensicnexus-frontend.vercel.app/plans)** · **[Book a demo](mailto:contact@forensicnexus.io?subject=ForensicNexus%20demo)** · [contact@forensicnexus.io](mailto:contact@forensicnexus.io)

*© 2026 ForensicNexus · Proprietary software. For lawful, authorized investigation and security testing only.*
