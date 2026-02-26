# credit_memo_workflow
Diagramming credit IC memo workflow

# Credit Investment Memo Workflow System

A structured workflow system for credit investment memo production. Maps every step an analyst takes from initial opportunity screening through IC presentation, ongoing position monitoring, and annual process review — with LLM deliverability classification, role assignments, handoff protocols, and decision gates at each step.

---

## What This Is

This system provides the analytical framework and process discipline for producing institutional-quality credit investment memos. It answers three questions for every step in the workflow:

1. **What exactly needs to happen?** — Verb + object step definitions with explicit inputs, outputs, and quality standards
2. **Who does it?** — Role assignments (Analyst, PM, Legal Counsel, Cold Reader, Ops/Trading) with RACI matrix
3. **Can an LLM help?** — Three-tier classification (Fully Deliverable / Partially Deliverable / Not Deliverable) with prompt examples

The workflow covers 12 phases from initial credit screen to annual process review:

| Phase | Name | Focus |
|---|---|---|
| 1 | Opportunity Screening & Mandate Fit | Initial screen, compliance clearance, preliminary thesis |
| 2 | Issuer & Industry Analysis | Revenue quality, competitive position, sector dynamics |
| 3 | Credit Financial Analysis | EBITDA bridge, credit ratios, covenant headroom, liquidity |
| 4 | Legal & Structural Analysis | Indenture deep-dive, LME vulnerability, structural subordination |
| 5 | Credit Modeling & Scenario Analysis | Pro forma, base/stress/bull cases, recovery, refinancing |
| 6 | Relative Value Analysis | Spread comps, historical spreads, total return matrix, OAS decomposition |
| 7 | Data Freeze Gate | Model audit, pricing verification, covenant validation, formal freeze |
| 8 | Memo Drafting | All memo sections including exit strategy, exec summary written last |
| 9 | Quality Assurance & Review | Self-review, cold reader, version stamp |
| 10 | IC Preparation & Execution | Pre-read distribution, Q&A prep, IC presentation, trade execution |
| 11 | Ongoing Position Monitoring | Recurring review against pre-established exit criteria |
| 12 | Post-Mortem — Annual Process Review | Framework accuracy review, systematic gap identification, process improvement |

---

## Repository Contents

### Guides

| File | Description |
|---|---|
| `Credit_Investment_Memo_Creation_Guide.docx` | The detailed analyst playbook. Every step has: verb+object definition, source documents, deliverable specification, best practices, LLM deliverability rating with notes, and deal killer flags. This is the "how-to" reference. |
| `Credit_LLM_Workflow_Guide.docx` | The operational workflow companion. Step tables with LLM status, RACI matrix, handoff protocols, variant branches, decision points, and **prompt examples** for every LLM-deliverable step. Designed to be used alongside the memo guide. |

### Tracker

| File | Description |
|---|---|
| `Investment_Memo_Workflow_Tracker.xlsx` | Multi-tab workbook with dashboard and per-step tracking. Columns include: Step ID, Phase, Verb+Object, Role, LLM Classification (current + future-state), Handoff Protocol, Decision Points, Variant Branches, Risk/Compliance Flags. |

### RACI Matrix

| File | Description |
|---|---|
| `Credit_RACI_Matrix.xlsx` | Responsibility assignment matrix mapping every step to roles: Analyst, Senior Analyst, PM, Legal Counsel, Compliance, Cold Reader, Ops/Trading. |

### Workflow Diagrams

| File | Description |
|---|---|
| `Credit_Comprehensive.mermaid` | **The ground truth.** Full 12-phase workflow diagram with every step, decision gate, kill path, handoff, and feedback loop. 430 lines, ~82 workflow nodes. Color-coded by LLM deliverability (green = Full, amber = Partial, red = None). |
| `credit_L0_overview.mermaid` | Compressed ~25-node overview of the full workflow. Good for presentations and orientation. |
| `credit_L1_phase01_screening.mermaid` | L1 sub-process: Phase 1 — Opportunity Screening & Mandate Fit |
| `credit_L1_phase02_issuer_industry.mermaid` | L1 sub-process: Phase 2 — Issuer & Industry Analysis |
| `credit_L1_phase03_financial.mermaid` | L1 sub-process: Phase 3 — Credit Financial Analysis |
| `credit_L1_phase04_legal.mermaid` | L1 sub-process: Phase 4 — Legal & Structural Analysis |
| `credit_L1_phase05_modeling.mermaid` | L1 sub-process: Phase 5 — Credit Modeling & Scenario Analysis |
| `credit_L1_phase06_relative_value.mermaid` | L1 sub-process: Phase 6 — Relative Value Analysis |
| `credit_L1_phase07_data_freeze.mermaid` | L1 sub-process: Phase 7 — Data Freeze Gate |
| `credit_L1_phase08_drafting.mermaid` | L1 sub-process: Phase 8 — Memo Drafting |
| `credit_L1_phase09_qa.mermaid` | L1 sub-process: Phase 9 — Quality Assurance & Review |
| `credit_L1_phase10_ic.mermaid` | L1 sub-process: Phase 10 — IC Preparation & Execution |
| `credit_L1_phase11_monitoring.mermaid` | L1 sub-process: Phase 11 — Ongoing Position Monitoring |
| `credit_L1_phase12_postmortem.mermaid` | L1 sub-process: Phase 12 — Post-Mortem — Annual Process Review |

Each L1 diagram shows the internal structure of a single phase: step sequencing, parallel branches, inner subgroups, decision gates, and loops. The L0 overview references these as sub-processes. The comprehensive diagram contains all of them in a single file.

---

## How to Use This System

### For Analysts Writing a Credit Memo

1. **Start with the Memo Guide** (`Credit_Investment_Memo_Creation_Guide.docx`) — follow it phase by phase
2. **Reference the LLM Guide** (`Credit_LLM_Workflow_Guide.docx`) for prompt examples at each step where LLM assistance is available
3. **Track progress** using the XLSX tracker
4. **Use the comprehensive diagram** to understand where you are in the workflow and what's upstream/downstream

### For Teams Implementing the Workflow

1. **Review the RACI matrix** to assign roles
2. **Walk through the comprehensive diagram** to understand decision gates, kill paths, and feedback loops
3. **Customize** — the system is designed for high-yield credit but includes adaptation notes for investment grade, distressed, and direct lending

### For Using with an LLM

The LLM Workflow Guide contains prompt examples for every step classified as Full or Partial deliverable. Each prompt specifies:
- **Source files** — what to provide the LLM (with reference to which phase produced each input)
- **Output specification** — exactly what the LLM should produce (format, length, detail level)
- **Downstream destination** — where the output goes next in the workflow
- **Review notes** — what to verify before passing output downstream, common failure modes

---

## Workflow Diagram Color Legend

The comprehensive diagram uses color to encode LLM deliverability at a glance:

| Color | Class | Meaning |
|---|---|---|
| 🟢 Green | `llmFull` | Fully LLM deliverable — LLM can produce near-final output |
| 🟠 Amber | `llmPartial` | Partially LLM deliverable — LLM assists but human completes |
| 🔴 Red | `llmNone` | Not LLM deliverable — requires human judgment, presentation, or execution |
| 🔵 Blue | `decision` | Decision gate (Go/No-Go, IC approval, covenant check) |
| 🟣 Purple | `endpoint` | Terminal node (deal killer, archive, position established) |

To render `.mermaid` files: use the [Mermaid Live Editor](https://mermaid.live), GitHub's native rendering, or any Mermaid-compatible viewer.

---

## Strategy Adaptations

The system is built for **high-yield credit** but adapts to other strategies:

| Strategy | Adaptation |
|---|---|
| **Investment Grade** | Reduce covenant/recovery depth. Increase relative value and spread duration focus. |
| **Distressed** | Add restructuring analysis (Chapter 11, DIP, plan of reorganization, claim trading). LME analysis becomes the most critical step. |
| **Direct Lending / Private Credit** | Add origination steps (term sheet negotiation, covenant structuring, collateral perfection, borrower DD). |

---

## Key Design Principles

1. **Exit criteria accumulate through analysis** — Phases 3, 5, and 6 naturally produce the thresholds that become sell discipline triggers. Phase 8 formalizes them. Phase 11 monitors against them.

2. **The data freeze gate is non-negotiable** — Phase 7 freezes the analytical dataset before drafting begins. An explicit un-freeze protocol exists for material events during drafting.

3. **Process improvement is structural** — Phase 12 (annual post-mortem) reviews the analytical framework itself, not individual positions. Outputs are institutional improvements to templates, stress parameters, and screening criteria.

4. **Credit is asymmetric** — The upside is the coupon; the downside is the principal. Every step in this system exists to protect the principal.

---

## Contributing

This is an active project. The comprehensive diagram is the ground truth — all other files are derived from or aligned to it. If you identify gaps or improvements, reference the specific phase and step number.

---

## License

Internal use. Do not distribute outside the team without authorization.
