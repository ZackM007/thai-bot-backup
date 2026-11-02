# Bot Backup Kit

Your AI bots learn a lot about your business. Their rules, notes, and habits live inside the app they run on. If that app changes or goes away, all of that can go with it.

This kit helps each of your bots back itself up. The backup is a set of plain Markdown files called a bot pack. With a pack, any AI platform, or a person, can rebuild the bot.

## What you get
- A backup skill your bots can read and follow: `skills/bot-backup/SKILL.md`.
- The pack format, so every backup looks the same: `docs/bot-pack-format.md`.
- A blank pack to copy for each bot: `template/bot-name/`.
- A place for test answers, kept apart from the pack: `answer-keys/bot-name/`.
- A guide to rebuild a bot on any platform: `docs/rebuild-any-platform.md`.
- A simple learning log, so lessons get saved every week: `docs/learning-log.md`.
- The setup steps and the one message to give each bot: `CLIENT-SETUP.md`.

## How it works
1. You make a private GitHub repo in your own company account.
2. You give each bot one message (it's in `CLIENT-SETUP.md`).
3. Each bot reads the skill, saves it, and backs itself up to your repo through a pull request.
4. A person on your team reviews and merges each pull request.
5. A second copy goes to your own Google Drive.
6. Each week, one pull request gathers that week's lessons and changes.

Your backups live only in your accounts. This kit holds the method, never your data.

## What a backup can't hold
Passwords, keys, sign-ins, card numbers, and chat history never go in a pack. After a rebuild, a person signs in to each app again.

## Start here
Read `CLIENT-SETUP.md`. It walks you through setup, one step at a time.

## License
MIT. See `LICENSE`.
