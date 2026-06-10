---
stepsCompleted: [step-01-init, step-02-discovery, step-02b-vision, step-02c-executive-summary, step-03-success]
inputDocuments:
  - planning_artifacts/product-brief-cuentame.md
  - planning_artifacts/product-brief-cuentame-distillate.md
  - context_driven_lesson_template_guide.md
workflowType: 'prd'
projectName: 'Cuéntame'
classification:
  projectType: web_app
  domain: edtech
  complexity: medium
  projectContext: greenfield
---

# Product Requirements Document - Cuéntame

**Author:** Jason
**Date:** 2026-04-26

## Executive Summary

Cuéntame is a web application that converts a learner's English diary entries into personalized Spanish micro-lessons. Target users are A2-B1 Spanish learners — adults who have foundational Spanish knowledge but cannot yet speak fluidly in real-life situations. The product addresses the documented root cause of language learning stall: speaking anxiety triggered by vocabulary retrieval failure under pressure, not by grammar deficiency. Personal vocabulary — tied to lived experience — encodes more deeply and retrieves faster under the pressure of real conversation. Cuéntame builds a daily practice loop around this mechanism.

The core user flow: write a few sentences in English about your day → Cuéntame translates the entry into Spanish and extracts vocabulary, phrases, and grammar patterns ranked by learning value → generates a structured 10-20 minute lesson → spaced repetition resurfaces personal vocabulary on expanding intervals. The aha moment occurs within the first session: the user sees a lesson built entirely from their own words.

Primary user segments: (1) stalled intermediates who completed beginner apps and hit the wall where gamification stopped producing real speaking ability; (2) Heritage Reconnectors — second/third-gen Hispanic Americans who understand Spanish but cannot produce it; (3) learners supplementing online tutor sessions with targeted vocabulary practice between sessions.

### What Makes This Special

**Write in English, learn in Spanish.** Users write diary entries in English — no Spanish fluency required to use the product. Every competitor requires operating in the target language to extract value; Cuéntame meets learners where they are and teaches them how to say their actual life in Spanish.

**Personal vocabulary retrieves faster.** The curriculum is not preset. Vocabulary extracted from the learner's own diary is emotionally encoded and context-rich, making it significantly more durable under the pressure of real conversation than generic word lists. This is the scientific foundation of the product's core promise, supported by retrieval practice and spaced repetition research.

**Targets the unserved A2-B1 gap.** Duolingo and beginner apps fail to bridge learners into real speaking ability. LangJournal (closest competitor) provides diary-based CEFR feedback but generates no lessons and targets no speaking outcome. Cuéntame occupies the high-personalization + speaking-focus quadrant that no current product addresses.

**Zero cost barrier.** No mandatory subscription. Users bring their own API key — including free-tier providers (Gemini Flash: 1,500 req/day at no cost) — making AI-powered personalization accessible without a recurring fee. Supported by an optional "Buy Me a Coffee" model during early release.

### Project Classification

- **Type:** Web application (SPA, cloud-hosted)
- **Domain:** EdTech — Language Learning
- **Complexity:** Medium — AI-powered lesson generation with no regulatory pathway; key concerns are data privacy, accessibility, and content validity
- **Context:** Greenfield — no existing codebase

## Success Criteria

### User Success

- User completes their first diary entry and sees a generated lesson within the first session (the aha moment — target: <5 minutes from signup to first lesson viewed)
- User voluntarily returns to write a second diary entry within 48 hours of first lesson
- User reports using a word or phrase from the app in a real-life Spanish conversation — captured via optional weekly in-app prompt ("Did you use any of your words this week?")
- User demonstrates measurable CEFR progression: +0.5 level improvement within 90 days of consistent use

### Business Success

| Metric | Target |
|---|---|
| Day-7 retention | >35% |
| Day-30 retention | >20% |
| Avg diary entries per user per week | >3 |
| BYOK activation rate | >25% of registered users |
| NPS | >50 |
| CEFR level improvement at 90 days | +0.5 levels |

Success during dogfood phase (solo use): validate that the diary → lesson pipeline produces pedagogically sound, personally relevant output consistently. Ship when the generated lessons feel genuinely useful to the developer.

Success at first 10-20 external users: at least 50% write a second diary entry within one week. At least one user reports using a learned word in real conversation.

### Technical Success

- Lesson generation completes within 30 seconds of diary entry submission (p95)
- App is available >99% of uptime during active use periods
- BYOK API key setup completes without user requiring external documentation
- Spaced repetition queue accurately resurfaces items at correct intervals
- Generated lessons are pedagogically valid: vocabulary and grammar targets align with CEFR A2-B1 descriptors

### Measurable Outcomes

The primary signal that Cuéntame is working: a user says something in a real Spanish conversation that they first practiced in the app. This is the product's core promise made concrete. Secondary signals: diary entry frequency (>3/week indicates the habit is forming), lesson completion rate (>70% of started lessons completed), and spaced repetition engagement (user engages with review queue at least 3x/week).

## Product Scope

### MVP — Minimum Viable Product (V1)

- Typed English diary entry input with onboarding prompts to reduce cold-start friction
- AI pipeline: English → Spanish translation → vocabulary and grammar pattern extraction → ranked by learning value (personal frequency 40%, global utility 30%, functional B1 value 30%)
- Three-phase micro-lesson generation: Recall Warm-up, Contextual Expansion, Production Challenge
- Flashcard deck with spaced repetition (review intervals: Day 0, 1, 3–4, 7, 14, 30)
- CEFR level tracking (A2→B1 progress visualization)
- Lightweight level assessment at signup — redirects below-A2 users to foundational resources
- BYOK model: user provides own API key; supports OpenAI, Anthropic Claude, Google Gemini (including free-tier providers)
- Progress animation during lesson generation (simple, Mario-style — bridges the wait)
- "Support the project" voluntary contribution model (no mandatory subscription)
- Web only (SPA, cloud-hosted, cloud database)

### Growth Features (Post-MVP)

- **V1.2:** Voice diary input via transcription API ("coming soon" placeholder UI in V1)
- **V2:** Listening comprehension module (so users never need to leave the app for listening practice)
- **V2:** Social / team journaling features
- **V2:** Platform-managed subscription tier (app covers API costs; user pays monthly fee)
- **V2:** Native mobile apps (iOS/Android)

### Vision (Future — Year 2–3)

- Multi-language support — Portuguese as first expansion, then others
- Full personal language learning platform: speaking practice, conversation simulation, pronunciation feedback — all anchored to the learner's own life context
- Personal diary history as proprietary flywheel: the more entries a user creates, the more irreplaceable and personalized their experience becomes
