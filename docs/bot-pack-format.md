# Bot pack format

Version 1. A bot pack is a folder of plain Markdown files. Together they hold everything needed to rebuild one bot, except secrets and sign-ins.

## Folder layout
In your company's private backup repo:

```
bots/<bot-slug>/          one folder per bot
answer-keys/<bot-slug>/   test answers, kept apart from the pack
lessons/learning-log.md   the weekly log lines (made by the first weekly backup)
```

## Files in each pack
- `README.md`: what the bot does, who it works for, how to restore it, and the export date and time.
- `profile.md`: name, title, description, and settings that are not secret.
- `rules.md`: standing rules and hard lines, word for word.
- `memory.md`: every fact the bot can read from its own memory, with dates.
- `latest-findings.md`: for each key document, its name, link, newest version, an INTERNAL or CLIENT-SAFE flag, and "superseded by vN" for older versions. Note any documents that disagree.
- `contacts.md`: people the bot works with. Name, company, role, and what they decide. Main contact first. No emails, phones, or addresses.
- `folder-map.md`: the folders and repos the bot uses, and what lives where.
- `naming.md`: the version naming rule. Every version is a new file, never an overwrite.
- `skills/README.md` plus `skills/<name>.md`: the full text of each skill the bot uses. For skills built into the app that can't be copied, write the name and 2 or 3 lines on what it does.
- `skills/bot-backup.md`: a copy of the kit's `skills/bot-backup/SKILL.md`.
- `routines.md`: each scheduled job. Name, owner, schedule with time zone, the prompt word for word, and what it does when nothing changed. Write "none" if there are none.
- `connectors.md`: the apps the bot connects to and what each is for. Names only.
- `handoff.md`: work in progress, open loops, what a rebuilt bot should do first, and who connects each app.
- `sources.md`: files outside the pack that the rules or skills point to, with links and the date checked.
- `tests.md`: 10 to 12 real tasks that cover the bot's main jobs. Keep last round's items.
- `changelog.md`: what changed since the last export.
- `instructions.md`: one ready-to-paste system prompt for any AI platform. The top lists the files to attach.
- `built-in-behaviors.md`: what the app did for the bot on its own, and what to do instead on a plain platform.

`answer-keys/<bot-slug>/tests-answer-key.md`: the bot's own answers today, plus restore scores. A restore test never sees this folder.

## Rules
- No passwords, API keys, tokens, sign-ins, card numbers, or personal emails, phones, or addresses in any file. Scan before saving.
- Plain Markdown. Short sentences. Easy words.
- Rebuild the whole pack at each export. Don't patch old files.
- Main copy: your private GitHub repo, through a pull request. Never push to `main`.
- Second copy: your Drive, in a folder named "Bot Pack - <Bot Name> - MMDDYY".
- Write `instructions.md` last, after the other files. Keep it under about 8,000 words.
