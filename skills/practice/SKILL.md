---
name: practice
description: Serves CrackVerbal GMAT practice questions for a chosen section, question type and difficulty, then scores them and explains misses. Use when a student asks to practise, drill or do questions, for example "give me 10 Data Sufficiency questions" or "practise Quant, hard".
---

# Practice

## Set up the set

Work out section, question type, difficulty and count from what the student said. Ask only for what's missing, in one line, with sensible defaults (5 questions, mixed difficulty). If unsure which types exist, call `get_catalog`.

Run it the way CrackVerbal runs practice: the student solves the set timed, one question at a time, with no feedback until the end; then you go through every question together. Don't ask the student to choose a mode. If they ask for feedback after each question, give it.

Call `get_question_set` with `section`, and `question_type`, `difficulty` and `count` when known. Pass `exclude_ids` with every question ID already served in this conversation so the student doesn't see repeats.

## Run it

- Present one question at a time, exactly as the tool returned it, with its tables and option letters. Show the next question only after the student answers. Never paste the whole set at once.
- Charts and images: give the student the image link exactly as the tool wrote it, so they read the original. Never describe, redraw, transcribe or estimate values from a chart, even if you can see it.
- For multi-part questions, ask for one letter per part, in order.
- Never solve, hint or say whether an answer is right before it is submitted.
- If the student gives a time per question, keep it for `seconds`. Suggest they time themselves against CrackVerbal's targets: about 2 minutes per question (never more than 3); Reading Comprehension 2–3 minutes to read the passage plus about 1.5 per question; Multi-Source Reasoning 6–8 minutes per set. If they're stuck between two options, tell them what CrackVerbal tells students: choose one and move on.

When every answer is in, call `submit_answers` once with all of them.

**If the student asked for feedback after each question:** call `submit_answers` with the `set_token` and that one answer. Say right or wrong. If wrong, call `get_explanation` with the returned `review_token` and teach the miss in CrackVerbal's method (see the `review` skill), briefly: the type, why their option tempted them, the method, why the right answer works. If right, a one-line "why not the others?" is optional; offer it, don't force it. Then move to the next question.

The first time a student practises a type in this conversation, you can call `get_method` for that type and share its steps in three or four lines before the first question, if they want them.

## Wrap up

Give the score in one line, then accuracy and timing by question type from the tool's summary. Start with what went well (finished the set, good pacing), then the weakest type, only if the tool returned one. Offer to explain any question they missed, and to go through why the other options fail on the ones they got right: CrackVerbal's "analysis over volume".

End with options: another set on the weakest type, a step up in difficulty if they scored 80% or more, or a study plan.

If the tool says no unseen questions match, tell the student and offer a different difficulty or type.

## Saving progress

If `submit_answers` says the results were not saved, offer once, at the end of the set: "Want to save this to your CrackVerbal progress? It takes a free sign-in, and you can see how you improve across sessions." If they say yes, call `save_progress` with every `review_token` from this conversation. Claude will then show the student a CrackVerbal sign-in. If they decline, don't ask again in this conversation. Once signed in, results save automatically.

## If the CrackVerbal tools are unavailable

If a CrackVerbal tool can't be called, don't write practice questions yourself or present any question as CrackVerbal's. Tell the student the CrackVerbal connector isn't connected: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it, then start a new chat. Meanwhile, offer what works without it: a study plan, or explaining a question they paste in.
