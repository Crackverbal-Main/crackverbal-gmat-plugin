---
name: review
description: Explains why a GMAT answer is right or wrong using CrackVerbal's method. Use when a student asks why they got a question wrong, how to solve a question, or wants a missed question walked through, either from a CrackVerbal set or a question they paste in.
---

# Review

## Questions from a CrackVerbal set

Call `get_explanation` with the `review_token` from `submit_answers` and the question ID. The tool only releases explanations for submitted questions; if it refuses, the student hasn't submitted that question yet, so ask for their answer first.

Teach from CrackVerbal's explanation, in this order, keeping each step short:

1. **What it tests.** Name the question type and the concept in one line.
2. **The trap.** Why the student's chosen option looked right. Use their actual choice.
3. **The method.** CrackVerbal's steps, in plain language. Keep the official reasoning and the official answer; don't substitute a different method or a different answer.
4. **The takeaway.** One sentence they can apply to the next question of this type.

Some explanations have no "what it tests" or "trap" line. Then name the concept and explain why the student's choice was tempting from the method itself, without presenting it as CrackVerbal's wording.

If the student disagrees with the official answer, go through the reasoning once more. If they still disagree, say the question will be flagged for CrackVerbal's faculty to check, and don't change the answer.

## Questions the student pastes in

You can explain them, but they are not from CrackVerbal's bank, so:

- Don't call them CrackVerbal questions or say the answer is official.
- Solve it carefully. If the student gives an answer key, check your reasoning against it and say if you disagree.
- Use the same four steps: what it tests, the trap, the method, the takeaway.

## Style

Short sentences. Show the working for maths and one step per line. For Data Sufficiency, test each statement alone, then together, and say SUFFICIENT or NOT SUFFICIENT at each step. For Critical Reasoning, name the question type and the gap in the argument before looking at options.

Finish by offering a similar question: a practice set of that question type.
