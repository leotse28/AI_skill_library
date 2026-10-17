---
name: independent-evidence-based-review
description: Use when the user asks for an independent, objective, evidence-based review of one or more answers, plans, documents, prompts, or skills. Evaluate based on available materials and applicable standards.
---

# Independent Evidence-Based Review

## 1. Responsibilities and Scope

The task is to explain the actual quality, problems, and differences of the object(s) under review and what conclusions the available evidence supports.

Remain independent of the author, model brand, user preferences, and the reviewer's prior opinions. Do not pander, nitpick for the sake of being critical, or manufacture balance for the sake of neutrality. Also do not invent conclusions simply to provide a neat summary.

Deliver evidence-based judgments. Unless the user explicitly requests, do not extend the review into integrated recommendations, rewrites, implementation plans, or new skills.

If the original request or requirements are unreasonable, point out those issues rather than adapting the review to justify the original request.

## 2. Input Verification

Accept one or more actual objects as input, plus the original question, scenario, and constraints (if provided).

- Prefer checking the current conversation and any attachments rather than guessing from filenames.
- If an object cannot be found, ask for it; do not search public sources for private attachments.
- If only excerpts or summaries are available, limit the review to those and do not assume unseen content.
- Missing context that does not change essential judgments should not block the review; only ask for background that would materially affect conclusions.
- Claims in the original text such as "already tested" or "clearly superior" are treated as assertions to be verified, not as established facts.
- If external facts or standards matter, verify them with reliable sources when available; if you cannot verify, clearly state the limitation and do not pretend confirmation.

## 3. Define the Review Questions

Briefly confirm what this review needs to determine:
- Whether a single object is correct, reliable, complete, or fit for purpose.
- The substantive differences and relative merits between multiple objects.
- Whether a specific claim holds.
- Or whether the review can only identify problems and not reach a final judgment.

Do not rewrite the user's request into a different task (for example, picking a winner) unless the user explicitly asks. If the user asks to pick a winner, try to do so, but state when evidence is insufficient.

## 4. Select Applicable Criteria

Choose appropriate criteria based on the objects under review; do not rigidly apply every dimension:
1. Factual and domain correctness: Are key concepts, data, and causal claims valid?
2. Logic and evidence: Are claims supported and are inferences warranted?
3. Problem alignment: Does the object answer the original question or miss the target?
4. Completeness and consistency: Are definitions, assumptions, steps, and conclusions coherent and complete?
5. Feasibility and verifiability: If execution is required, can it be run and tested? (Only check when execution is relevant.)
6. Applicability: Under what conditions is this approach beneficial and what are the costs or limits?
7. Expression quality: Does presentation hinder understanding? Length, layout, and jargon density affect usability but are not direct measures of correctness.

Distinguish between universal baselines and preferences tied to specific scenarios.

Avoid inventing precise weights or scores. If scoring is necessary, disclose the scale, weights, and subjective elements.

## 5. Review Method

### Itemized checks of important claims

For findings that affect conclusions, record:
- Observation: What the object actually says or lacks, with references to the source when possible.
- Evidence: The source text, external reliable evidence, logical checks, or tests.
- Judgment: Why this is a strength, flaw, or uncertain.
- Impact: Whether it affects correctness, usability, or only expression.
- Boundary: What remains unverified and what conditions could change the judgment.

You do not need to show every check—only those that materially affect conclusions.

### Categorize findings

- Confirmed errors: Statements that directly conflict with evidence or definitions.
- Confirmed omissions: Necessary information missing in the provided scope.
- Conditional limitations: Valid only under certain assumptions.
- Plausible but unverified claims: Some support exists but not enough to confirm.
- Insufficient information: Cannot judge with the materials given.
- Style/preference issues: Readability or rhetorical choices that do not imply factual problems.

Do not penalize absent content that was not requested or required.

## 6. Rules for Comparing Multiple Objects

- Apply the same standards to all objects while allowing object-specific checks.
- Do not favor an object because of brand, author identity, or prior familiarity.
- Distinguish substantive differences from phrasing differences and avoid overstating minor advantages.
- Do not expect the same kinds of evidence from objects that had different scopes or requirements.
- If one object has much more available material, note the asymmetry—more data can reveal more issues and does not necessarily mean it's worse.
- Avoid converting qualitative distinctions into unjustified numeric rankings.

## 7. Forming Conclusions

Choose conclusions based on the evidence; do not precommit to a particular format:
- One object is clearly superior on key criteria.
- One object is slightly better overall but with important caveats.
- Different objects suit different conditions; no single ranking is possible.
- One or more objects fail to meet essential baselines.
- Evidence is inadequate to form a stable judgment.

State the most decisive evidence and why it matters. Avoid saying "each has pros and cons" when a clear advantage exists, and avoid pretending certainty when the evidence is limited.

When necessary, separate judgments about local claims and overall conclusions. Do not invent a confidence percentage without calibration.

## 8. Default Output

Keep the length proportional to the complexity. For simple questions, the answer can be brief.

### Conclusion
Directly answer the user's question first. Note any decisive limitation.

### Main Evidence
List the facts and differences that most influenced the conclusion. For multiple objects, a short table is acceptable but do not fill tables with empty content.

### Key Issues and Their Impact
Explain important errors, omissions, or limitations and how they affect the verdict.

### Judgment Boundaries
State what was not provided, not verified, or not tested and whether it affects the conclusion.

End the review there unless the user asks for recommendations or a rewrite; separate any suggested improvements from the review findings.
