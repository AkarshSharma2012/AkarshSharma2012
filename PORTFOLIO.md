# Engineering review guide

I am interested in internships and mentorship focused on agent tooling, developer tools, and software engineering. I use AI-assisted development tools and focus on the surrounding engineering: explicit interfaces, persistent state, failure handling, and checks that make results inspectable.

## Choose a starting point

| Your area | Project | Review question |
| --- | --- | --- |
| Agent and developer tooling | [Autopilot](https://github.com/AkarshSharma2012/autopilot-skill) | What does a signed receipt prove, and what does it leave unknown? |
| Web applications and integrations | [QuarryFind](https://github.com/AkarshSharma2012/QuarryFind) | How should an application distinguish no result from an unavailable source? |
| State management and learning tools | [Live Mastery Tutor](https://github.com/AkarshSharma2012/live-mastery-tutor) | How can progress survive a new conversation without rewriting earlier scores? |
| Robotics and engineering workflows | [FRCstack](https://github.com/AkarshSharma2012/FRCstack-skill) | How do observations become a useful workbook without turning missing evidence into fabricated measurements? |

## Autopilot — portable agent workflows and artifact integrity

**Problem:** Agent hosts expose different tools and permissions, while files produced by a workflow need inspectable provenance.

**Implementation to inspect:** The skill adapts its workflow to observed capabilities. Its Node CLI creates Ed25519 receipts, and a browser verifier checks signatures and content hashes with Web Crypto.

**Engineering distinction:** A valid signature binds bytes to a signing key and declaration. It does not establish that instructions were followed or identify every AI-generated file.

[Protocol source](https://github.com/AkarshSharma2012/autopilot-skill/blob/main/skills/autopilot/scripts/lib/protocol.mjs) · [Protocol tests](https://github.com/AkarshSharma2012/autopilot-skill/blob/main/tests/protocol.test.mjs) · [CI configuration](https://github.com/AkarshSharma2012/autopilot-skill/blob/main/.github/workflows/ci.yml) · [Usage and documented checks](https://github.com/AkarshSharma2012/autopilot-skill#build-and-test)

## QuarryFind — evidence and failure semantics across public sources

**Problem:** Research across independent services encounters blocks, timeouts, and inconsistent responses. Those outcomes need different meanings from a confirmed lack of a match.

**Implementation to inspect:** A TypeScript engine, client-driven batches, streamed results, Supabase-backed state, and source-health fixtures. The frontend uses Next.js and Tailwind CSS.

**Engineering distinction:** A matching username is a lead, not proof of identity. The hosted application is owner-only; reviewers can inspect the public source, screenshots, and local setup instructions.

[Architecture](https://github.com/AkarshSharma2012/QuarryFind#how-it-works) · [Engine source](https://github.com/AkarshSharma2012/QuarryFind/tree/main/supabase/functions/_shared/engine) · [End-to-end tests](https://github.com/AkarshSharma2012/QuarryFind/tree/main/e2e) · [Local setup](https://github.com/AkarshSharma2012/QuarryFind#run-it-locally)

## Live Mastery Tutor — durable state and honest assessment

**Problem:** A conversational tutor can lose state, confuse exposure with mastery, or let corrected answers replace original performance records.

**Implementation to inspect:** A Python state tool atomically records progress, validates session identity, and retains first-attempt history. Portable course packs are versioned separately from learner state.

**Engineering distinction:** These are mechanisms for preserving and evaluating recorded work. Their presence alone does not prove improved learning outcomes.

[State engine](https://github.com/AkarshSharma2012/live-mastery-tutor/blob/main/skills/live-mastery-tutor/scripts/tutor_state.py) · [State tests](https://github.com/AkarshSharma2012/live-mastery-tutor/blob/main/tests/test_tutor_state.py) · [Validation workflow](https://github.com/AkarshSharma2012/live-mastery-tutor/blob/main/.github/workflows/validate.yml)

## FRCstack — evidence-backed engineering reports

**Problem:** Scouting and CAD assistance need to distinguish observed behavior, inferred geometry, and unknown information.

**Implementation to inspect:** Portable agent instructions, observation-ledger validation, Python summarization, and a multi-sheet Excel exporter that preserves raw observations and sources.

**Engineering distinction:** The repository does not bundle a trained robot tracker or a live Onshape connector. Broadcast footage cannot reveal hidden dimensions or mechanisms reliably.

[Workbook exporter](https://github.com/AkarshSharma2012/FRCstack-skill/blob/main/skills/frcstack/scripts/export_scouting.py) · [Workbook tests](https://github.com/AkarshSharma2012/FRCstack-skill/blob/main/tests/test_workbook.py) · [Documented capabilities](https://github.com/AkarshSharma2012/FRCstack-skill#what-is-implemented-and-what-is-not)

## Current research: Ram Lab

[Ram Lab](https://github.com/AkarshSharma2012/ram-lab) is in research and planning. Its proposed direction combines controlled agent failures, observable reactions, recovery verification, and Excel reports linked to individual events and claim evidence. It is not presented here as an implemented product or a completed benchmark.

## Start a conversation

[Open an opportunity discussion as a GitHub issue](https://github.com/AkarshSharma2012/AkarshSharma2012/issues/new?template=opportunity.yml) for internships, mentorship, or technical collaboration. Include a short description of the team or project and a public role or contact link.

