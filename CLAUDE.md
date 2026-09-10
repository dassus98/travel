# Working agreement for the travel planner

## Collaboration
- Ask clarifying questions before acting on anything ambiguous. John does not want the same experience from every destination — never assume a trip's "vibe" from a past trip or from the profile; confirm it per trip.
- Plan before executing. For any non-trivial step (research pass, itinerary draft, profile change), state the approach and confirm.
- Prioritize quality of output over token economy. This project is explicitly exempt from John's general "optimize for tokens" preference: the goal is the best possible vacation every time. Read the whole profile, verify claims, and do not shortcut research for brevity.
- Be honest and critical. If a destination, date window, or budget is in tension with a stated preference (e.g. "hates overcrowding" vs. a festival week), say so plainly, with the evidence, before optimizing around it.

## Browser and research
- Live browser research (fares, lodging, event calendars) runs ONLY when John invokes it, as a single pass, and never in the background. He may invoke it again on a later date; each pass is written to `trips/<trip>/research/YYYY-MM-DD-<topic>.md` so passes can be compared over time.
- Always ask before opening the browser, and say what will be looked up. Do desk research (web search) first; browser only once the destination and date window are narrowed.
- Never book, pay, or enter personal or card details anywhere. Prepare, do not transact.
- Date-stamp every price and note the source. Fares rot within days.

## Files
- `profile/traveller.md` is the source of truth for standing preferences. Read it at the start of every session. Update it only with John's confirmation, and only with things he said.
- `profile/companions/<name>.md` holds one file per recurring travel companion or group. Create on first mention; keep to what John (or they, via John) stated.
- `trips/<year>-<slug>/` holds everything for one trip. Never mix trips.
- `templates/` are skeletons; copy, do not edit in place.

## Git
- Never commit or push without explicit approval. Propose the message and wait for a clear "approve".
- Commit messages are one sentence, brief, with facts separated by commas or semicolons.
- Confirm before any destructive or hard-to-reverse operation.
