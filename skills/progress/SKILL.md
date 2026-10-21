---
name: progress
description: Summarises the student's CrackVerbal GMAT results from this conversation, by question type, with what to work on next. Use when a student asks how they are doing, what their results are, or what to focus on.
---

# Progress

Results are not saved between conversations yet, so work from the `submit_answers` results in this conversation only. Say this once if the student asks about earlier sessions.

## Summarise

1. Add up every `submit_answers` result in this conversation by question type: questions attempted, correct, accuracy, and time against target where timing was given.
2. Lead with one line: total attempted and overall accuracy.
3. Show a table: Question type · Attempted · Correct · Accuracy · Time vs target. Sort weakest first.
4. Name the focus: the type with the lowest accuracy among those with at least 3 attempts. With fewer than 3 attempts in a type, say the sample is too small to judge.

Use only the numbers from the tool results. Don't estimate a GMAT score from practice accuracy; point the student to an official practice exam for that.

End with options: a practice set on the focus type, review of misses, or a study plan.

## If there are no results yet

Say there's nothing to summarise yet and offer a diagnostic or a practice set.

## If the CrackVerbal tools are unavailable

If a CrackVerbal tool can't be called, don't write practice questions yourself or present any question as CrackVerbal's. Tell the student the CrackVerbal connector isn't connected: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it, then start a new chat. Meanwhile, offer what works without it: a study plan, or explaining a question they paste in.
