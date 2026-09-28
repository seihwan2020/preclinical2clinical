# Preclinical-to-Clinical Dose Design System

**English** | [한국어](README.ko.md)

A web tool that translates preclinical animal data into human equivalent doses (HED) and a maximum recommended starting dose (MRSD), and drafts Phase 1/2 study designs and dose-escalation strategies on a single screen.

> [!WARNING]
> **For preclinical and clinical research use only.** This tool must not be used as the basis for actual human dosing decisions, diagnosis, treatment, or any other medical practice. All results must be reviewed by qualified experts.

## Getting started

No installation is required.

**Use it on the web:** https://seihwan2020.github.io/preclinical2clinical/

**Use it offline:**
1. Download [`index.html`](index.html) from this repository.
2. Open it in a browser (Chrome, Edge, Safari or Firefox).

All code and the charting library are bundled into that one file, so it **works without an internet connection**.

## Features

**Preclinical to human dose translation**
- Enter NOAEL, MED, ED50 and STD10 / HNSTD for mouse, rat, dog and monkey
- HED conversion based on body surface area (Km), with automatic selection of the most sensitive species
- MRSD calculation with a safety factor (SF), increased when toxicity concerns are selected
- Indication-specific paths: healthy volunteers / patients / oncology (STD10/10 or HNSTD/6) / biologics (MABEL)

**Clinical study design**
- Phase 1a SAD: dose per cohort, formulation combinations, placebo allocation, sentinel dosing
- Phase 1b MAD: multiple dosing, steady state (Css), accumulation ratio (Rac), loading dose
- Dose-escalation methods: Modified Fibonacci · 3+3 Design · Accelerated Titration
- Mark DLTs per cohort to recalculate the MTD, MAD, PK and Phase 2 doses automatically
- Food-effect PK study and suggested Phase 2 dose arms (low / mid / high, RP2D)
- Oral / intravenous (IV) / subcutaneous (SC) / intramuscular (IM) routes and formulation strengths

**Results and export**
- Dose-escalation curve, HED comparison across species, and a human dose-range visualization
- Recommendations based on the analysis
- CSV export, draft study protocol (text), print / PDF
- 10 sample datasets: ideal · oncology · peptide · mAb · CNS · cardiovascular · antibiotic · immunomodulator · diabetes · natural product

**Languages:** Korean · English · Japanese · Chinese. Switch the language at the top of the page; charts and exported files follow the selected language.

## Calculation basis

- HED conversion: FDA Guidance for Industry, *Estimating the Maximum Safe Starting Dose in Initial Clinical Trials for Therapeutics in Adult Healthy Volunteers* (2005)
  - Km factors: mouse 3, rat 6, monkey 12, dog 20, human 37
  - HED (mg/kg) = animal dose (mg/kg) × (animal Km ÷ human Km)
- MRSD = HED (NOAEL) ÷ safety factor (default 10)
- Oncology starting dose: 1/10 of the rodent STD10 or 1/6 of the non-rodent HNSTD (the approach recommended by ICH S9)

## Data and privacy

- All calculations run inside your browser. Nothing you enter is sent anywhere.
- Inputs and the language setting are stored only in your browser's local storage (localStorage).

## Technical details

- A single HTML file (HTML · CSS · JavaScript)
- Charts: [Chart.js](https://www.chartjs.org) 4.4.1 (MIT License), bundled inside the file with its license notice kept

## Contact

SEIHWAN Inc. · seihwan2022@gmail.com

© 2025 SEIHWAN Inc. All rights reserved.
