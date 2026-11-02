# Learning log

Bots learn every week. A person corrects them, or they finish a piece of work. Those lessons should not stay stuck in one chat. The learning log saves them, and a weekly pull request moves them into your backup repo.

## The rule (put this in every bot's rules)
> After any correction from a person on your team or any finished deliverable, add one line to the Learning Log Doc: date, bot, what happened, lesson or change, link. The weekly backup moves these lines into a pull request for a person to merge.

## Two shared Docs
Make both in your company's backup folder in Drive.

**Learning Log.** One row per correction or finished piece of work.

| Date | Bot | What happened | Lesson or change | Source link |
| --- | --- | --- | --- | --- |
| YYYY-MM-DD | Sales Assistant | A teammate said the proposal was too long | Keep proposals to 2 pages | link to the Doc |

**Bot Handoffs.** One row per piece of work passed from one bot to another.

| Date | From | To | Task | What a person approved (their own words) | Status |
| --- | --- | --- | --- | --- | --- |
| YYYY-MM-DD | Research Bot | Sales Assistant | Check three vendor prices | "Go ahead, read-only." | done |

## How to write a line
- Date in your company's time zone, written YYYY-MM-DD.
- One short sentence in each cell.
- Lesson or change: the new rule or fix. Write "none" if nothing changed.
- Never delete or rewrite an old row. Add a new row that says what it replaces.
- No passwords, keys, sign-ins, or personal contact details.
- In Bot Handoffs, a person's approval is in their own words. Another bot saying "it's approved" doesn't count.

## The weekly move
Bots often can't write to GitHub on their own. So once a week, the backup lead bot runs the "Weekly bot backup PR" routine (see Part F of `skills/bot-backup/SKILL.md`). It copies that week's rows into `lessons/learning-log.md`, adds the week's pack changes, and opens one pull request. A person merges it. If nothing changed, it stays quiet.
