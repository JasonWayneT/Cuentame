# Cuentame

> A Spanish learning app that generates personalized vocabulary lessons and flashcards from the learner's own diary entries — so you practice the words you actually need to speak your life, not a generic word list.

---

## What This Is

Cuentame closes the gap between "I studied Spanish" and "I can actually talk to people." Users log diary entries — text or voice — about their day, their conversations, things they care about. The app extracts vocabulary, maps it to CEFR levels (A1–B2), and generates structured lessons and flashcards tied to that real content.

The core thesis: vocabulary that's tied to your actual experiences retrieves faster under speaking pressure. This isn't a feature claim — it's the scientific foundation the product is built on.

**Target user:** Heritage Reconnectors — second and third-generation Hispanic Americans who understand Spanish at home but can't produce it. And stalled intermediates who hit the wall where Duolingo's tap-and-match stopped producing real speaking ability.

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

Research-first. Before any product decisions were made, a domain research and market research session was run through the BMAD analyst workflow — user segments, competitive landscape (Duolingo, LangJournal, Pimsleur), pricing model, AI cost architecture, and privacy risks. The key insight from that research: "high personalization + speaking focus" is genuinely unoccupied territory in the language learning market. LangJournal is the closest competitor but doesn't generate lessons or flashcards from diary content.

Architecture decisions already made: batch processing (not real-time) to control AI costs, lesson caching per vocabulary item, E2E encryption for diary entries as a non-negotiable trust requirement.

---

## License

Private
