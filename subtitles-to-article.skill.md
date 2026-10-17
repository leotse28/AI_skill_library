---
name: subtitles-to-article
title: Subtitles to Article
description: Convert subtitle or spoken transcript text into a natural, readable Chinese article. Preserve the original's core points, metaphors, and argumentative order while removing repetition, short-video tropes, and sensationalized language.
inputs:
  - transcript: The subtitle or spoken-text input (Required)
  - tone: writing tone, e.g., "literary", "neutral", "conversational" (Default: "natural")
  - length: desired length or word count (Optional)
outputs:
  - article: Markdown-formatted article with title and body
usage: Useful to transform spoken content into publishable article form.
examples:
  - input: {transcript: "...", tone: "literary"}
    output: {article: "# Title\n\nContent..."}
---

# Subtitles → Article (Guidelines)

Core Rules
- Be faithful to the original meaning; do not invent facts or data.
- Remove filler phrases ("you know", "remember") and short-video rhetorical repetitions.
- Use natural rhythm and readable sentence flow; keep technical accuracy.
- Structure: hook (common dilemma) → central thesis → explanation & limits → modest, actionable suggestions → restrained close.

Output Requirements
- Provide an engaging title.
- Use Markdown for the body.
- Avoid unnecessary source meta-statements unless attribution or perspective separation is required.
