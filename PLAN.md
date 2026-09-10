# Travel planner — build plan (v1, 2026-09-03)

## Goal
An ad-hoc, invoke-when-needed planner that (1) never re-asks standing facts, (2) always asks what is trip-specific, (3) researches only on command, (4) presents 2–3 options on the cost / experience / friction frontier, and (5) learns from debriefs.

## Design decisions (from Chitra, 2026-09-03)
- Surface: Cowork skill (`/plan-trip`) + files in this folder. Not a claude.ai Project. (Trade-off accepted: no phone access; gains web search, browser, spreadsheets, memory.)
- Intake: adaptive conversation, not a fixed questionnaire. The skill asks only what profile + destination cannot answer, and re-asks when a destination's purpose is ambiguous.
- Trade-offs: never pick; show 2–3 options built on different assumptions.
- Research: web search freely during desk research; browser only when Chitra invokes it, one pass per invocation, date-stamped, never continuous.
- Quality over token economy.
- Debrief step included; writes to profile only with confirmation.

## Stages
Each stage ends in a reviewable state. Commit only on approval.

0. Scaffold — CLAUDE.md, README.md, PLAN.md, profile/, templates/, skills/plan-trip/SKILL.md, skill saved to account. Verify: tree matches README; SKILL.md loads; profile reflects only stated facts. **(this session)**
1. Pilot brief — `trips/2027-iberia/brief.md` with known facts, flagged tensions, and open intake questions. Verify: every open question is one the profile cannot answer. **(this session)**
2. Pilot intake — answer open questions in conversation; companion files for Amy and Kaam (done 2026-09-10); freeze the brief. Verify: no "TBD" left that affects destination choice.
3. Desk research — web search: Easter 2027 calendar effects in PT/ES, weather and sea temps for the window, ETIAS status, typical YYZ fares, neighbourhood safety/cleanliness/crowding reputations, food scenes vs. lactose. Output `research/YYYY-MM-DD-desk.md`. Verify: each claim has a source and a date.
4. Options — `options.md`: three destination-level options with different assumptions (e.g. Lisbon shoulder-calm vs. Barcelona post-Easter vs. Madrid + Valencia day-trip for beach). Verify: totals reconcile to `budget.xlsx`; each option lists its biggest risk against Chitra's hard dislikes.
5. Live research (on invocation only) — browser pass for fares/lodging on the chosen option(s). Output `research/YYYY-MM-DD-live.md`. Re-runnable on later dates; skill diffs against the previous pass.
6. Itinerary + budget — `itinerary.md`, `budget.xlsx` with per-person split for three travellers. Verify: one anchor per day, buffer half-day present, dairy notes on food picks.
7. Debrief (after trip, ~April 2027) — `debrief.md`; propose profile/companion updates; propose SKILL.md changes. Verify: every profile change traces to a debrief line Chitra confirmed.

## Deliberately not built
- No automated fare alerts or scheduled runs (Chitra wants invocation-only).
- No booking. Prepare only.
- No second copy of instructions in a claude.ai Project (avoid drift). Revisit if phone-side use becomes a real need.

## Open risks
- Pearson-only + $2,500 all-in + late-March Europe is tight; research will say whether it's realistic for the pilot or whether the target should be per-trip.
- Amex Cobalt acceptance in Europe is patchy; Visa remains the working card.
