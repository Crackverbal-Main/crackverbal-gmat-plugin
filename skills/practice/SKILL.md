---
name: practice
description: Serves CrackVerbal GMAT practice questions for a chosen section, question type and difficulty, then scores them and explains misses. Use when a student asks to practise, drill or do questions, for example "give me 10 Data Sufficiency questions" or "practise Quant, hard".
---

# Practice

## Set up the set

Work out section, question type, difficulty and count from what the student said. Ask only for what's missing, in one line, with sensible defaults (5 questions, mixed difficulty). If unsure which types exist, call `get_catalog`.

Then ask which mode they want, unless they already said:

- **Learn mode** (default): feedback after each question.
- **Test mode**: no feedback until the end, like the real exam.

Call `get_question_set` with `section`, and `question_type`, `difficulty` and `count` when known. Pass `exclude_ids` with every question ID already served in this conversation so the student doesn't see repeats.

## Run it

- Present one question at a time, exactly as the tool returned it, including attached charts and tables. Keep the option letters.
- For multi-part questions, ask for one letter per part, in order.
- Never solve, hint or say whether an answer is right before it is submitted.
- If the student gives a time per question, keep it for `seconds`.

**Learn mode:** after each answer, call `submit_answers` with the `set_token` and that one answer. Say right or wrong. If wrong, call `get_explanation` with the returned `review_token` and teach the miss in CrackVerbal's method (see the `review` skill), briefly. Then move to the next question.

**Test mode:** collect every answer, then call `submit_answers` once with all of them.

## Wrap up

Give the score in one line, then accuracy and timing by question type from the tool's summary. Name the weakest type only if the tool returned one. Offer to explain any question they missed.

End with options: another set on the weakest type, a step up in difficulty if they scored 80% or more, or a study plan.

If the tool says no unseen questions match, tell the student and offer a different difficulty or type.

## Saving progress

If `submit_answers` says the results were not saved, offer once, at the end of the set: "Want to save this to your CrackVerbal progress? It takes a free sign-in, and you can see how you improve across sessions." If they say yes, call `save_progress` with every `review_token` from this conversation. Claude will then show the student a CrackVerbal sign-in. If they decline, don't ask again in this conversation. Once signed in, results save automatically.

## If the CrackVerbal tools are unavailable

If a CrackVerbal tool can't be called, don't write practice questions yourself or present any question as CrackVerbal's. Tell the student the CrackVerbal connector isn't connected: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it, then start a new chat. Meanwhile, offer what works without it: a study plan, or explaining a question they paste in.
