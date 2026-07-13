# quiz-me

Your agents wrote the code. Can you still answer for it?

`quiz-me` is a single prompt file that turns your coding agent into an honest examiner. It reads what changed in your repo recently, asks you 8 questions — mostly "why is it built this way?" and "what breaks if X fails?" — grades you without flattery, and re-explains what you missed.

Because investors, customers, and incidents don't interview your agents. They interview you.

## Use it

Tell your agent (Claude Code, Codex, Cursor — anything that can read a URL and your repo):

> Read https://raw.githubusercontent.com/shushukurov/quiz-me/main/QUIZ_ME.md and quiz me on this repo

That's the whole install.

## The ritual

I run this weekly on my own fintech, where agents write essentially all the code. Eight questions on whatever shipped that week. If I can't pass, I don't get to call the product mine yet.

— [@runsagents](https://x.com/runsagents)
