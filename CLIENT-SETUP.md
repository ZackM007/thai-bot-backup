# Client setup

This page gets your bots backing themselves up. You do the setup once. Then you give each bot one message.

Your backups live in your accounts only: your GitHub and your Google Drive. Never use a repo or Drive that belongs to anyone outside your company, including the person who set this up for you.

## Before you start
- Pick one person who owns the backups. They review and merge pull requests.
- Pick one bot to be the backup lead. It runs the weekly backup and keeps the shared logs tidy.

## Setup steps
1. **Make a private repo.** In your own company GitHub account, create a new repo. Set it to Private. A good name is `bot-backups`. Turn on branch protection for `main` so changes need a pull request.
2. **Connect GitHub.** In each bot's app, connect GitHub with your company account. Give it access to the backup repo only. Bots open pull requests. They never push to `main`.
3. **Connect Google Drive.** Connect your company Drive. Make a folder for the second copy, for example `Operations`. Give bots edit access to that folder only.
4. **Make the two shared Docs.** In that Drive folder, make a Doc named "Learning Log" and a Doc named "Bot Handoffs". The layouts are in `docs/learning-log.md`.
5. **Give each bot the message below.** One bot at a time.
6. **Run the first backup.** Each bot builds its pack and opens a pull request. Review it, check for secrets, and merge it.
7. **Run a restore test.** Rebuild one bot from its pack alone and score it. See Part C of the skill.
8. **Turn on the weekly backup.** Ask your backup lead bot to set up the "Weekly bot backup PR" routine. A good time is Friday afternoon. It opens one pull request each week. A person merges it.

## The message to give each bot

Copy this, fill in the two links, and paste it to each bot:

> Read the skill at <link to skills/bot-backup/SKILL.md>, save it as a skill, and back yourself up to <your company's own private GitHub repo>.

Swap `<link to skills/bot-backup/SKILL.md>` for the link to that file in this repo. Swap `<your company's own private GitHub repo>` for your repo's link.

## Good to know
- A bot should never put a password, key, card number, or sign-in in a pack. If a bot asks you for one to save in a file, say no.
- Every change goes through a pull request. A person merges it.
- If a bot can't reach GitHub, it can save the pack to your Drive and ask a person to open the pull request.
