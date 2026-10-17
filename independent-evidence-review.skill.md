---
name: independent-evidence-review
title: Independent Evidence-Based Review
description: Perform an independent, objective, evidence-based review of one or more artifacts (answers, plans, documents, prompts, or skills). Produce fact-based judgments and clearly separate evidence, author claims, and reviewer inferences.
inputs:
  - artifact: The text, document, or collection of materials to be reviewed. (Required)
  - context: Original request, scenario, and constraints (Optional)
  - comparison_items: List of other objects to compare (Optional)
outputs:
  - conclusion: Direct answer to the requested judgment
  - main_evidence: Key facts and differences that support the conclusion
  - key_issues: Important errors, omissions, and limitations
  - judgment_boundaries: What was not provided or verified
usage: Use when a factual, independent assessment is needed; do not extend into implementation plans unless requested.
examples:
  - input: {artifact: "proposal.md", context: "evaluate fitness for production"}
    output: {conclusion: "Insufficient: missing testing data", main_evidence: ["no test results section"]}
---

# Independent Evidence-Based Review

Purpose
- Provide an objective, evidence-centered assessment of artifacts. Focus on what can be supported by the available material and clearly call out assumptions and missing information.

Template Sections
1. Scope & Inputs — what was provided and what is missing.
2. Review Questions — what the user asked to judge.
3. Criteria — factual correctness, logic & evidence, problem alignment, completeness, feasibility, applicability, expression quality.
4. Findings — itemized observations with evidence, judgment, impact, and boundaries.
5. Conclusion — direct answer to the user's question.
6. Main Evidence — prioritized facts that drove the conclusion.
7. Key Issues & Impact — how issues affect the verdict.
8. Judgment Boundaries — what remains unverified and whether it matters.

Notes
- Distinguish original claims, confirmed facts, and reviewer inference.
- Mark unverifiable claims and avoid fabricating data.
- If comparing multiple objects, apply consistent criteria and note asymmetries in available material.
