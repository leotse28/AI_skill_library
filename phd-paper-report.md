---
name: phd-paper-report
description: Helps PhD students organize a read paper into material suitable for reporting to an advisor. Useful for paper presentations, group meeting sharing, preparing discussions with an advisor, and clarifying next research steps.
---

# PhD Paper Report: From Background Understanding to Research Judgment

## 1. Objective

Enable listeners who have not read the paper and are unfamiliar with the subfield to first understand it, and then allow the advisor to judge the paper's contribution, credibility, research space, and relevance to the student's project.

Do not perform line-by-line translation, chapter recitation, or jargon stacking. Do not invent flaws to appear critical, nor invent innovations to claim novelty. Do not assume every paper is worth adopting.

## 2. Five Core Questions

1. What is the background? What is the research object, in what context is it used, what real-world difficulties exist, and why is it worth studying?
2. What does it solve? What specific problem does the paper address, what approach does it use, and what evidence-backed conclusions does it reach?
3. Are the conclusions credible? Why accept, remain cautious about, or question these conclusions, and what are the conditions and boundaries for their validity?
4. What research space remains? What work is unfinished, which questions deserve further research, and what potential innovation directions exist?
5. What does it mean for my research? Which parts are worth adopting or pursuing, what should I do next, and what judgments do I need from my advisor?

Main thread: Understand background → Grasp contribution → Judge credibility → Identify research space → Decide personal actions.

## 3. Input and Material Boundaries

### Minimum input
Full paper, abstract, readable excerpts, or reading notes—at least one. If only the title or bibliographic information is available, request more material and do not generate definitive paper conclusions.

### Preferred contextual inputs
- User's project: subject, goals, current approaches, main bottlenecks and constraints.
- Presentation purpose: knowledge sharing, route selection, method discussion, reproduction preparation, or seeking help.
- Format and length: default is a 5-minute oral report; alternatives include a one-page summary, PPT outline, or preparatory Q&A.
- Audience background: assume general scientific/engineering literacy but not domain-specific expertise. If the user requests zero baseline, explain foundational concepts.

Prefer using context already present in the conversation; avoid redundant questions. If missing non-essential information, continue output; only ask about missing items that materially affect judgment.

### Graded downgrade by available materials
- Full paper: analyze only what is actually readable; if figures, formulas, or appendices are missing or unreadable, note this.
- Abstract: produce an abstract-level preliminary report and do not claim verification of methods, experiments, or figures in the full text.
- Notes: mark content as based on user notes and unverified against the original; separate note-derived viewpoints from verifiable content.
- Unknown project: treat relevance to the user's project as conditional potential and state required conditions.
- Unknown purpose: default to understanding the paper and assessing whether further investment is warranted.

Begin with a short note stating the material scope and any key missing items that affect judgment; do not swamp the report with disclaimers.

## 4. Workflow

### A. Explain the background clearly

Establish intuitive understanding in this order:
1. Object: What system, process, or phenomenon is this, and what does it mainly do?
2. Scenario: In what context does it operate? Use concrete situations.
3. Difficulty: What was hoped for but fails or performs poorly in practice?
4. Significance: Why does this difficulty matter and what value does solving it provide?
5. Paper focus: Which specific problem does this paper target?

Expression rules:
- Define key terms in plain language on first use, then give formal names or acronyms as needed.
- Use short analogies if helpful but state important differences explicitly.
- Avoid vague statements like "as technology rapidly evolves." Do not assume audience knows the user's technical jargon.
- Only add background necessary to understand the paper; do not narrate the field's entire history.
- Distinguish background provided by the paper from supplemental explanation; label unverifiable external facts.

Background should answer "what is it and why care"; research question should answer "what specifically is studied"; the research gap should answer "why prior work is insufficient"—avoid repeating these answers.

### B. Reconstruct the problem, method, and contribution

Extract the research question, shortcomings of prior work, the authors' claimed contributions, and the main method.

Explain how the method maps inputs to results and what assumptions and conditions govern the conclusions. Tailor details to paper type:
- Modeling/simulation: system boundaries, key assumptions, boundary conditions, parameter sources, and validation.
- Experiment: subjects, operating conditions, measurements, controls, repeatability, and uncertainty.
- Algorithm/optimization: objective, constraints, train/test splits or test scenarios, baselines, fairness, and compute cost.
- Theory: assumptions, derivation logic, and scope of propositions.
- Survey: search and selection scope, classification criteria, synthesis conclusions, and omissions.

Do not require every paper to have experiments, statistics, or code. Do not accept claims of novelty or being "first" without evidence.

### C. Map conclusions to evidence and judgments

Select 1–3 conclusions that truly affect research judgment. For each, state:
- The author's conclusion and the conditions under which it applies.
- Which figures, data, derivations, or text support it.
- Source location in the paper (page, figure, table, equation, or section) where possible.
- Your judgment and rationale.
- Remaining unresolved questions.

If you cannot verify locations, say "location to be verified" rather than inventing numbers.

Retain units, conditions, baselines, and metric definitions when reporting numbers. If you compute values from reported data, label them as "calculated from paper data" and provide the calculation basis.

### D. Independent evaluation of credibility and applicability

Check:
- Whether evidence supports the claims or if causal leaps are made.
- Whether comparisons are fair and whether claimed benefits entail unreported costs.
- Whether validation covers the claimed scope and how uncertainty is handled.
- Whether key assumptions apply to the intended transfer scenario.
- Whether data, parameters, and method details are sufficient for reproduction.

Distinguish confirmed limits, scope boundaries, and open questions. Do not invent faults; do not penalize missing info that was not required.

For each key conclusion, rate "well supported / conditionally supported / insufficient evidence / cannot judge from current materials" and explain why.

### E. Identify follow-up research space and possible innovations

Start from what the paper actually did, then discuss remaining work. Avoid listing what the authors already completed as future work.

Classify proposed directions by source:
1. Author-specified future work: restate accurately and cite if possible.
2. Gaps or assumptions from the paper that suggest further work: explain the reasoning.
3. Reporter-proposed exploratory directions: label them as speculation.

By nature:
- Validation/completion: fill verification gaps, test assumptions, improve reproducibility.
- Exploratory innovation: new mechanisms, problem formulations, or method combinations that need vetting.

For each promising direction, include:
- A concrete research question, not just "improve the algorithm." 
- The basis in the paper that motivates it.
- Expected value and potential verification methods.
- Initial check steps or experiments and what would disconfirm the idea.

Avoid proposing many unfounded ideas. If a direction depends on an unverified mechanism, say what observations would falsify it.

### F. Relate to the student's project and propose next steps

Separate general research space from choices tailored to the user. Assess:
- Whether this direction is worth pursuing.
- Suitability to the student's constraints and project.
- Whether the student should invest now.

Provide a small number of actionable next steps: actions, responsible parties, expected artifacts, and stop/go criteria. Do not promise timelines; mark any thresholds as tentative.

For advisor questions, suggest focused questions and the decision points where the advisor's input is needed.

## 5. Default Output Template: 5-minute oral report

Material scope / reporting purpose / key missing items: one concise sentence.

1) Background: make the audience understand.

2) One-line positioning and specific problem: "In the above context, this paper addresses ___ using ___ and finds ___ under ___ conditions."

3) Method outline and key conditions.

4) Key conclusions and evidence: each as "conclusion → evidence & location → my judgment / caveats."

5) Independent evaluation: most credible elements and key limitations.

6) Research directions: distinguish author suggestions, derivable next steps, and your own exploratory ideas.

7) Project relevance and next steps for the student: practical links and what to ask the advisor.

Compress to the allotted time and avoid stuffing all analysis into the short report.

## 6. Optional Modes

Provide only the mode requested by the user.

### One-page summary

Organize by the five core questions, preserve key evidence and judgments, and keep candidate directions brief. Long candidate lists go to an appendix.

### PPT outline

Default 5–7 slides: background & problem, method & conditions, core evidence, independent assessment, research directions, project actions. Use conclusion-type slide titles and indicate original figures to show. Do not claim to have included figures you did not obtain.

### Advisor Q&A prep

Provide 3–5 high-value questions and short answers covering background, method choices, evidence, boundaries, research directions, and project linkages. Explicitly mark unverifiable answers and how to check them.

### Detailed research-space analysis

If requested, expand each candidate direction with source, nature, expected value, verification path, and open checks.

## 7. Facts and Inference Rules

- Separate original facts, author claims, user notes, your judgments, hypotheses, and unverifiable content.
- Do not invent data, experiments, baselines, statistical significance, figure numbers, bibliographic details, or claims.
- Do not generalize local results to universal claims.
- Do not substitute journal names or citation counts for content evaluation.
- Do not claim to have run searches, reproductions, or calculations not actually performed.
- Use the user's language by default; keep technical terms accurate but explain them plainly when needed.
- The template is self-contained and does not rely on external templates unless the user asks.

## 8. Pre-publication Quality Gates

- Can a reader unfamiliar with the paper still explain its object, difficulty, and significance after the background section?
- Did you separate background, research question, gap, and contribution clearly?
- Are key conclusions tied to evidence and location or clearly marked "to be verified"?
- Did you separate author claims from your judgments and avoid unsupported praise or criticism?
- Are suggested directions specific, justified, and not inflated into guaranteed innovation?
- Are project relevance and next steps grounded in known constraints?
- Does the output fit the requested format and length?

Fix issues directly rather than attaching long self-checks. Do not add extra deliverables unless asked.
