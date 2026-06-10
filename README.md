# AI Policy Tracker

I was trying to understand the actual AI governance landscape — not just "the EU AI Act exists" but what all the major laws and frameworks actually say and how they relate to each other. I couldn't find a simple place that had everything in one view, so I built one.

**[Live Demo →](https://aadyagoraya.github.io/ai-policy-tracker)**

---

## What it covers

12 real policy instruments across the EU, US, UK, China, and global bodies — with plain-English summaries, status (enacted / proposed / draft / withdrawn), thematic tags, and links to the actual source documents.

You can filter by jurisdiction, search across everything, and see a chronological timeline of how the regulatory landscape has developed since 2022.

---

## The policies

| Policy | Where | Status |
|---|---|---|
| EU AI Act | EU | Enacted |
| Executive Order on Safe, Secure & Trustworthy AI | US | Enacted |
| Bletchley Declaration | UK | Enacted |
| Interim Measures for Generative AI Services | China | Enacted |
| NIST AI Risk Management Framework 1.0 | US | Enacted |
| UN General Assembly Resolution on AI | Global | Enacted |
| General-Purpose AI Code of Practice | EU | Proposed |
| AISI Frontier Model Evaluations Programme | UK | Enacted |
| California SB 1047 | US | Withdrawn |
| IAEA-Style International AI Agency Proposal | Global | Draft |
| Algorithm Recommendation Regulations | China | Enacted |
| EU AI Liability Directive | EU | Proposed |

---

## How it works

All filtering and search runs client-side on a structured JS array. Jurisdiction pills set a filter state, search does substring matching across title, summary and tags, and both apply at the same time. The timeline and coverage matrix pull from the same dataset — no duplicated data.

To add a new policy you just append an object to the array:

```javascript
{
  id: 13,
  jurisdiction: 'US',
  title: 'Policy Name',
  date: 'YYYY-MM-DD',
  dateLabel: 'Mon YYYY',
  status: 'proposed',
  summary: 'What it actually does.',
  tags: ['Tag1', 'Tag2'],
  link: 'https://source.gov'
}
```

---

## Something I noticed building this

Most of the enacted laws focus on how AI gets deployed and used. Very little is binding at the training level — there's no international framework that says what safety evaluations you need before training a frontier model, or what compute threshold triggers oversight. The IAEA-style agency proposal is trying to address that but it's still just a draft. That gap is probably the most important open problem in governance right now.

---

## Stack

Vanilla HTML/CSS/JS. No chart library — the visualizations are pure CSS. No build step, no dependencies.

---

## Running it

```bash
git clone https://github.com/aadyagoraya/ai-policy-tracker
open index.html
```

Or visit the live demo above.

---

## Author

Aadya Goraya — CS Student  
[GitHub](https://github.com/aadyagoraya) · [CoviDash](https://aadyagoraya.github.io/CoviDash/) · [Finance Tracker](https://aadyagoraya.github.io/FinanceTracker/)
