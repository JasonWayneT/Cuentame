---
title: Cuentame Product Brief
status: draft
created: 2026-06-08
updated: 2026-06-08
---

# Cuentame

> A Spanish learning app that generates personalized vocabulary lessons and flashcards from the learner's own diary entries — so you practice the words you actually need to speak your life, not a generic word list.

---

## Executive Summary

Cuentame is a pre-development product concept for a diary-driven Spanish learning app. The core insight: vocabulary tied to real, personal experiences retrieves faster under speaking pressure than vocabulary learned from generic lists. Users log diary entries — text or voice — about their day; the app extracts vocabulary, maps it to CEFR levels (A1–B2), and generates structured lessons and flashcards from that real content.

Domain and market research are complete. A full lesson design specification exists grounded in cognitive science and second language acquisition research. The product occupies a genuine gap: high personalization combined with a speaking focus is unoccupied territory in the current language learning market. Development has not yet started.

---

## The Problem

Most language learning apps teach vocabulary in the abstract — Duolingo's tap-and-match, Pimsleur's audio phrases, generic word frequency lists. They produce learners who can pass a test and can't hold a conversation about their actual life.

Two specific user populations feel this most acutely:

**Heritage Reconnectors.** Second and third-generation Hispanic Americans who understand Spanish at home but can't produce it. They don't need to learn "red is rojo." They need vocabulary for the conversations they're already having: family dinners, neighborhood relationships, professional settings. Generic apps weren't built for them.

**Stalled Intermediates.** Learners who studied Spanish formally and hit the wall where structured apps stopped producing real speaking ability. They have grammar; they don't have words for their life. More structured study isn't the answer — more personal practice is.

The gap isn't another vocabulary app. The gap is vocabulary that's actually yours.

---

## The Solution

Users log diary entries about their day — what happened, who they talked to, what they're thinking about. Text or voice. The app processes those entries, extracts vocabulary the user doesn't yet know, maps each word or phrase to a CEFR level (A1–B2), and generates a structured lesson and flashcard set from that content.

**The lesson structure** is a 3-phase daily micro-lesson (10–20 minutes), defined in `context_driven_lesson_template_guide.md`:

1. **Recall Warm-up** — reactivates previously studied material through cloze deletion, translation recall, and sentence reconstruction using the user's own prior diary content. No multiple choice — active retrieval only.
2. **Contextual Expansion** — takes the user's own sentences and requires recombination: transform an event into a habit, swap connectors, reuse chunks in a new real-life context.
3. **Production Challenge** — constrained output. Write or speak 6–8 sentences about a real event using target grammar forms, connectors, and vocabulary. Self-correction against the AI model answer.

Spaced repetition runs underneath all of it — vocabulary and chunks resurface on expanding intervals as recall weakens, not on a fixed daily schedule.

The aha moment: the user sees their first lesson generated from their own words within 90 minutes of signing up. That's the primary onboarding target.

**Architecture decisions already made:**
- Batch processing, not real-time — controls AI costs
- Lesson caching per vocabulary item — costs don't scale 1:1 with users
- E2E encryption for diary entries — non-negotiable; diary content is private by nature
- BYOK tier — cost escape valve for power users with their own API key

The app is supplemental, not a Duolingo replacement. It sits alongside whatever structured study the user already does and closes the gap between "I studied" and "I can speak."

---

## What Makes This Different

**LangJournal** is the closest competitor — diary writing with CEFR-level feedback. It does not generate lessons or flashcards from diary content. That's the gap Cuentame fills.

**Duolingo, Pimsleur, Rosetta Stone** — all generic vocabulary, generic sentences. None generate content from your life.

The competitive position: **high personalization + speaking focus.** Market research confirmed this is genuinely unoccupied territory. The lesson design is grounded in retrieval practice, spaced repetition, lexical chunking, and CEFR-aligned communicative design — not intuition or gamification mechanics.

The risk: LangJournal adding lesson generation is a plausible 6–12 month threat. Speed matters.

---

## Who This Serves

**Primary: Heritage Reconnectors.** Second and third-generation Hispanic Americans who want to speak Spanish for family and cultural connection. They have listening comprehension; they lack production vocabulary for their actual life.

**Secondary: Stalled Intermediates.** People who've studied Spanish and stopped making progress. Their vocabulary doesn't cover their real life; that's why conversation stays out of reach.

**Not the target:** Complete beginners with zero Spanish exposure. The app assumes some listening context — learners with no baseline lack the framework to absorb vocabulary extracted from their own content.

---

## Success Criteria

| Criterion | Target |
|---|---|
| First lesson generated within 90 minutes of signup | Primary onboarding goal |
| All vocabulary in lessons drawn from user's own diary | Architectural requirement |
| E2E encryption for all diary content | Non-negotiable |
| AI costs scale sub-linearly with users (lesson caching) | Architecture target |
| User can produce vocabulary under speaking pressure | Core outcome |

---

## Scope

**In scope (v1):**
- Diary entry input: text and voice (transcription)
- Vocabulary extraction and CEFR mapping (A1–B2)
- Lesson generation: 3-phase micro-lesson structure
- Flashcard generation with spaced repetition
- Platform-managed API + BYOK tier

**Out of scope (v1, by design):**
- Pronunciation feedback — transcription only for voice
- Social or team journaling — solo-first
- Languages beyond Spanish

**Open (design not yet resolved):**
- UI treatment for lessons — content structure is defined; visual/interaction design is not
- Social features — roadmap candidate, not v1

---

## Reference Documents

| File | Purpose |
|---|---|
| `context_driven_lesson_template_guide.md` | Full lesson design spec — cognitive science grounding, pipeline, micro-lesson template, evaluation criteria |
| `Context-Driven Lesson Template Guide for Personalized Spanish Learning (A2→B1).md` | Extended research version of the same |
| `planning_artifacts/product-brief-cuentame.md` | Prior BMAD brief draft |
| `planning_artifacts/prd.md` | PRD in progress |

---

## Vision

The long-term thesis: the most durable vocabulary is the vocabulary of your life. Cuentame starts with Spanish because the Heritage Reconnector need is concrete and underserved. The model — diary-driven, personal, CEFR-mapped — applies to any language pairing.

The roadmap points toward reducing the cost of personalization to near-zero through aggressive lesson caching and local model options. Every learner should be able to maintain a living vocabulary practice tied to their actual experience — without paying per lesson indefinitely.
