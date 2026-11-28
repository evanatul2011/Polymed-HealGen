# Polymed-HealGen

# PolyMed Care Portal (HealGen)

**PolyMed Care Portal** is a health-literacy and caregiver-support web application built for **SparkX 2026–27 (Theme S2: HealGen – Accessible Healthcare & Diagnostics)**. Designed with a safety-first, non-diagnostic approach, it helps patients, family caregivers, and elderly users make sense of medical prescriptions, medicine strips, and imaging scans in everyday language—while flagging potential active-salt overlaps and preparing clear questions for doctor visits.

## Key Features

* **Prescription & Strip Scanner + Active-Salt Overlap Detection:** Upload prescription or medicine strip photos (or test with a 1-tap demo sample) to extract medicine details, view daily schedule slots, and catch duplicate or overlapping active salts (such as repeated Paracetamol across multiple medicines).
* **Scan & Explain (X-Ray / MRI) Tab:** Dedicated educational view for X-ray and MRI images featuring an immediate disclaimer pop-up on tab entry, a persistent `i` info button, an image quality & clarity check (flagging blurry/cropped views or missing orientation markers), and structured plain-language output covering **Terms & Areas Mentioned**, **General Educational Notes**, and **Questions to Ask Your Doctor** (with a checklist and 1-tap copy support).
* **Accessibility & Multilingual Support:** Switch between **Simple**, **Standard**, and **Detailed** explanation depths, adjust text size (`A-` / `A+`), switch display languages, and use spoken caregiver audio guidance.
* **Medicine Cabinet, Doctor Summary & Fridge Card:** Save scanned items to a local **Medicine Cabinet**, generate a concise summary for medical appointments, and keep quick-reference caregiver notes handy.
* **Privacy-First Local Storage:** Prioritizes local browser storage (`localStorage`) and device-side handling with privacy reminders so sensitive personal health details are not needlessly stored on external servers.

## Responsible AI & Safety Guardrails

* **Strictly Non-Diagnostic:** PolyMed Care Portal is an educational and health-literacy aid—it does **not** diagnose medical conditions, confirm injuries/sprains/tears, alter dosages, or replace a licensed physician, radiologist, or pharmacist.
* **Clinician Confirmation First:** All explanations and checklists are structured to support informed conversations with qualified healthcare professionals.

## Tech Stack & Deployment

* **Frontend & Builder:** React web application built and previewed via Emergent (`active-salt--07rb23i5.preview.emergentagent.com`)
* **Live Portal:** `https://active-salt.emergent.host`
* **State & Storage:** Browser `localStorage` for local-first persistence
