# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Status

This project is in the **pre-development / product planning phase**. No code exists yet. Domain research and market research are complete. The next step is finalizing the Product Brief (BMad workflow: invoke `bmad analyst`, then say "continue product brief").

Key research is in `research-session-2026-04-21.md`.

## Product Concept

A web/mobile app for beginner-to-intermediate Spanish learners. Users log diary entries (text or voice) about their life; the app extracts vocabulary, maps it to CEFR levels (A1–B2), and generates structured lessons and flashcards so learners can speak about their actual life faster.

**Core thesis:** Personal vocabulary (emotionally encoded, tied to real experiences) retrieves faster under speaking pressure. This is the scientific foundation — not a feature claim.

**Positioning:** Supplemental tool, not a Duolingo replacement. Targets people who have real Spanish speakers in their life (family, partners, community) but lack vocabulary confidence.

**Priority user segment:** Heritage Reconnectors — second/third-generation Hispanic Americans who want to speak Spanish for family and cultural connection.

## Key Product Decisions (From Research)

**The aha moment:** User sees their first lesson generated from their own words. Must happen within 90 minutes of signup. This is the primary onboarding goal.

**Competitive positioning:** Occupies "high personalization + speaking focus" — genuinely unoccupied territory. LangJournal is the closest competitor (diary + CEFR feedback) but does not generate lessons or flashcards.

**Pricing tiers:** Free (3 entries), Standard ($9.99/mo), BYOK ($4.99/mo + own API key), Family ($14.99/mo).

## AI Architecture Principles

- Batch processing, not real-time — controls API costs
- Cache generated lessons per vocabulary item (costs don't scale 1:1 with users)
- BYOK (Bring Your Own Key) as escape valve for cost-conscious power users
- Prefer Claude API for structured lesson generation
- E2E encryption for diary entries — non-negotiable for user trust

## Open Questions (Not Yet Resolved)

1. Product name
2. AI architecture: platform-managed API vs. BYOK vs. hybrid
3. Lesson format: what does a lesson look like in the UI?
4. Voice input scope: transcription only, or pronunciation feedback too?
5. Social features: solo-first or team journaling (like LangJournal)?

## Risk Flags

- LangJournal adding lesson generation is high-probability (6–12 months) — shipping speed matters
- User privacy around diary data is a high-impact trust issue — never compromise on E2E encryption or data selling
- AI cost scaling is a real constraint — enforce batch/cache architecture from day one

## BMad Workflow State

| Step | Status |
|---|---|
| Domain Research | Complete |
| Market Research | Complete |
| Product Brief | In progress — Stage 1 (Understand Intent) |
| Architecture, PRD, Epics | Not started |
