# Rebuild a bot on any platform

Use this guide to rebuild a bot from its pack on any AI platform. Most chat and agent tools take a system prompt and some reference files. That is all you need.

## Before you start
- You need: the pack in `bots/<bot-slug>/`, a person who can sign in to your apps, and a platform that takes a system prompt and reference files.
- A person signs in to every app. Never put a password, key, or sign-in in a file or chat.
- Keep `answer-keys/` away from the bot you are rebuilding. A person uses it to score the tests.

## Steps
1. Make a new assistant with the bot's name.
2. **System prompt:** paste `instructions.md` from the line "PASTE BELOW THIS LINE" to the end.
3. **Reference files:** attach the files listed at the top of `instructions.md`. If the platform has a skills feature, load the files in `skills/` there, one skill each.
4. **Apps:** a person connects each app in `connectors.md`. Use read-only access where the bot only reads. Limit write access to the folders it needs.
5. **Schedules:** set up each routine in `routines.md` with the platform's own scheduler. Copy the prompt word for word. Use the same time zone.
6. **Shared Docs:** make sure the "Learning Log" and "Bot Handoffs" Docs exist (see `docs/learning-log.md`).
7. **Test:** give the bot `tests.md`. Score the answers against `answer-keys/<bot-slug>/`. Fix the pack and test again.
8. Do the "first things" list in `handoff.md`.

Don't attach `tests.md` until test time. Never attach `answer-keys/` or `archive/`.

If the platform limits how many files you can attach, keep `instructions.md`, `built-in-behaviors.md`, `memory.md`, `latest-findings.md`, and the skills. Merge the rest into one `reference.md`.

## Words that mean different things on different platforms

| Word | What it means anywhere |
| --- | --- |
| Skill | A reusable instruction file. Load it as a skill, or attach it and tell the bot when to read it. |
| Memory | A notes file: `memory.md` plus `latest-findings.md`. Update them at the end of each job. |
| Routine | A scheduled task. A saved prompt plus a time or trigger. Use the platform scheduler, cron, or GitHub Actions. |
| Connector | An app connection, like email, calendar, Drive, or GitHub. |
| Vault | A password manager a person controls. Its contents never go in files. |
| Draft | A message a person reviews and sends. |

## How to swap built-in app habits for plain rules
Many apps do things for a bot without being asked. On a plain platform, write those habits into the instructions. Each pack's `built-in-behaviors.md` lists them. Common ones:

- **Sending messages.** The old app may have shown drafts for a person to send. Instead: save an email draft, tell the person, and stop. The bot never sends on its own.
- **Approvals.** The old app may have paused risky actions for a yes. Instead: ask in chat first before sending, posting, sharing, deleting, overwriting, buying, or pushing to `main`. No answer means no.
- **Messages between bots.** The old app may have let bots message each other. Instead: use the shared "Bot Handoffs" Doc. One lead bot is the hub.
- **Routines.** Use the platform's own scheduler. Write each job down: name, schedule with time zone, prompt word for word, owner, and what to do when nothing changed (stay quiet). A routine drafts and tells a person. It never sends.
- **Code and repo changes.** Use a branch and a pull request. A person merges.
- **Sign-ins and payments.** The bot stops and hands them to a person.

## New information, new decisions
A written rule stands until real new information arrives. Then a person on your team decides again. A rebuild does not change any rule by itself.

## What can't come back
App sign-ins, saved passwords, browser sessions, chat history, files on the bot's own computer, and the text of skills built into the old app.

## After the rebuild
Time how long it took. Log the time and the test scores in the Learning Log. Fix anything in this guide or the pack that slowed you down.
