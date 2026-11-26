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
