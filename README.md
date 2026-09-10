# Travel planner

A Claude-driven, ad-hoc vacation planner. Invoke `/plan-trip` in Cowork (or open this folder and say what you want to plan). The skill reads `profile/traveller.md`, runs an adaptive intake for the trip at hand, researches, and presents 2–3 options along the cost / experience / friction frontier rather than picking one.

```
travel/
  CLAUDE.md                 working agreement (read this first)
  PLAN.md                   staged build plan for the tool itself
  profile/
    traveller.md            Chitra's standing constraints and tastes
    companions/             one file per recurring companion or group
  templates/                skeletons copied into each trip folder
  skills/plan-trip/         the skill (also saved to the Claude account)
  trips/<year>-<slug>/      one folder per trip
    brief.md                intake result: who, when, what this trip is for
    options.md              2–3 frontier options with trade-offs
    itinerary.md            the chosen plan
    budget.xlsx             cost model
    research/               date-stamped research passes
    debrief.md              post-trip: what actually worked, written back to profile
```

Workflow per trip: brief → desk research → (ask) live research → options → pick → itinerary + budget → debrief.
