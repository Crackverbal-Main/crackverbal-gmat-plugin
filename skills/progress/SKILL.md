---
name: progress
description: Shows the student's CrackVerbal GMAT progress, by question type, with what to work on next. Use when a student asks how they are doing, what their results are, how they have improved, or what to focus on.
---

# Progress

## Saved progress (signed-in students)

Call `get_progress`. It returns every saved result across sessions: questions done, accuracy by question type, the last 14 days, and the focus type.

If the student isn't signed in, Claude shows them a CrackVerbal sign-in when you call it. If they'd rather not sign in, use this conversation's results instead (below), and mention once that signing in keeps results across sessions.

Lead with one line: questions done and overall accuracy. Then a table, weakest first: Question type · Done · Accuracy · Last 14 days. Name the focus type the tool returned. Use only the numbers returned. Don't estimate a GMAT score from practice accuracy; point the student to an official practice exam for that.

## This conversation only

Without sign-in, add up the `submit_answers` results in this conversation by question type: attempted, correct, accuracy, and time against target where given. Same table. With fewer than 3 questions in a type, say the sample is too small to judge.

End with options: a practice set on the focus type, review of misses, or a study plan.

## If there are no results yet

Say there's nothing to show yet and offer a diagnostic or a practice set.

## If the CrackVerbal tools are unavailable

If a CrackVerbal tool can't be called, don't present any numbers as saved CrackVerbal progress. Tell the student the CrackVerbal connector isn't connected: in Claude, open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it, then start a new chat.
