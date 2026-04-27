---
title: "Product Brief: Cuéntame"
status: "complete"
created: "2026-04-26"
updated: "2026-04-26"
inputs:
  - research-session-2026-04-21.md
  - context_driven_lesson_template_guide.md
---

# Product Brief: Cuéntame

## Executive Summary

Most Spanish learners reach a plateau they can't escape. After months of Duolingo streaks and vocabulary drills, they still freeze when a real conversation begins. The problem isn't effort — it's that every existing app teaches Spanish in a vacuum, using invented sentences about airports and hotel lobbies, while the vocabulary a learner actually needs (their family, their job, their relationships) goes completely unaddressed.

Cuéntame breaks that pattern. Users write a short diary entry about their day — dinner with family, a conversation with a coworker, something they're looking forward to — and Cuéntame transforms that content into a personalized Spanish micro-lesson built entirely from their own life. Within minutes of their first entry, a new user sees vocabulary from their own sentences, grammar patterns from their own stories, and flashcards they'll actually remember because the content is already meaningful to them.

The science is clear: vocabulary tied to lived personal experience encodes more deeply and retrieves faster under the pressure of real conversation. Cuéntame turns that insight into a daily practice loop — and targets the learner that every major app has failed: the A2-to-B1 speaker who knows enough to know they still can't really speak.

## The Problem

Millions of adults study Spanish for years and emerge unable to hold a real conversation. The mechanism is well-documented: when learners freeze mid-sentence, the culprit is vocabulary retrieval failure under pressure — not grammar, not pronunciation. The anxiety that follows neurologically shuts down language production, making every failed attempt harder than the last.

Existing apps don't solve this. Duolingo builds recognition, not recall — its own users report "freezing when they respond" after years of daily streaks. AI-native challengers like Speak and Jumpspeak are output-focused but work from preset scenarios, not the learner's own life. LangJournal, the closest competitor, takes diary input and returns grammar corrections — useful, but it generates no lessons and targets no speaking outcome.

The A2-B1 learner — someone who knows the basics but can't yet have a flowing conversation — has no targeted product. They've hit the wall and don't know where to go.

## The Solution

Cuéntame is a web application built around a single repeatable loop:

1. **Write** — A few sentences in English about your day. No Spanish required to start. Onboarding prompts ease the first entry for users who aren't sure what to write.
2. **Generate** — Cuéntame translates the entry into Spanish, extracts vocabulary, phrases, and grammar patterns ranked by learning value, and builds a structured 10-20 minute lesson. A simple progress animation (think: jumping platform) bridges the generation wait, keeping the magic moment intact.
3. **Practice** — Three phases: *Recall Warm-up* (retrieve previously studied vocabulary from your own content), *Contextual Expansion* (transform your own sentences into new forms), and *Production Challenge* (write or speak about a real event using target grammar and connectors).
4. **Review** — Spaced repetition resurfaces personal vocabulary at the right intervals, building durable recall over time.

The more entries a user creates, the more personalized the review queue becomes — surfacing their highest-frequency personal vocabulary first, building a learning flywheel that gets harder to walk away from.

## What Makes This Different

**Personal vocabulary retrieves faster.** Vocabulary tied to real, emotionally relevant experience encodes more deeply and surfaces under pressure better than any preset word list. Cuéntame is the first product to systematically build a practice loop around this insight.

**It picks up where Duolingo leaves off.** Cuéntame doesn't compete with beginner apps. It targets the specific transition from A2 to B1 — from "I studied Spanish" to "I can actually talk to people" — a gap no existing product addresses directly.

**Write in English, speak in Spanish.** Users write about their real life in English — no Spanish fluency required to use the app. Cuéntame translates that content into Spanish and builds lessons from it. Every competitor requires the learner to operate in the target language to get value; Cuéntame meets them where they are.

**Zero barrier to start.** No monthly subscription required to begin. Users bring their own API key — including free-tier providers like Gemini Flash — making the AI cost optional and often zero. A "support the project" model keeps the early experience frictionless for the learner who won't pay $12/month for another app that might not work.

## Who This Serves

**Primary: The Stalled Intermediate.** Adults at A2-B1 who have made real progress with existing apps and hit a wall where drilling stopped producing real speaking ability. They have Spanish speakers in their life — a partner, family members, coworkers, a community — and want to actually communicate with them. They're motivated, often frustrated, and willing to try a different approach.

This segment includes Heritage Reconnectors (second-gen Hispanic Americans who understand Spanish but struggle to produce it), learners supplementing online tutor sessions (Cuéntame gives practice sessions more relevant vocabulary), and anyone for whom Spanish is a live social need.

**Not for:** Complete beginners (A0-A1). Since input is in English, anyone can write an entry — but the lessons assume a basic Spanish foundation. A lightweight level assessment at signup sets expectations and routes users below A2 toward foundational resources first.

## Success Criteria

| Metric | Target |
|---|---|
| Day-7 retention | >35% |
| Avg diary entries per user per week | >3 |
| BYOK activation or support conversion | >25% |
| NPS | >50 |
| CEFR improvement at 90 days | +0.5 levels |

The primary qualitative signal: users report saying something in a real conversation that they first practiced in the app.

## Scope

**V1 — Core Loop (Web, Cloud)**
- Typed diary entry input with onboarding prompts
- AI extraction and micro-lesson generation (BYOK, including free-tier LLMs)
- Three-phase lesson structure: Recall Warm-up, Contextual Expansion, Production Challenge
- Flashcard deck with spaced repetition
- CEFR level tracking (A2→B1)
- Lightweight level assessment at signup
- "Support the project" model (no mandatory subscription)

**V1.2**
- Voice diary input ("coming soon" UI placeholder in V1)

**Explicitly out of V1**
- Listening comprehension module (roadmap)
- Social / team journaling
- Native mobile apps
- Platform-managed AI subscription tier

## Roadmap Thinking

If the core loop resonates, Cuéntame grows into a full personal language learning platform: listening comprehension, speaking practice, conversation simulation — all anchored to the learner's own life. The model extends naturally to other languages. Over time, a user's diary history becomes the most personalized language curriculum that exists for them anywhere.

The long-term vision: personal context as the universal curriculum. Starting with Spanish. Built for the conversation you actually want to have.
