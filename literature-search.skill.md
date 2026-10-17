---
name: literature-search
title: Literature Search Assistant
description: Assist a beginner researcher in searching and organizing core literature for a defined research question. Produce a validated list of key papers with metadata, contributions, methods, and relevance.
inputs:
  - topic: Short description of research topic or question (Required)
  - keywords: 3–5 keywords (Optional but recommended)
  - time_range: e.g., "last 5 years" (Optional)
  - max_results: number of papers to list (Default: 10)
outputs:
  - search_strategy: The search plan and query examples
  - literature_table: A table with Title, Year, Authors, Venue, Key Contribution, Methodology, Relevance
usage: Use for curated literature overviews; when automated retrieval is used, mark items requiring manual verification.
examples:
  - input: {topic: "heat transfer in microchannels", keywords: ["phase change", "microchannel"], time_range: "5 years"}
    output: {literature_table: [...], search_strategy: "Scopus/Google Scholar queries"}
---

# Literature Search — Template

1. Clarify scope and user constraints.
2. Proposed search strategy: databases, query strings, and filters.
3. Inclusion/exclusion criteria.
4. Result table: Title | Year | Authors | Venue | Key Contribution | Methodology | Relevance.
5. Verification notes: DOIs, links, and items that need manual check.

Strict rule: do not assert a paper exists without a verifiable citation; mark unverified items clearly.
