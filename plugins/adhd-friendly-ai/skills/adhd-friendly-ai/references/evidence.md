# Evidence and design rationale

## Scope

This skill combines three kinds of input:

1. established descriptions of ADHD and group-level cognitive findings;
2. cognitive-accessibility guidance for content and natural-language interfaces;
3. pragmatic interaction heuristics that still require individual calibration.

The skill does not claim that a response format treats ADHD, works for every person with ADHD, or follows directly from a clinical trial of AI conversations.

## What is well supported

ADHD is heterogeneous. The US National Institute of Mental Health describes differing presentations and notes difficulties that can include sustained attention, organization, remembering daily tasks, planning, following instructions, completing large projects, and multitasking. This supports adapting to the individual rather than imposing a single “ADHD mode.”

Source: [NIMH, Attention-Deficit/Hyperactivity Disorder: What You Need to Know](https://www.nimh.nih.gov/health/publications/attention-deficit-hyperactivity-disorder-what-you-need-to-know)

The World Federation of ADHD consensus statement synthesizes evidence from meta-analyses and large studies. It reports group-level differences across several cognitive domains while emphasizing that such findings do not diagnose or describe every individual. This supports cautious language and user-specific calibration.

Source: [Faraone et al., 2021, World Federation of ADHD International Consensus Statement](https://pubmed.ncbi.nlm.nih.gov/33549739/)

Meta-analytic research finds average differences in executive-function domains, including vigilance, working memory, inhibition, and planning, but executive-function weaknesses are neither necessary nor sufficient to account for every ADHD case. This supports reducing avoidable working-memory demands without treating a presumed deficit as universal.

Sources: [Willcutt et al., 2005, meta-analytic review](https://pubmed.ncbi.nlm.nih.gov/15950006/); [Alderson et al., 2013, adult working-memory meta-analysis](https://pubmed.ncbi.nlm.nih.gov/23688211/)

## Accessibility guidance relevant to conversational AI

W3C cognitive-accessibility guidance recommends clear content, support for focus, orientation, task completion, and avoiding unnecessary cognitive barriers. These patterns cover cognitive and learning disabilities broadly; they are useful design evidence but are not ADHD-specific treatment evidence.

Sources: [W3C, Making Content Usable for People with Cognitive and Learning Disabilities](https://www.w3.org/TR/coga-usable/); [W3C, Help Users Focus](https://www.w3.org/WAI/WCAG2/supplemental/objectives/o5-user-focus/)

W3C's draft requirements for natural-language interfaces say users may need clear language, explanations of unfamiliar terms, help and instructions, reviewable dialogue history, and summaries before irreversible actions. These directly inform jargon explanations, memory externalization, help on request, and confirmation for consequential actions.

Source: [W3C, Natural Language Interface Accessibility User Requirements](https://www.w3.org/TR/naur/)

## Evidence-to-design translation

| Design behavior | Rationale | Confidence |
|---|---|---|
| Preserve goals, decisions, and progress | Reduces avoidable reliance on working memory; aligns with reviewable history and orientation guidance | Strong rationale, indirect conversational evidence |
| Protect the current focus | Aligns with attention-related barriers and W3C focus guidance | Strong accessibility rationale |
| Guided steps and visible expected results | Supports task completion and reduces the information held at once | Strong accessibility rationale |
| Clear language and brief definitions of unfamiliar terms | Explicit W3C natural-language-interface requirement | Strong accessibility rationale |
| Progressive disclosure | Structures complexity and reduces simultaneous processing demands | Established UX/accessibility heuristic |
| Recommend one option when context is sufficient | Reduces unnecessary decision work | Pragmatic design heuristic |
| Show roughly two or three relevant options by default | Useful starting preference, not an ADHD finding | User preference / heuristic |
| Use short paragraphs, restrained emphasis, or a small number of bullets | May improve scanning, but exact quantities are not clinically established | User preference / heuristic |

## Guardrails for future changes

- Label a rule as research-backed only when the cited source supports that specific claim.
- Do not convert averages across groups into claims about an individual.
- Do not turn an effective personal preference into a universal ADHD rule.
- Prefer configurable defaults over fixed numerical limits.
- If a user repeatedly benefits from a different format, update the preference rather than defending the default.
- Keep clinical advice outside this skill; consult qualified clinicians and current medical guidance for diagnosis or treatment decisions.

## Source status

The W3C COGA and NAUR documents are informative guidance or drafts, not normative WCAG conformance requirements. The interaction rules in this repository are therefore best understood as evidence-informed accessibility design, not a medical protocol or formal standard.
