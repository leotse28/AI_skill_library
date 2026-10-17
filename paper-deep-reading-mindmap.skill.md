---
name: paper-deep-reading-mindmap
title: Paper Deep Reading & Mindmap
description: Produce a systematic deep-reading note and a mindmap outline for a single academic paper, covering problem, method, theoretical mechanisms, experiments, limitations, and suggested next steps.
inputs:
  - paper: PDF/text/URL/DOI (Required)
  - output_mode: "summary", "detailed", or "mindmap" (Default: "summary")
outputs:
  - structured_note: Title, Authors, Venue, Key Contributions, Method, Evidence, Limitations, Suggested Next Steps
  - mindmap_outline: Hierarchical items suitable for visualization
usage: Use for in-depth reading and preparing reproducible notes or presentations.
examples:
  - input: {paper: "paper.pdf", output_mode: "mindmap"}
    output: {mindmap_outline: "Root -> Methods -> Experiments -> Results"}
---

# Deep Reading & Mindmap — Template

Sections
1. Metadata: Title, Authors, Venue, Year.
2. One-line summary and 3–5 key contributions.
3. Methodology: concise but precise description depending on paper type.
4. Evidence: key experiments/figures and what they show.
5. Limitations & open questions.
6. Suggested next steps and verification experiments.
7. Mindmap outline: hierarchical nodes for quick visualization.

Guidelines
- Preserve units, baselines, and exact conditions for quantitative claims.
- Label any calculated values derived from reported data.
