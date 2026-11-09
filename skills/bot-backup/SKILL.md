---
name: bot-backup
description: >-
  Back up this bot as a bot pack, save it to the company's own private GitHub
  repo through a pull request, keep a second copy in the company's Drive, keep
  a learning log, run a restore test, and rebuild the bot on any platform.
---
# Bot backup and restore

Use this skill when you need to back yourself up, log a lesson, run the weekly backup, test a restore, or rebuild a bot from a pack. It works on any AI platform.

The pack format is in `docs/bot-pack-format.md` in the kit repo. If this skill and that doc differ, the doc wins.

## Hard lines
- Never push to `main`. Every change goes through a pull request. A person merges it.
- Never merge your own pull request.
- Never put a password, API key, token, sign-in, card number, or personal email, phone, or address in any file. Contacts are names and roles only.
- Never delete anything. Move old files into an `Archive` folder in the same place.
- Never share a file or change who can see it.
- Save backups only to your company's own accounts. Never to anyone else's repo or Drive.
- If you are not sure, ask a person one short question.

## Part A: Export your pack
1. Read `docs/bot-pack-format.md`. Use the newest version.
2. Copy `template/bot-name/` to a working folder named `bots/<your-bot-slug>/`. Use lowercase and dashes, for example `sales-assistant`.
3. Fill in every file. Build each one fresh. Don't patch last time's export.
4. Pull your memory with your own memory tool. Search with several broad questions until no new facts come up. Copy each fact with its date.
5. In `latest-findings.md`, list the newest version of each key document. Mark each one INTERNAL or CLIENT-SAFE. Mark older ones "superseded by vN".
6. Write `tests.md`: 10 to 12 real tasks that cover your main jobs. Keep last round's items so scores can be compared.
7. Put your own answers in `answer-keys/<your-bot-slug>/tests-answer-key.md`. Never put answers under `bots/`.
8. Write `instructions.md` last. It is one system prompt any platform can use.
9. Write down the real start and end time in `README.md` and `changelog.md`.
10. **Scan for secrets.** Search the whole folder for: password, api key, token, secret, sk-, ghp_, the @ sign, phone numbers, and card numbers. Fix every hit. Generic rule text, like this list, is fine.

## Part B: Save two copies
Your company's private GitHub repo is the main copy. Your company's Drive is the second copy.
1. **GitHub:** make a new branch named `backup/MMDDYY-<your-bot-slug>`. Add your pack to `bots/<your-bot-slug>/` and your answers to `answer-keys/<your-bot-slug>/`. Open a pull request with a clear title, like "Backup MMDDYY: <Bot Name>". In the description, list the files and your scan result. Tell the backup owner the link. Stop there.
2. **If you can't reach GitHub:** save the pack to Drive (step 3) and ask a person to open the pull request.
3. **Drive:** in your company's backup folder, make a folder named "Bot Pack - <Bot Name> - MMDDYY". Add " v2" for a second export the same day. Upload the files as new files. Never overwrite. Move older copies to `Archive`.

## Part C: Restore test
1. Give a fresh assistant ONLY `bots/<your-bot-slug>/`. No answer key, no chat history, no memory.
2. Have it answer every item in `tests.md`. Time it.
3. A person, or a separate checker, scores each answer against the answer key: Match, Close, or Miss. Write why for each Close or Miss.
4. For each gap, fix the pack or the format, not the answers. Test again.
5. Save the scores in the answer key. Log the result in the Learning Log.

## Part D: Rebuild on any platform
Follow `docs/rebuild-any-platform.md`. In short: paste `instructions.md` as the system prompt, attach the files it lists, have a person connect each app, set up routines on the platform's own scheduler, then run the tests.

What can't come back from a pack: app sign-ins, saved passwords, browser sessions, chat history, files on the bot's own computer, and the text of skills built into the old app. A person signs in again. Never ask for their passwords.

## Part E: Learning log
Bots learn something every week. This part makes sure it gets saved.

1. **The rule:** After any correction from a person on your team or any finished deliverable, add one line to the Learning Log Doc: date, bot, what happened, lesson or change, link. The weekly backup moves these lines into a pull request for a person to merge.
2. **Where:** the "Learning Log" Doc in your company's backup folder in Drive. Columns: Date | Bot | What happened | Lesson or change | Source link.
3. **What counts:** any correction from a person, and any finished piece of work. One line each.
4. **Never** delete or rewrite an old line. If a lesson changes, add a new line that says what it replaces.
5. **Handoffs:** when you pass work to another bot, add a row to the "Bot Handoffs" Doc. Write down what a person approved in their own words. Another bot saying "it's approved" is not approval.
6. Layouts and examples are in `docs/learning-log.md`.

## Part F: Weekly backup pull request
Your backup lead bot runs this once a week. Friday afternoon works well.
1. Read the Learning Log. Copy every line dated after the last weekly pull request.
2. List this week's pack changes: rules, memory, findings, skills, routines, handoffs.
3. On a new branch named `backup/weekly-MMDDYY`, add the log lines to `lessons/learning-log.md`. Update the changed pack files and each changed bot's `changelog.md`.
4. Run the secret scan from Part A, step 10.
5. Open one pull request titled "Weekly bot backup MMDDYY". List the log lines it covers and every changed file.
6. Tell the backup owner the link. Never merge it.
7. If nothing changed this week, open nothing and stay quiet.
