# quiz-me

Your agents wrote the code. Can you still answer for it?

`quiz-me` turns your coding agent into an honest examiner. It reads what changed in your repo recently, asks you 8 questions — mostly "why is it built this way?" and "what breaks if X fails?" — grades you out of 8 without flattery, and re-explains what you missed.

Because investors, customers, and incidents don't interview your agents. They interview you.

## Install

```
npx skills add shushukurov/quiz-me
```

Works with Claude Code, Codex, Cursor, and anything else that reads skills. Then say **"quiz me"** in your repo.

No installer? Tell your agent:

> Read https://raw.githubusercontent.com/shushukurov/quiz-me/main/QUIZ_ME.md and quiz me on this repo

## The ritual

I run this weekly on my own fintech, where agents write essentially all the code. Eight questions on whatever shipped that week. Below 6 of 8, I study and retake. The product isn't mine until I pass.

— [@runsagents](https://x.com/runsagents)

## Compatibility & limitations

Works anywhere an agent can read your repo and a file: Claude Code, Codex, Cursor, and other skills-aware agents. Grading quality depends on the model and on your git history — squash-everything repos give it less to work with. It is an exam for **you**, not a code review; run your review gates separately.

Version: v1.0.0 · License: CC0 (public domain — take it, no credit needed)

## Prior art

The quiz idea was championed in [A Field Guide to Claude: Finding Your Unknowns](https://claude.com/blog/a-field-guide-to-claude-fable-finding-your-unknowns) by Thariq Shihipar (Anthropic) — don't merge what you can't pass a quiz on. Related tools: [change-quiz](https://github.com/Neeeophytee/finding-unknowns-skills), [pr-quiz](https://github.com/dkamm/pr-quiz). quiz-me is the standalone, zero-dependency version of the ritual, framed for the people who answer for the code. Anthropic's [own research](https://www.anthropic.com/research/AI-assistance-coding-skills) found AI-assisted developers scored 17% lower on comprehension quizzes — that gap is the point.
