# Discord Task Management Bot

A Discord bot that stores your class tasks and **automatically posts task announcements** and a
**daily summary** to a channel, on schedules you choose. Everything is saved in a local SQLite
database, so schedules survive restarts.

- Default timezone: **Asia/Manila (UTC+8)**
- Built with Python, discord.py, APScheduler and SQLite

---

## Setup

Install Python 3.10+, then install dependencies with `pip install -r requirements.txt`. Create a Discord application and bot in the Developer Portal, invite it with the `bot` and `applications.commands` scopes, and grant View Channels, Send Messages and Embed Links.

Copy `.env.example` to `.env` and set `DISCORD_TOKEN` to your bot token. Optionally set `GUILD_ID` for instant command sync. Keep the token secret. Run the bot with:

```bash
python main.py
```

All schedule times use `TIMEZONE` (default `Asia/Manila`). SQLite is created at `data/taskbot.db`; configure `DATABASE_PATH` to change it.

## Commands

- `/add-task`, `/tasks`, `/edit-task`, `/delete-task`, `/task-status`
- `/schedule`, `/schedules`, `/pause`, `/resume`, `/editschedule`, `/deleteschedule`
- `/daily-summary` to configure the summary of pending tasks

Set `RESTRICT_TO_MANAGERS=true` to limit changes to members with Manage Server. Run tests with `python -m unittest discover -s tests -v`.

See the project files and command help for scheduling frequencies, date formats, timezone, persistence and recovery behavior.
