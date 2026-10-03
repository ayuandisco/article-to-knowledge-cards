---
name: make-knowledge-cards
description: Convert pasted articles or local Markdown and plain-text files into a small set of focused, source-faithful knowledge cards. Use when a user wants to study, review, or distill article content; do not use for web pages, PDFs, Anki exports, or graphical interfaces.
---

# Make Knowledge Cards

Turn the supplied source into useful study cards without adding outside knowledge.

## Inputs

Accept either:

- article text pasted in the conversation; or
- one or more local `.md`, `.markdown`, or `.txt` files.

Read local files before drafting. If an input is missing, unreadable, unsupported, or contains too little substantive information for even one card, state that plainly and ask for usable text. Do not fetch web pages, process PDFs, create Anki packages, or build a graphical interface.

## Select the knowledge

1. Identify the article's main claim, key concepts, mechanisms, distinctions, or actionable principles.
2. Prefer knowledge that is necessary to understand the source, broadly reusable, or easy to misunderstand. Omit introductions, transitions, promotion, decorative anecdotes, and minor details unless they carry an essential lesson.
3. Merge overlapping passages and remove repeated claims. Keep each card about exactly one knowledge point; split a card when its title requires joining unrelated ideas with “and.”
4. Create 5–8 cards only when the source supports that many distinct, important points. Produce fewer when it does not. Never pad the set by restating a point or inventing details.
5. Keep every claim traceable to the supplied source. Preserve attribution, qualifications, uncertainty, scope, and causal direction; present an author's opinion as an opinion rather than an established fact. Do not silently correct or supplement the source with outside knowledge. If the source itself is ambiguous or contradictory, label that limitation instead of resolving it by guessing.

## Write the cards

Use the user's requested language. Otherwise, follow the source language, including the field labels shown below. Present cards in source order when that improves comprehension; otherwise order them from foundational to dependent ideas.

Use this Markdown structure for every card:

```markdown
## 卡片 1：<具体、可辨识的标题>

**核心知识：** <一句话概括单一知识点>

**简明解释：** <用简洁语言说明含义、机制或重要性>

**例子：** <仅使用原文明确提供或可直接改写的例子>
```

When the source does not provide a safe example, replace `例子` with a self-test question that can be answered solely from the card or source:

```markdown
**自测问题：** <检验理解而非只考原句记忆的问题>
```

Do not fabricate an example to fill the field. Keep cards self-contained, concise, and free of duplicated explanations. After drafting, check that each card covers one distinct point, all content is source-supported, and the total count reflects the source rather than the 5–8 target.
