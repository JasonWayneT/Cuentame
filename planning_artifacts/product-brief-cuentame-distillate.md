---
title: "Product Brief Distillate: Cuéntame"
type: llm-distillate
source: "product-brief-cuentame.md"
created: "2026-04-26"
purpose: "Token-efficient context for downstream PRD creation"
---

# Cuéntame — Detail Pack

## Target User (Precise Definition)

- **Level:** A2–B1 specifically. Goal is breaking through A2 into confident contextual speaking.
- **Not A0–A1:** App requires a Spanish foundation to make lessons meaningful. Level assessment at signup redirects below-A2 users to foundational resources rather than frustrating them with output they can't use.
- **Not just Heritage Reconnectors:** The research session over-indexed on Heritage Reconnectors as priority segment. The actual target is broader — any A2-B1 learner who knows the basics but can't yet speak in real situations.
- **Primary persona:** Adult who has studied Spanish (Duolingo, classes, self-study), made real progress, and hit the wall where drilling stopped producing real-world speaking ability. Has Spanish speakers in their life or uses online tutors. Motivated and frustrated.
- **Segments included:** Heritage Reconnectors (second/third-gen Hispanic Americans who understand but can't produce), stalled Duolingo graduates, learners supplementing online tutor sessions (Cuéntame practice between sessions becomes more tutor-relevant).
- **Conversation partner NOT required:** App is not marketed only to people with a Spanish speaker at home. Personal vocabulary benefits everyone regardless of practice setup.

## Input Model

- **100% English input.** Users write diary entries in English about their real life. No Spanish fluency required to use the app.
- App translates English entry into Spanish, then extracts vocabulary and builds lessons from the translation.
- This is a key differentiator: every competitor requires operating in the target language to get value. Cuéntame meets users where they are.
- Onboarding prompts provided for cold start ("what do I write?") — this is a high-probability friction point flagged in research.

## Lesson Philosophy (from lesson template guide)

- **Source doc:** `context_driven_lesson_template_guide.md` — full pedagogical framework, should be used as input to PRD lesson design.
- **Scientific basis:** Retrieval practice + spaced repetition + personal context. Personal vocabulary encodes more deeply and retrieves faster under speaking pressure (emotionally encoded memory).
- **Lesson target per session:** 3–5 lexical chunks/high-value words, 1–2 grammar contrasts (e.g., preterite vs. imperfect), 1 discourse connector.
- **Three-phase micro-lesson structure:**
  1. **Recall Warm-up** — reactivate prior personal vocabulary via cloze, translation from memory, sentence reconstruction. No multiple choice — forces retrieval not recognition.
  2. **Contextual Expansion** — transform own sentences into new forms (change tense, swap connectors, reuse chunk in new context). Converts memorized sentences into flexible repertoire.
  3. **Production Challenge** — constrained output using real event + required grammar targets (e.g., "retell last night's dinner in 6-8 sentences, use 2 preterite, 2 imperfect, 2 connectors, one opinion").
- **Duration target:** 10–20 minutes per lesson.
- **Lesson UI feel:** Duolingo-esque — bite-sized, visually clear, interactive, progression feel. Not a wall of text.
- **Spaced repetition:** Integrated into pipeline, not a separate flashcard add-on. Review intervals: Day 0, Day 1, Days 3–4, Day 7, Day 14, Day 30. Shorter for unstable items.
- **Vocabulary ranking:** Personal frequency (0.4 weight) + global utility/CEFR frequency (0.3) + functional value for B1 (narration, opinion, sequencing) (0.3). These weights are Proposed Design Theory from the template.
- **Spanish-specific grammar focus for A2→B1:** Preterite vs. imperfect, early high-frequency subjunctive triggers ("quiero que…", "es importante que…"), discourse connectors ("al principio", "luego", "sin embargo", "aunque", "al final", "me pareció que…").

## Platform & Technical Scope

- **V1:** Web app, cloud-hosted, cloud database. No local/self-hosted version (user initially considered this, then reversed — wants to practice cloud deployment).
- **V1 input:** Typed diary entries only.
- **V1.2:** Voice diary input. Requires transcription API (has a cost). "Coming soon" placeholder UI in V1 — do not omit the UI hint entirely, just disable/label it.
- **Generation UX:** Lesson generation has latency. A simple progress animation (Mario-style jumping platform — "just the up button", very simple) bridges the wait. This is part of the magic moment experience.

## Monetization & Access Model

- **Early stage:** Not selling right now. App is dogfooded by the developer first.
- **BYOK (Bring Your Own Key):** Primary access model. Users provide their own LLM API key.
- **Free-tier LLMs supported:** Gemini Flash free tier (1,500 req/day, 1M context, no credit card), Groq free tier. This allows zero AI cost for early users.
- **"Buy Me a Coffee" / "Support the project" model:** Voluntary contribution, not a paywall. Low friction, appropriate for early public release.
- **Future monetization:** Platform-managed subscription tier (user pays monthly, app covers API costs) is deferred — not in V1 scope. Decision deferred until user base validates the product.
- **Design constraint:** AI used only where necessary to control token costs. Lessons cached per vocabulary set — cost doesn't scale 1:1 with users.
- **BYOK UX risk:** Non-technical users may not understand "API key." Proposed mitigation: app uses a small shared budget for first lesson to demonstrate value, then prompts for key setup. Full solution deferred to post-dogfood phase.

## Competitive Intelligence

- **LangJournal (closest competitor):** Still no lesson generation as of April 2026. Latest update (May 2025) added most-frequently-used-words tracking. Remains a writing correction tool, not a speaking accelerator. Window is open but rated high-probability to add lessons within 6–12 months.
- **Duolingo:** $748M revenue, 11.5M paid subscribers. Documented weakness: recognition-based, users "freeze when they respond." Not building diary/journal features publicly as of research date.
- **Speak, Jumpspeak, Langua:** Output-focused AI challengers, but preset content — not life-generated.
- **White space confirmed:** High personalization + speaking focus quadrant is genuinely unoccupied.

## Rejected Ideas / Scope Decisions

- **Heritage Reconnector as primary segment:** Rejected as sole focus. Product is for all A2-B1 learners, not just Hispanic Americans reconnecting with family language. Heritage Reconnectors remain a strong sub-segment but not the only one.
- **Local/self-hosted version:** Initially considered, then dropped. User wants cloud to build cloud skills.
- **Listening comprehension module:** Explicitly out of V1. Reserved as a future module so users don't need to leave the app. Many free resources exist for listening practice; this is not a gap that needs filling in V1.
- **Social/team journaling:** Not in V1. Solo-first. (LangJournal has team journaling — not a differentiator to pursue immediately.)
- **Native mobile apps:** Web first. Mobile deferred.
- **Real-time AI (conversational tutor):** Batch/async processing only in V1. Real-time AI costs too much at early scale.
- **Voice input in V1:** Deferred to V1.2 due to transcription API cost. Placeholder UI only.
- **Platform-managed subscription:** Deferred. BYOK + donation model for early release.

## Open Questions (Unresolved at Brief Close)

- **BYOK onboarding UX for non-technical users:** How exactly does a non-developer set up their API key? First-lesson shared budget as bridge? Full UX design needed.
- **Sub-A2 level assessment:** What does the assessment look like? Quiz? Self-report? How many questions? What's the redirect experience?
- **Lesson caching strategy:** When two users write similar diary content, how much of the generated lesson can be reused? Needs technical spike.
- **Future subscription pricing:** Research suggested $9.99/mo Standard, $4.99/mo BYOK, $14.99/mo Family. Not validated or committed to yet.

## Roadmap (Confirmed Sequence)

| Phase | Scope |
|---|---|
| V1 | Core loop: English diary → translation → lesson → flashcards → spaced repetition. Web. BYOK. |
| V1.2 | Voice diary input |
| Future | Listening comprehension module |
| Future | Social/team journaling |
| Future | Native mobile apps |
| Future | Platform-managed subscription tier |
| Year 2–3 | Additional languages (Portuguese first candidate) |
| Long-term | Full personal language learning platform |

## Success Metrics (V1)

| Metric | Target |
|---|---|
| Day-7 retention | >35% |
| Avg diary entries/user/week | >3 |
| BYOK activation or support conversion | >25% |
| NPS | >50 |
| CEFR improvement at 90 days | +0.5 levels |

**Primary qualitative signal:** User reports saying something in a real conversation that they first practiced in the app.

## Go-to-Market Context (From Research)

- **Phase 1 (Months 1–6):** Dogfood and nail the magic moment. Soft launch. Obsess over first-90-minute onboarding (diary → lesson in one session).
- **Phase 2 (Months 6–12):** TikTok content showing diary-to-lesson in 30 seconds. Reddit presence (r/learnspanish, r/languagelearning). 2–3 micro-influencer partnerships.
- **Phase 3 (Year 2):** App Store, family plans, language expansion.
- **The 90-minute aha moment:** Top-quartile language apps get users to their aha moment within 90 minutes and achieve 38.2% trial-to-paid conversion. Aha moment for Cuéntame = user sees their first personalized lesson from their own words.
