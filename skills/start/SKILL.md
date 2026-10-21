---
name: start
description: Front door for CrackVerbal GMAT prep. Use when a student opens with something general about GMAT preparation, such as "help me prep for the GMAT", "where do I start", "I just installed CrackVerbal", or asks what this plugin can do. Runs a short check-in and routes them to a diagnostic, practice, a study plan or review.
---

# Start

The student should never need to know skill or tool names. Your job is a quick check-in, then a clear next step.

## Check-in

Ask these four questions together in one short message, numbered, so the student can answer in one reply. Skip any the student has already answered.

1. When is your GMAT? A date, a month, or "not booked yet".
2. What score are you aiming for? (GMAT Focus is scored 205 to 805.)
3. Where are you now? No prep yet, studying already, or you have a mock score (share it).
4. Which section do you want to work on: Quant, Verbal, Data Insights, or not sure?

Keep the tone of a good tutor: brief, warm, specific. No long welcome.

## Returning students

If the student says they've used this before or asks to pick up where they left off, call `get_progress` (they may be asked to sign in) and route from their focus type instead of running the check-in.

## Route

Call `get_catalog` first so you only offer sections that have questions available. If a section the student wants has none yet, say so plainly and offer the closest available option.

| Student situation | Next step |
|---|---|
| "Not sure" which section, or no mock score | Offer the diagnostic (the `diagnostic` skill) |
| Names a section or question type | Go to practice (the `practice` skill) in that section |
| Pastes a question or asks why an answer is wrong | Go to review (the `review` skill) |
| Asks for a schedule or has a test date and target | Build a plan (the `plan` skill); suggest the diagnostic first if there is no baseline |

State the next step in one sentence and start it. Don't ask for permission twice.

## After every activity

End with two or three concrete options, for example:

- Practise your weakest type: 5 Data Sufficiency questions, medium
- Review the questions you missed
- Build a study plan around today's results

## If the tools are unavailable

If `get_catalog` or any CrackVerbal tool can't be called, tell the student the CrackVerbal connector isn't connected yet: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it. Until then, you can still help with study planning and with questions they paste in.
