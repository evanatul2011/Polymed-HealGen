# System Architecture & Safety Design — PolyMed Care Portal

## 1. High-Level Data Flow

```text
[User Image / Camera / 1-Tap Demo Sample]
       │
       ▼
[Client-Side Privacy & Compression Layer]
  ├── Personal-details crop/hide confirmation check
  └── Local browser image compression (never stored on external servers)
       │
       ▼
[Mode Router]
  ├── Mode A: Prescription & Medicine Strip Explainer
  │     ├── Multimodal AI extraction (medicine names, active salts, timing slots)
  │     ├── Active-Salt Overlap Engine (flags duplicate ingredients like Paracetamol)
  │     └── Output: Daily Schedule + Overlap Warning + Caregiver Audio + Fridge Card
  │
  └── Mode B: Scan & Explain (X-Ray / MRI Health Literacy)
        ├── Mandatory Pop-Up Safety Disclaimer + Persistent "i" Info Modal
        ├── Image Quality & Clarity Check (flags blur, cropped edges, missing L/R markers)
        └── Non-Diagnostic Output: Terms & Areas + Educational Notes + Doctor Questions
       │
       ▼
[Personalization & Accessibility Layer]
  ├── Explanation Depth: Simple / Standard / Detailed
  ├── Typography Scaling: A- / A+
  └── Multilingual Output + Spoken Caregiver Guide
       │
       ▼
[Local-First Persistence]
  └── Browser localStorage (Medicine Cabinet & 30-Second Doctor Summary)
