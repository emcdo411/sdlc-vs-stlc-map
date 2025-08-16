# SDLC vs STLC — Luxury Hotel You Design, Build, Open, and Operate

[![SDLC](https://img.shields.io/badge/SDLC-end--to--end%20lifecycle-0ea5e9?style=for-the-badge)](#)
[![STLC](https://img.shields.io/badge/STLC-embedded%20quality%20discipline-22c55e?style=for-the-badge)](#)
[![Agile](https://img.shields.io/badge/Agile-shift--left%20testing-f59e0b?style=for-the-badge)](#)
[![DevOps](https://img.shields.io/badge/DevOps-CI%2FCD%20%26%20Monitoring-8b5cf6?style=for-the-badge)](#)

---

## Table of Contents

* [Core Idea](#core-idea)
* [Phase Mapping (Hotel Analogy)](#phase-mapping-hotel-analogy)
* [Diagram 1 — Embedded STLC Across SDLC (Flowchart)](#diagram-1--embedded-stlc-across-sdlc-flowchart)
* [Diagram 2 — SDLC/STLC Overlap Timeline (Gantt)](#diagram-2--sdlcstlc-overlap-timeline-gantt)
* [Workflows & Artifacts (STLC by Phase)](#workflows--artifacts-stlc-by-phase)
* [How to Use This in a Post](#how-to-use-this-in-a-post)

---

## Core Idea

**SDLC** covers the *entire* lifecycle of the hotel (from site selection to daily operations and renovations). **STLC** is the *embedded quality discipline* that spans the lifecycle—planning, inspecting, testing, and monitoring every system *before, during, and after* opening.

> This framing aligns with modern Agile/DevOps practices (iterative testing, CI/CD, observability). In traditional waterfall, STLC activities may appear more sequential, but they still map to the same phases.

---

## Phase Mapping (Hotel Analogy)

| Hotel Stage           | SDLC Focus                         | STLC Focus                                                                                             |
| --------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Concept & Codes       | Vision, budget, constraints        | Requirement testability, acceptance criteria, **Requirement Traceability Matrix (RTM)**, risk register |
| Blueprints            | System architecture & integrations | Test strategy, test plans/cases/scripts, test environments, **synthetic data**, traceability           |
| Build & Connect       | Construction & integration         | **Unit / Integration / System** inspections, CI automation, defect triage                              |
| Pre‑Opening           | Launch preparation                 | **Performance, Security, Accessibility, Resilience/DR**, regression & fixes, RTM updates               |
| Soft → Grand Opening  | Release                            | UAT, feedback, **go/no‑go quality gate**                                                               |
| Operations & Upgrades | Run & evolve                       | Monitoring/observability, incident mgmt, regression packs, **test closure reports**, retros            |

---

## Diagram 1 — Embedded STLC Across SDLC (Flowchart)

```mermaid
flowchart LR
  %% SDLC backbone
  subgraph SDLC[SDLC Lifecycle]
    direction LR
    P[Concept & Requirements] --> D[Design & Architecture]
    D --> I[Construction & Integration]
    I --> V[Pre-Opening Validation]
    V --> R[Release]
    R --> O[Operations & Improvement]
  end

  %% STLC activities mapped per phase
  subgraph STLC[STLC Activities (Embedded per Phase)]
    direction LR
    P1[Req Testability\nAcceptance Criteria\nRTM Draft]:::stlc --> D1[Test Strategy\nTest Plans/Cases\nEnvironments & Data]:::stlc
    D1 --> I1[Unit/Integration/System Tests\nCI Automation\nDefect Triage]:::stlc
    I1 --> V1[Perf/Sec/Accessibility/DR\nRegression & Fix Verify\nRTM Update]:::stlc
    V1 --> R1[UAT & Sign-off\nGo/No-Go Gate]:::stlc
    R1 --> O1[Monitoring/Incidents\nRegression Packs\nTest Closure & Retros]:::stlc
  end

  %% Cross-links from SDLC phases to their STLC counterparts
  P -.feeds.-> P1
  D -.feeds.-> D1
  I -.feeds.-> I1
  V -.feeds.-> V1
  R -.feeds.-> R1
  O -.feeds.-> O1

  classDef stlc fill:#d9ead3,stroke:#38761d,stroke-width:1.5px,color:#111
  classDef default fill:#e0f2fe,stroke:#0369a1,stroke-width:1.5px,color:#111
```

**How to read this:** SDLC forms the main spine. At each phase, STLC has a dedicated, structured set of activities that begin early (shift‑left), continue through delivery, and persist in operations.

---

## Diagram 2 — SDLC/STLC Overlap Timeline (Gantt)

```mermaid
gantt
  dateFormat  YYYY-MM-DD
  title SDLC/STLC Overlap Timeline (Illustrative)
  axisFormat %b

  section SDLC
  Concept & Requirements       :active, s1, 2025-01-01, 14d
  Design & Architecture        :s2, 2025-01-15, 21d
  Construction & Integration   :s3, 2025-02-05, 28d
  Pre-Opening Validation       :s4, 2025-03-05, 14d
  Release                      :milestone, s5, 2025-03-19, 1d
  Operations & Improvement     :s6, 2025-03-20, 21d

  section STLC (Embedded)
  Req Testability & RTM        :st1, 2025-01-01, 21d
  Test Strategy & Design       :st2, 2025-01-15, 35d
  Unit/Integration/System Tests:st3, 2025-02-05, 35d
  Non-Functional Test Battery  :st4, 2025-03-05, 14d
  UAT & Go/No-Go               :st5, 2025-03-18, 3d
  Monitoring & Regression      :st6, 2025-03-20, 30d
```

**How to read this:** STLC doesn’t start “after coding.” It overlaps *from day one* (testability/RTM), crescendos through construction and validation, and continues into operations (monitoring, regression).

---

## Workflows & Artifacts (STLC by Phase)

**Requirements (Shift‑Left)**

* RTM (requirements ↔ tests), acceptance criteria, risk register

**Design**

* Test strategy, test plan, test cases/scripts, environment & data plan

**Build/Integrate**

* Unit/Integration/System suites, CI pipelines, defect lifecycle (open → triage → fix → verify → close)

**Pre‑Opening**

* Performance (load/stress), security (pen‑test), accessibility (WCAG/ADA), resilience/DR; regression packs; RTM updates

**Release**

* UAT reports, exit criteria, go/no‑go quality gate

**Operations**

* Observability (logs/metrics/traces), incident management, post‑release regression, **test closure reports** & retrospectives

---

## How to Use This in a Post

* Copy the diagrams directly into your README or blog (GitHub renders Mermaid).
* For LinkedIn or slides, paste the code into a Mermaid editor to export images, then share with your commentary:

  * “STLC isn’t a phase; it’s the embedded quality discipline across SDLC. Shift‑left + monitor‑right.”

> Tip: Pair Diagram 1 (flow of work) with Diagram 2 (time overlap) to drive home *both* structure and chronology.
