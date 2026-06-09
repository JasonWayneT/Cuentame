---
title: "Cuentame"
description: "A Spanish learning app for heritage speakers and stalled intermediates — lessons built from the user's own diary vocabulary, not a generic word list."
author: "Jason Taylor"
role: "Product Manager"
status: "in-progress"
ai_role: "research synthesis, product brief drafting under Jason's direction; no code written yet — pre-development phase"
tech_stack: []
pm_skills: ["market research", "competitive analysis", "user segmentation", "product brief", "AI cost architecture design", "privacy-first design"]
keywords: ["Spanish learning", "heritage speakers", "language learning", "CEFR", "vocabulary", "personalized learning", "diary"]
date_completed: ""
---

# Cuentame

> A Spanish learning app for people who already understand Spanish but can't produce it. You log what happened in your day; the app builds lessons from that actual vocabulary.

---

## What This Is

Cuentame closes a specific gap: "I studied Spanish" versus "I can actually hold a conversation." Users log diary entries in text or voice. The app extracts vocabulary from those entries, maps it to CEFR levels (A1–B2), and builds lessons and flashcards from that content.

The core thesis: vocabulary tied to real experiences retrieves faster under speaking pressure than generic list vocabulary. Not a feature claim. The cognitive science foundation the product is built on.

**Target user:** Heritage Reconnectors (second and third-generation Hispanic Americans who understand Spanish at home but can't produce it) and stalled intermediates who studied, hit the plateau, and now have grammar but not the words for their actual life.

**My role:** Market research, competitive landscape analysis, user segmentation (Heritage Reconnectors as primary segment), product brief, AI cost architecture decisions, privacy model design.
**AI's role:** Research synthesis, product brief drafting under my direction. No code exists yet — this is the pre-development phase.

**What this is not:**
- A Duolingo replacement — supplemental tool that bridges structured study to real conversation
- A finished product — currently in the planning and research phase, no public release

---

## Status

| Field | Value |
|---|---|
| **Phase** | Pre-development |
| **Stability** | Research and product brief complete — development not started |
| **Last updated** | April 2026 |

---

## Challenges & Decisions

### Supplemental positioning, not Duolingo replacement
**Problem:** Any new Spanish app invites comparison to Duolingo. Competing on breadth loses. Duolingo has 10 years and 500M users.
**Decision:** Position as supplemental — explicitly for people who already have some grammar foundation and need to bridge to real conversation. "What you studied + what you actually say."
**Tradeoff:** Smaller addressable market. Excludes total beginners.
**Outcome:** Clearer product brief. Heritage Reconnectors and stalled intermediates are the real target — people with existing Spanish exposure who can't produce under pressure. That's a real, underserved segment.

### Batch processing over real-time AI generation
**Problem:** Real-time AI generation (one API call per user action) scales costs 1:1 with users. A lesson app with 10,000 daily active users would have unpredictable API bills.
**Decision:** Batch processing. Generate and cache lesson content per vocabulary item. The same lesson for "trabajo" doesn't get regenerated for every user who logs that word.
**Tradeoff:** Less real-time personalization at the lesson level. Batch jobs require infrastructure for scheduling and cache invalidation.
**Outcome:** Cost scales with vocabulary diversity, not user count. That's the right model for a consumer product with variable usage patterns.

### E2E encryption for diary entries as non-negotiable
**Problem:** Diary entries are personally sensitive. A language learning app that stores unencrypted diary content about users' daily lives is a privacy liability and a trust problem.
**Decision:** E2E encryption on diary entries from day one. Server never has access to plaintext. BYOK tier as an escape valve for cost-conscious users who want to run their own AI pipeline.
**Tradeoff:** Higher implementation complexity. Harder to do server-side AI processing on encrypted data — requires client-side decryption before any AI call.
**Outcome:** Non-negotiable for the Heritage Reconnector segment specifically. Family stories and personal context are exactly the content they'd diary about. That trust has to be earned architecturally, not just promised in a privacy policy.

---

## How Lessons Work

Each lesson is a 3-phase daily micro-lesson (10–20 minutes), fully specified in `context_driven_lesson_template_guide.md`:

1. **Recall Warm-up** — cloze deletion, translation recall, and sentence reconstruction from the user's own prior diary content. Active retrieval only — no multiple choice.
2. **Contextual Expansion** — takes the user's own sentences and requires recombination: transform an event into a habit, swap connectors, reuse vocabulary chunks in a new real-life context.
3. **Production Challenge** — write or speak 6–8 sentences about a real event using target grammar and connectors. Self-correction against the AI model answer.

Spaced repetition runs underneath: vocabulary resurfaces on expanding intervals as recall weakens. The lesson content structure is fully defined. UI design is an open question.

---

## What's In This Repo

| File | Purpose |
|---|---|
| `Context-Driven Lesson Template Guide for Personalized Spanish Learning (A2→B1).md` | Domain and market research session — user segments, competitive landscape, key product decisions |
| `context_driven_lesson_template_guide.md` | Lesson format specification and CEFR mapping approach |
| `planning_artifacts/` | BMAD planning outputs — PRD and prior brief drafts |
| `docs/product-brief.md` | Final product brief — source of truth for scope, user, and success criteria |

---

## How This Was Built

I ran domain and market research before committing to any product decisions: user segments, competitive landscape (Duolingo, LangJournal, Pimsleur), pricing model, AI cost architecture, privacy risks. The finding that shaped everything: "high personalization + speaking focus" is genuinely unoccupied territory. LangJournal is the closest competitor and it doesn't generate lessons or flashcards from diary content. That gap is real.

Architecture is decided: batch processing over real-time to control AI costs, lesson caching per vocabulary item so costs don't scale 1:1 with users, E2E encryption for diary entries as non-negotiable. Development hasn't started. The foundation is solid.

---

## License

Private
