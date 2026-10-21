# CrackVerbal GMAT Prep

Free GMAT Focus practice from CrackVerbal, inside Claude. Ask in plain words and Claude serves real CrackVerbal questions, scores your answers, explains misses the way CrackVerbal's faculty teach, and builds a study plan around your weak areas.

## What you can do

- **Get started:** "Help me prep for the GMAT." A four-question check-in routes you to the right next step.
- **Find your weak areas:** "Where am I weak?" runs a short diagnostic, one question per question type.
- **Practise:** "Give me 10 Data Sufficiency questions, medium." Learn mode gives feedback after each question; test mode holds it to the end.
- **Review a miss:** "Why is my answer wrong?" walks through what the question tests, the trap and the method.
- **Plan:** "I have 8 weeks and 10 hours a week, target 655." You get a week-by-week plan.
- **Check progress:** "How am I doing?" shows your results by question type. Sign in with Google or an email code to keep them across sessions.

Data Insights (Data Sufficiency, Multi-Source Reasoning, Table Analysis, Two-Part Analysis, Graphics Interpretation) is available now. Quant and Verbal questions are being added.

## Install

**In Claude (web, desktop or mobile):**

1. Open **Customize > Plugins**, select **Add**, then **Add marketplace**.
2. Enter `Crackverbal-Main/crackverbal-gmat-plugin` and add it.
3. Find **CrackVerbal GMAT Prep** in the list and select **Add**.
4. Open the plugin's **Connectors** tab and connect **crackverbal-gmat**. Choose **Sign in when needed**: practice works without an account, and you sign in only when you want to save progress.
5. Start a new chat and say "Help me prep for the GMAT".

**In Claude Code:**

```
/plugin marketplace add Crackverbal-Main/crackverbal-gmat-plugin
/plugin install crackverbal-gmat@crackverbal
```

## What the plugin sends and stores

The plugin connects to one server run by CrackVerbal at `https://crackverbal-gmat-mcp.marketing-e89.workers.dev/mcp`.

- **Sent to CrackVerbal:** the section, question type and difficulty you ask for; the IDs of questions already shown in the conversation, so you don't get repeats; your answer letters and, if you give them, your times.
- **Stored by CrackVerbal:** one anonymous row per scored question (question ID, number correct, seconds, app name, timestamp). If you choose to sign in to save progress: your email, your name from Google if you use Google, and your saved results. No chat text.
- **Not read:** your Claude memory, chat history or files.

Answers and explanations stay on CrackVerbal's server until you submit, so Claude can't reveal them early.

Privacy policy: TO CONFIRM before submission
Support: TO CONFIRM before submission

## Troubleshooting

- **"The CrackVerbal connector isn't connected":** open Customize > Plugins > CrackVerbal GMAT Prep > Connectors and connect it.
- **"No unseen questions match":** you've seen every question for that filter in this conversation. Try another difficulty or type, or start a new conversation.
- **A chart doesn't show:** ask Claude to show the question again.

## License

Question content and explanations © CrackVerbal. See LICENSE.
