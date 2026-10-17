---
name: phd-paper-report
title: PhD Paper Report
description: Produce a concise, advisor-ready report that summarizes a research paper for a PhD student: background, research question, method, evidence, credibility, research gaps, and recommended next steps.
inputs:
  - paper: Full paper PDF/text or abstract/notes. (At least one required)
  - user_project: Brief description of the student's project and constraints (Optional)
  - purpose: Desired format: "5-min oral", "one-page", "PPT outline", or "detailed" (Default: 5-min oral)
outputs:
  - report: The requested output (oral script, one-pager, PPT outline, or detailed notes)
  - key_questions: High-value follow-up questions for the advisor
usage: Use to prepare group-meeting or advisor-facing summaries of academic papers.
examples:
  - input: {paper: "paper.pdf", purpose: "5-min oral"}
    output: {report: "Background... Key contributions... Judgments..."}
---

# PhD Paper Report — Template

1. Material scope and key missing items (1 sentence).
2. Background: What the system/problem is and why it matters (short paragraph).
3. One-line positioning + specific research question.
4. Method overview and key assumptions/conditions.
5. Key conclusions → evidence → reviewer judgment (1–3 items).
6. Independent evaluation: credibility, boundaries, and suggested caveats.
7. Research space: author-suggested, derivable gaps, and reporter's exploratory directions.
8. Relevance to user's project and recommended next steps (actionable).
9. Optional modes: one-page summary, PPT outline, advisor Q&A prep.

Guidelines
- Preserve exact numerical units, conditions, and baselines when reporting quantitative results.
- Cite exact locations when possible (figure/table/section). If unavailable, mark as "to be verified." 
- Separate author claims from reviewer inferences and label speculative directions.
