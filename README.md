# AeroFit — Aeromedical Fitness Evaluation
> Source-grounded AI that decides whether a pilot is fit to fly — with a traceable verdict, not a black box.

![Private source](https://img.shields.io/badge/source-private-8A1C1C?style=flat-square)
![Case study](https://img.shields.io/badge/type-case%20study-C8A24A?style=flat-square)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-C8A24A?style=flat-square)
![ML](https://img.shields.io/badge/Machine%20Learning-F7931E?style=flat-square)

<p align="center">
  🚀 <a href="https://aero-fit-eight.vercel.app"><b>Live demo</b></a>
</p>

![Hero](assets/hero-aerofit.jpg)

## The problem

Aeromedical fitness decisions carry legal and clinical consequence: a wrong "fit" can put a pilot in a cockpit who shouldn't be there. Most ML systems answer with a score and no justification — AeroFit answers with a verdict **and its sources**.

## What it does

Ingests lab results, psychological exams and real-time sensor signals (blood pressure, heart rate, oxygenation), reasons over a dataset built from national and international aeronautical and medical regulation, and returns a **fit / fit-with-restrictions / unfit** verdict with its sources, risks, justification and specialist referral. Tuned to **0.65 recall on the risk class** — a missed risk costs more than a false alarm. Human-in-the-loop by design: it refers to a specialist even when the verdict is "fit," and the pilot controls deletion of their own data.

## Architecture

```mermaid
flowchart LR
  I[Lab · psychological · real-time sensors] --> E{Dual engine}
  E -->|air-gapped RAG| R[Regulation corpus<br/>DGAC / OACI]
  E -->|ML| M[Risk classifier<br/>recall-tuned]
  R --> V[Verdict + sources + risks]
  M --> V
  V --> S[Specialist referral]
```

## Results & impact

- **0.65 recall** on the risk class (safety-first tuning)
- 6 phases from research to validation
- Final-year engineering capstone

## Stack

Python · RAG · Ollama · scikit-learn · real-time sensor ingestion

## Source & access

Private (product IP). Happy to walk through the architecture or grant **read-only access on request**.
Open technical core: [Medical-Aeronautic RAG Engine](https://github.com/akhanER2000/Local-RAG-medical-assistance-aeronautic).

**Contact:** [Portfolio](https://cs-portfolio-psi-topaz.vercel.app) · [LinkedIn](https://www.linkedin.com/in/akhan-espinoza) · castrolorenzosegundo@gmail.com

---
<sub>Docs © 2026 Akhan Lorenzo Espinoza Rojas — All rights reserved.</sub>
