i need to build a website For the HealGen Build a complete, production-ready web application called "PolyMed Care Portal — Multimodal Prescription & Active-Salt Explainer" designed specifically for Indian patients, elderly users, and family caregivers.

Core Purpose & Clinical Safety Guardrails
Role: Medication literacy, active-ingredient safety checker, and family caregiver assistant.
Strict Medical Disclaimer: Always display a prominent safety banner stating: "Health literacy & caregiver aid only — never diagnoses or modifies dosages. Confirm all details with a licensed doctor or pharmacist."

Privacy First: Include a confirmation checkbox reminding users to crop or hide personal patient details (name, phone number, address) before scanning. Do not store sensitive patient photos permanently on external servers.

Visual Aesthetic & Layout
Theme: Sleek, high-contrast medical dark mode (#070b14 slate background, #0f172a elevated cards, #1e293b subtle borders, sky-blue #0284c7 and indigo #4f46e5 primary accents, emerald green for safe/completed states, and pulsing red borders for active-salt overdose alerts).
Zero-Friction Demo Mode: Include a "Load Demo Sample" button in the hero section that immediately loads a realistic Indian prescription scenario (e.g., Dolo-650, Crocin Advance 500, Pantocid 40, Augmentin 625 Duo, and Candid-V Ointment) with an active Paracetamol overlap warning—fully localized when English or Hindi is selected—so judges or visitors can test every feature in 1 click without needing an API key or photo.

Multimodal Input & Gemini AI Engine
Photo Upload & Compression: Support drag-and-drop and click-to-upload (plus mobile camera capture capture="environment") for multiple PNG, JPG, or WEBP prescription and blister-strip photos. Compress images client-side (max 768px, JPEG quality ~0.78) for fast 2–4 second multimodal scanning.

Model Reliability & Failover: Use Google Gemini (gemini-2.5-flash primary with automatic fallback to gemini-2.5-flash-lite and gemini-2.0-flash). Support both a secure backend/proxy API key (so visitors need zero setup) and an optional manual session-only API key input bar.

Comprehension Levels: Let users switch between 3 explanation levels:

Simple / Elderly-Friendly: Everyday words, short sentences, zero medical jargon.

Standard / Family Caregiver: Clear everyday language + active salt names.

Detailed / Medical Literacy: Full pharmacological context & mechanism details.

Full 7-Language Localization & Phonetic Voice Guide
Supported Languages: English, Hindi (हिन्दी), Kannada (ಕನ್ನಡ), Tamil (தமிழ்), Malayalam (മലയാളം), Telugu (తెలుగు), and Marathi (मराठी).

Full UI Translation: Switching the language dropdown immediately translates the entire web interface (hero text, upload labels, buttons, table headers, tab titles, disclaimers, and placeholders) as well as all AI-generated medical explanations.

Phonetic Script Rule for Regional TTS: When an Indian regional language is selected, instruct Gemini to write the spoken audio_summary completely in native regional script, transliterating English brand names (e.g., Dolo-650) and numbers phonetically into that script so browser Text-to-Speech pronounces them naturally without stumbling over Latin letters or digits.

3 Clean Named Voice Personas per Language: Instead of exposing dozens of raw OS voices, provide 3 curated, friendly personas per language (e.g., Aarav — Calm & Clear (Default), Diya — Warm Caregiver, Rohan — Slow & Elderly-Friendly at 0.78x speed, with localized regional names for Hindi, Kannada, Tamil, Malayalam, Telugu, and Marathi) mapped automatically to the cleanest matching system voice with sentence-by-sentence playback and Play/Stop controls.

Core Clinical Intelligence & 4-Tab Workspace
Organize the generated care plan into a top Active-Salt Overlap Alert Banner (pulsing red warning whenever two medicines share an active ingredient like Paracetamol or an NSAID, or green confirmation if none overlap) followed by 4 instant client-side tabs:

Tab 1: Daily Schedule, Dose Tracker & Audio Guide

Structured Meal-Timing Table: Columns for Time of Day (Morning, Afternoon, Night), Before Food, After Food, and Today's Dose Log.

Clinical Formatting Rules:

If a once-daily medicine (OD/ODAC/ODPC) does not specify morning vs. night, default it logically and explicitly tag it (defaulted — confirm time).

Consistently include duration tags (e.g., (for 5 days)) across every row in the schedule.

Dedicated Topical / External Callout: Keep ointments, creams, and drops out of the oral food table and display them in a separate "External / Topical (Do Not Swallow)" callout banner below the table.

Interactive Daily Dose Log: Clickable Mark Taken button on every schedule row that timestamps intake (✓ Taken (08:15 AM)) in localStorage keyed by today's date so caregivers never double-dose.

1-Click WhatsApp Caregiver Share: Button (https://wa.me/?text=...) that formats active-salt alerts, daily meal timings, and topical notes into a clean emoji-structured WhatsApp message for family forwarding.

Phone Calendar Alarms (.ics): Button that generates and downloads a 7-day recurring .ics calendar file with 5-minute alerts for every meal slot so iPhone and Android users can add phone alarms in 1 tap.

Spoken Caregiver Audio Guide + Doctor Questions: Side-by-side cards with the localized spoken summary, voice persona selector, Play/Stop controls, and 3 tailored questions to ask the doctor or pharmacist.

Tab 2: Detected Medicines & Active Salts

Clean responsive cards for each medicine showing:

Brand Name & Active Salt Pill Badge

Visual Pill / Strip Appearance Badge (color, shape, imprint, or packaging cue extracted from the photo for elderly pill identification)

Purpose & Timing

Food & Spacing Tip Badge (e.g., "Avoid milk/antacids within 2 hours", "Swallow whole 30 mins before eating", "Do not combine with Dolo-650")

Jan Aushadhi / Generic Salt Insight (exact generic salt name to ask a pharmacist/Jan Aushadhi Kendra for affordable generic equivalence, framed safely for pharmacist verification)

OCR Scan Confidence Note

Tab 3: Ask Follow-Up Questions (Text + Hands-Free Elderly Voice Input)

Multi-turn Q&A chat grounded in the scanned prescription report (fast text-only context without re-uploading images on every message).

Prescription-Aware Suggested Question Chips: Dynamically generated from the user's actual scanned medicines and schedule slots (never hardcoded).

Hands-Free Voice Mic Input (SpeechRecognition): A microphone button next to the chat input configured to the selected Indian language so elderly users can speak their question instead of typing.

Tab 4: Printable Fridge Care Card

High-contrast, light-background print preview showing active-salt warnings, the oral meal schedule, topical applications, detected medicines/salts, and safety disclaimer.

Download & Print Button: Exports a standalone, print-optimized polymed_fridge_card.html file with @media print styling and a 1-click Print / Save as PDF button for kitchen/fridge display.

Bonus Multi-Prescription "Home Medicine Cabinet" Mode:

Allow saving scanned prescriptions to a persistent local "Home Medicine Cabinet" so caregivers can cross-check active-salt overlaps and cumulative daily dosages across multiple doctors' prescriptions at once.






 

Which Gemini key should power the built-in scanning so visitors need zero setup?

My own Gemini key

When the first Gemini model is busy or fails, what should the visitor see?

Switch models silently

Any additional info?

is it possible to switch to the emergent API if the google API fails in like 5 secs












Queue all (user approved all four builder suggestions): A. Per-Medicine Dose Log: let caregivers mark each medicine taken separately, so a skipped tablet in a slot is visible. B. Auto Re-Explain: rewrite the report automatically when language or level changes, no extra tap needed. C. Faster Backup Scans: reduce wait time when Google is busy and the Emergent backup key takes over. D. Refill Countdown: show days of medicine remaining and warn the family two days before the course ends.














Cabinet Countdown: Show days left for every saved prescription inside the Medicine Cabinet, so all doctors' courses are tracked in one place

Missed Dose Nudge: Show a gentle reminder on the schedule when a slot's time has passed and medicines are still unmarked

Fridge Card Image: Let families save the fridge card as a picture to share on WhatsApp straight from the phone

Larger Text Mode: Add a one-tap bigger-text button so elderly users can read the schedule without zooming on a phone














Apply these focused UI/UX and feature updates to the existing PolyMed Care Portal app (keep the existing Gemini API/model setup unchanged, and skip the automated browser testing agent after building to save credits — just verify the build compiles cleanly):
Part A — Bug Fixes & UI/UX Polish
Fix WhatsApp Share on Desktop/Web: Replace api.whatsapp.com links with https://web.whatsapp.com/send?text=... (opened with target="_blank" rel="noopener noreferrer") AND automatically copy the formatted WhatsApp summary to the user's clipboard with a "Copied! Ready to paste in WhatsApp" toast so it works seamlessly even if WhatsApp Web is blocked in an iframe or browser.
Translate ALL Dosage & Duration Strings When Language Changes: When switching to Hindi, Kannada, Tamil, Malayalam, Telugu, or Marathi, ensure every schedule dosage instruction and duration tag (such as "1 tablet", "2 teaspoonfuls mixed in one glass of water", "(for 5 days)", "(continue until told otherwise — confirm)") is also translated into the selected regional language—never left in English.
Move Disclaimer Banner to Bottom & Make It Slim: Remove the thick orange banner from the top of the screen and place it as a compact, single-line subtle footer notice at the bottom so the main workspace loads right at the top.
Explain Simple | Standard | Detailed + True Site-Wide Simple Mode:
Show a clear 1-line description right below the Simple | Standard | Detailed toggle (e.g., Simple: Plain everyday words across the whole website for elderly users, Standard: Clear family guide + ingredient names, Detailed: Full medical context).
When Simple is selected, simplify the entire website's UI copy too—replace terms like "blister strips" with "tablet packets", "active salts" with "main ingredients", and "pharmacological" with "medicine details".
Add A- / A+ Text Size Buttons: Add compact A- and A+ font-scaling buttons in the top bar (adjusting root font size smoothly between 14px, 16px, 18px, and 20px) for elderly readability.
Show Scanned Source Prescription in Demo Mode: When "Load Demo Sample" is clicked, generate and display a realistic sample Indian prescription + medicine strip preview image with a "View Scanned Source Prescription" thumbnail/modal so judges can compare the raw prescription directly against the extracted schedule.
Explain Jan Aushadhi & Add Pill SVG Icons:
Next to "Jan Aushadhi / generic salt", add a (?) info tooltip/popover stating: "Jan Aushadhi Kendras are Govt. of India pharmacies selling quality-tested generic medicines with the exact same main ingredient at 50–80% lower cost."
Next to "Looks like:" on each medicine card, render a small inline SVG icon matching the pill's shape and color.
Make Medicine Cabinet Self-Explanatory:
Show a dismissible 1-time welcome card the first time the Medicine Cabinet opens explaining what it does ("Save prescriptions from different doctors here to check if total daily ingredients overlap across your whole home cabinet"), plus a permanent (i) info button in the cabinet header.
Change the save input placeholder to "Nickname this prescription (e.g., Dad's Fever Slip)".
Part B — 3 Standout Competition Features
Doctor-Visit 30-Second Summary ("Clinic Mode"): Inside the Medicine Cabinet, add a "30-Sec Doctor Summary" button that opens a clean, high-contrast 1-screen "Current Medications List" card (showing active ingredients, daily totals, and start dates) designed to hand directly to a doctor during a quick OPD consultation.
"Missed Dose — What Should I Do?" Simulator: On every schedule row and medicine card, add a "Missed a dose?" button that opens a clear, safe timing guide (explaining general rules like taking as soon as remembered unless the next scheduled dose is within 2 hours, never doubling up, and flagging antibiotics/critical meds to confirm with a pharmacist).
1-Tap WhatsApp Refill Alert on Low-Stock Medicines: In the Medicine Cabinet course countdown, next to any medicine with Days left <= 2, add a "Remind Family to Refill" button (opening web.whatsapp.com + copying to clipboard) pre-filled with the medicine name, active salt, and remaining days.














Make two tiny header label additions only (keep everything else unchanged and skip the automated browser testing agent to save credits):
1. Above the Simple | Standard | Detailed pill toggle in the top header, add a subtle uppercase micro-label: "Explanation Depth:" (or "Language Simplicity:").
2. Above the A- | A+ pill button in the top header, add a matching subtle uppercase micro-label: "Text Size:".












Add a new "Scan & Explain (X-Ray / MRI)" tab in PolyMed Care Portal while keeping all existing features and UI intact (skip the automated browser testing agent to save credits):
1. Immediate Disclaimer Pop-Up on Tab Open + Persistent "i" Info Button:
   - As soon as the user opens the "Scan & Explain (X-Ray / MRI)" tab, automatically display a clean pop-up modal disclaimer with an "I Understand & Continue" button:
     "Health Literacy & Educational Aid Only — This tool explains medical terms and general visual notes in plain language. It does NOT diagnose conditions, determine causes, or replace a radiologist or doctor. Always confirm results with a licensed physician."
   - Do NOT put a bulky warning banner across the top of the tab. Instead, place a subtle circular "i" info button in the tab header (matching the Medicine Cabinet style) that re-opens this exact disclaimer pop-up whenever clicked.
2. Image Upload, View-Type Selector & Image Quality Check:
   - Include a quick scan-type selector (X-Ray / MRI / Auto-Detect) and an optional body-region/view note field (e.g., Chest, Knee, Spine) plus a 1-tap "Load Demo X-Ray/MRI Sample" button so evaluators can test without uploading a file.
   - Before or alongside generating the explanation, run an Image Quality & Clarity Check: if the uploaded photo is blurry, heavily glared, cropped, or missing visible labels/orientation markers, display a clear gentle notice ("Low image clarity or cropped view detected — visual notes may be incomplete; bring the original film or DICOM report to your doctor") while still showing safe educational explanations.
3. Safe Plain-Language Output & Doctor Checklist:
   - Return structured, plain-language output strictly in these three sections (never diagnosing or guessing causes):
     * "Terms & Areas Mentioned" (plain-language explanation of anatomical regions or labels visible)
     * "General Educational Notes" (neutral, non-diagnostic visual observations for understanding)
     * "Questions to Ask Your Doctor" (3–5 checkable questions a patient or caregiver can bring to their appointment, with a 1-tap "Copy Questions for Doctor" button)
   - Respect the active Explanation Depth (Simple / Standard / Detailed), Larger Text Mode (A- / A+), and selected language.
  


