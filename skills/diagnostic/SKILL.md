---
name: diagnostic
description: Runs a short CrackVerbal GMAT diagnostic, one question per question type, and reports the student's weakest areas. Use when a student asks where they stand, what they are weak at, how they would do on the GMAT, or wants a baseline before a study plan.
---

# Diagnostic

## Run it

1. Call `get_diagnostic_set`. Pass `sections` only if the student limited the scope; otherwise leave it out to cover every available section.
2. If the result says some sections are not available yet, tell the student in one line which sections this diagnostic covers.
3. Say how many questions there are and that the diagnostic works like the exam: no feedback until the end. Suggest they note how long each question takes, if they want timing in the report.
4. Present one question at a time, exactly as the tool returned it, including any attached chart or table. Show the option letters. For questions with several parts, ask for one letter per part.
5. Never solve, hint or comment on whether an answer is right until all answers are submitted. If the student asks for help mid-way, say you'll go through everything at the end.
6. Collect each answer as letters. If an answer is ambiguous or missing a part, ask again for that part only.
7. When all questions are answered, call `submit_answers` once with the `set_token` and every answer, plus `seconds` per question if the student gave times.

## Report

Lead with the result in one line: score and the weakest question type. Then a compact table:

| Question type | Result | Time vs target |
|---|---|---|

Then two or three sentences on what the pattern suggests, using only the numbers returned. One question per type is a small sample: say so, and recommend a focused practice set on the weakest type to confirm it.

Keep the `review_token`. Offer to walk through any missed question; when they accept, call `get_explanation` with the `review_token` and the question ID, and teach it the way the `review` skill describes.

End with next-step options: practise the weakest type, review misses, or build a study plan.

## Saving progress

If `submit_answers` says the results were not saved, offer once, at the end of the set: "Want to save this to your CrackVerbal progress? It takes a free sign-in, and you can see how you improve across sessions." If they say yes, call `save_progress` with every `review_token` from this conversation. Claude will then show the student a CrackVerbal sign-in. If they decline, don't ask again in this conversation. Once signed in, results save automatically.

## If the CrackVerbal tools are unavailable

If a CrackVerbal tool can't be called, don't write practice questions yourself or present any question as CrackVerbal's. Tell the student the CrackVerbal connector isn't connected: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it, then start a new chat. Meanwhile, offer what works without it: a study plan, or explaining a question they paste in.
