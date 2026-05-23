# 🔍 VeriLens — Multimodal Document Integrity Engine

> **AI-Powered Real-Time Forgery Detection for Banking Underwriting**  
> Built for **SuRaksha Hackathon by Canara Bank** · Theme: Real-time Anomaly Detection

---

## 🚨 The Problem

Document fraud in Indian banking — forged land records, fabricated ITRs, tampered legal agreements — costs banks an estimated **₹7,000+ crore annually**.

Underwriting still depends on **manual document review**:
- 3–4 hours per loan application
- 30–40% of sophisticated forgeries missed
- Zero detection of pixel-level tampering or semantic inconsistencies
- No system that learns from evolving fraud patterns

**No existing Indian banking solution combines computer vision + document AI + knowledge graphs + government API validation into a single pipeline.**

---

## 💡 Solution: VeriLens

VeriLens is an **8-module AI system** that analyzes any uploaded banking document across four detection layers simultaneously, then runs four exclusive intelligence modules — delivering a complete Underwriter Intelligence Report in **under 60 seconds**.

```
Input Document (PDF / Scan / Image)
         ↓
   Pre-Processing Pipeline
         ↓
┌─────────────────────────────────────────────────────┐
│         CORE DETECTION — 4 Layers (parallel)        │
│  Layer 1: Pixel Forensics     (EfficientNet-B4)     │
│  Layer 2: Semantic Verify     (LayoutLMv3 + spaCy)  │
│  Layer 3: Knowledge Graph     (Neo4j + NetworkX)    │
│  Layer 4: Public Records      (MCA21 + CERSAI APIs) │
└─────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────┐
│     EXCLUSIVE INTELLIGENCE — 4 Modules              │
│  Module 5: Fraud Narrative Reconstruction           │
│  Module 6: Forgery Evolution Graph                  │
│  Module 7: Synthetic Fraud Simulation Engine        │
│  Module 8: Trust DNA Score (6-axis fingerprint)     │
└─────────────────────────────────────────────────────┘
         ↓
   Underwriter Intelligence Report + Heat-map + Alert
```

---

## 🔬 Module 1–4: Core Detection Engine

### Layer 01 — Pixel Forensics
**Model:** EfficientNet-B4 (fine-tuned on synthetic forgery dataset)

Analyzes the raw document image for tampering **invisible to the human eye**:
- Copy-paste artifacts and splicing boundaries
- Font rendering inconsistencies (different sources pasted together)
- Noise pattern breaks where content was inserted
- Metadata and EXIF anomalies (modification timestamps, device fingerprints)

---

### Layer 02 — Semantic Cross-Verification
**Model:** LayoutLMv3 (Microsoft) + spaCy NER + Custom financial entity extractor

Extracts all structured data and checks **internal document consistency**:
- Loan amount on page 1 vs repayment schedule on page 3
- Stamp date predating the issuing authority's establishment
- Borrower name inconsistency across pages
- Date logic violations (signed before issuing date)

---

### Layer 03 — Knowledge Graph Anomaly Detection
**Stack:** Neo4j + NetworkX + PyTorch Geometric

Maps all document entities into a **knowledge graph** and runs graph traversal algorithms:
- Same property sold to two different people in overlapping periods
- Circular ownership chains indicating shell entity involvement
- Guarantor who is also the primary borrower
- Impossible legal relationships between entities

---

### Layer 04 — Public Record Cross-Referencing
**APIs:** MCA21, CERSAI, Land Registry Portals, UIDAI (where accessible)

Validates document claims against **live government databases**:
- Does this company registration number exist in MCA21?
- Is there an existing charge/lien on this property in CERSAI?
- Does the stated owner match land registry records?

---

## ⚡ Module 5–8: Exclusive Intelligence Modules

> These are what make VeriLens unique. No existing Indian banking system has built all four of these.

---

### Module 05 — Fraud Narrative Reconstruction 🔴 EXCLUSIVE

**Stack:** LLM (Claude / GPT) + SHAP attribution + Timeline analysis

Instead of just flagging fraud, VeriLens **reconstructs how the fraud was committed** — like a forensic investigator writing a case report.

**Example output:**
```
"The signature region on page 4 shows pixel noise divergence from the 
surrounding page — consistent with digital cloning from a separate document. 
File metadata indicates modification 3 days after the notarization date on 
page 1. Knowledge graph analysis reveals a circular ownership transfer: 
Entity A → Entity B → Entity A, executed within a 6-month window — 
a pattern consistent with shell entity-based property inflation fraud."
```

This makes VeriLens feel like **cyber-forensics-level intelligence** — not a fraud detector, a fraud investigator.

---

### Module 06 — Forgery Evolution Graph 🟢 EXCLUSIVE

**Stack:** HDBSCAN clustering + Temporal graph analysis + Time-series ML

The system **learns how fraud evolves over time**:
- Clusters similar fraud patterns across all analyzed documents
- Tracks emergence of new forgery techniques
- Generates a **Fraud Threat Intelligence Feed** alertable across bank branches
- Identifies when a new fraud tactic is spreading before it becomes widespread

This transforms VeriLens from a document checker into a **national fraud observatory**.

---

### Module 07 — Synthetic Fraud Simulation Engine 🟠 EXCLUSIVE

**Stack:** CTGAN + Adversarial generation + Diffusion-based document synthesis

VeriLens **generates its own synthetic forged documents** to continuously retrain and stress-test itself:
- Acts as both attacker (generating new forgery tactics) and defender (improving detection)
- Simulates adversarial fraud attempts the system hasn't seen before
- Creates a self-improving training loop — no new real fraud data needed
- Enables bank-wide stress testing of fraud detection robustness

**The only fraud detection system in India that improves itself automatically.**

---

### Module 08 — Trust DNA Score 🟣 EXCLUSIVE

**Stack:** Multi-axis ensemble scoring + 6-dimensional profiling

Every document receives a **6-axis Trust DNA fingerprint** — like a credit score, but for document integrity:

| Axis | Description |
|------|-------------|
| Tamper Probability | Likelihood of pixel-level manipulation |
| Entity Reliability | Trustworthiness of named entities in public records |
| Metadata Trust | Consistency of file metadata with claimed dates/sources |
| Ownership Consistency | Validity of property/ownership chain |
| Anomaly Density | Concentration of detected irregularities |
| Legal Authenticity | Match against known legal document templates |

Underwriters see exactly **which dimension is failing and why** — not just a pass/fail flag.

---

## 📤 System Output

### 1. Underwriter Intelligence Report (PDF)
- Overall fraud risk score (0–100) with confidence interval
- Per-layer findings with evidence
- Trust DNA fingerprint visualization
- Fraud narrative in plain English
- Recommended action: **Approve / Manual Review / Reject**

### 2. Visual Heat-map Overlay
- Original document with suspicious regions highlighted at pixel level
- Underwriters see exactly what was tampered, where, and with what confidence

### 3. Fraud Threat Intelligence Feed
- Cross-branch pattern alerts
- Emerging forgery tactic reports
- Evolution graph updates
- Shareable across Canara Bank's branch network

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Pixel Forensics | EfficientNet-B4, PyTorch, OpenCV |
| Document AI | LayoutLMv3, spaCy, Tesseract, PyMuPDF |
| Knowledge Graph | Neo4j, NetworkX, PyTorch Geometric |
| Anomaly Scoring | Isolation Forest, SHAP, Scikit-learn |
| Fraud Narrative | LLM API + Chain-of-thought prompting |
| Simulation Engine | CTGAN, Adversarial GAN, Diffusion models |
| Backend | FastAPI, Celery, Redis, PostgreSQL |
| Frontend | React, Tailwind CSS, PDF.js, D3.js |
| Infrastructure | Docker, Kubernetes, REST API |
| Government APIs | MCA21, CERSAI, Land Registry portals |

---

## 📊 Impact

| Metric | Before VeriLens | After VeriLens |
|--------|----------------|----------------|
| Verification time | 3–4 hours/application | < 2 minutes |
| Fraud detection rate | ~60–70% (manual) | 90%+ (AI-assisted) |
| Post-disbursement fraud | ₹7,000Cr+ annually | Significantly reduced |
| Underwriter workload | High, error-prone | Assisted, explainable |
| System improvement | Static | Self-improving |

---

## 🔌 Integration

VeriLens exposes a **REST API** that integrates into any existing Loan Origination System (LOS) with zero workflow disruption:

```bash
POST /api/v1/analyze
Content-Type: multipart/form-data
Body: { document: <file>, document_type: "land_record" }

Response: {
  fraud_risk_score: 73,
  trust_dna: { tamper: 87, entity: 63, metadata: 93, ... },
  narrative: "Signature cloned from external document...",
  recommendation: "MANUAL_REVIEW",
  heatmap_url: "...",
  report_pdf_url: "..."
}
```

---

## 📋 Evaluation Criteria

| Criteria | How VeriLens Addresses It |
|----------|--------------------------|
| **Relevance** | Directly solves land record + legal doc + financial statement forgery in underwriting |
| **Innovation** | 8-module fusion never built before in Indian banking; 4 exclusive modules |
| **Feasibility** | All open-source, synthetic training data, standard stack — buildable in 1 month |
| **Impact** | ₹7000Cr fraud, 4hr→2min verification, REST API plug-in, cross-branch intelligence |
| **Clarity** | 8 clearly defined modules, each with specific model, input, output, use case |

---

## 🗂️ Repository Structure (Planned)

```
verilens/
├── core/
│   ├── pixel_forensics/        # EfficientNet-B4 model + inference
│   ├── semantic_verify/        # LayoutLMv3 + NER pipeline
│   ├── knowledge_graph/        # Neo4j schema + graph algorithms
│   └── public_records/         # MCA21, CERSAI API integrations
├── intelligence/
│   ├── fraud_narrative/        # LLM chain-of-thought module
│   ├── evolution_graph/        # Temporal clustering + threat intel
│   ├── simulation_engine/      # CTGAN + adversarial generation
│   └── trust_dna/              # 6-axis scoring system
├── api/                        # FastAPI backend + Celery workers
├── frontend/                   # React underwriter dashboard
├── data/
│   ├── synthetic/              # Generated training data
│   └── samples/                # Sample anonymized test documents
└── docs/                       # Architecture diagrams + API docs
```

---

*Built for SuRaksha by Canara Bank — Real-time Anomaly Detection Track*  
*VeriLens: Because document fraud shouldn't survive the first 60 seconds.*
