# Columb AI — Telegram Bot

Asynchronous Telegram bot built with `aiogram` v3. Connects to the AI service for LLM responses, supports image analysis with OCR, and manages user quotas via Telegram Stars.

## Features

- **Streaming responses** — text appears in real time
- **Image analysis** — send a photo, the bot reads text (OCR) and describes it
- **Chat history** — context preserved across messages, auto-summarized after 20 messages
- **`/new`** — start a new conversation (clears history)
- **Quota system:**
  - 5 free messages per day
  - 50 messages — 100 ⭐️
  - 200 messages — 300 ⭐️
  - Unlimited (1 month) — 500 ⭐️
- **Admin access** — unlimited usage, no quota
- **Group Chat Support** — responds to mentions (`@username`) and replies (Reply) in group chats. History is grouped by `chat_id`, and quotas are consumed by `user_id`.

## Managing Admins

Run from the **project root**:

```bash
make list-admins
make add-admin ID=123456789
make remove-admin ID=123456789
```

## Project Structure

- `bot.py` — entry point, initializes DB and starts polling
- `handlers.py` — all message and callback handlers
- `db.py` — SQLite: users, admins, quotas, subscriptions, chat history
- `llm.py` — AI service HTTP client (chat, image analysis, summarization)
- `admin_cli.py` — CLI for admin management
- `config.py` — environment variables
