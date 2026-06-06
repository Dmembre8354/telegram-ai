# Telegram AI Agent Starter Kit Workspace Rules

Guidelines and instructions for the Antigravity Agent when working on this workspace.

## 1. Project Stack & Architecture

- **Telegram Bot (`bot/`)**: Built using `aiogram` (v3.10) and `aiosqlite` for asynchronous SQLite database operations (`data/bot_db.sqlite3`).
- **AI Inference Service (`ai_service/`)**: Built using `FastAPI` and `uvicorn`. Uses `transformers` (`Qwen/Qwen2.5-0.5B-Instruct` and `Salesforce/blip-image-captioning-large` with `EasyOCR`).
- **Fine-Tuning (`Dockerfile.train` / `ai_service/train.py`)**: Runs LoRA fine-tuning using `peft` and `trl`.

## 2. Core Rules & Constraints

- **Non-blocking Inference**: 
  - LLM/VLM/OCR inference runs synchronously and is highly blocking.
  - **Rule**: Always offload blocking operations to separate threads using `asyncio.to_thread` when calling them from async FastAPI routes or aiogram handlers.
- **Quota & Payments**:
  - The default free quota is 5 requests per user per day.
  - Subscriptions and extra package purchases are handled via **Telegram Stars** (`XTR` currency).
  - Admins (registered in the `admins` table) have unlimited quota bypass.
- **Context Compression**:
  - Chat history reaches limit at 20 messages. Once reached, the older 10 messages are summarized into a `summary` type role in `chat_history`, and the recent 10 messages are preserved.
- **Multi-GPU / CPU Support**:
  - Set `USE_GPU=true` in `.env` to leverage Nvidia GPUs for training/inference.

## 3. Formatting & Code Conventions

- **Language Constraint**:
  - All user-facing application text, labels, prompt configurations, and responses must be strictly in English.
- **Database Operations**:
  - Direct database interaction should go through the wrapper functions in `bot/db.py`.
  - Always use `aiosqlite` methods asynchronously and ensure commits are made when modifying data.
- **Telegram UI/UX Updates**:
  - When updating message text (e.g. streaming chunks), wrap calls in `try/except TelegramBadRequest` to prevent crashes when a user rapidly invokes commands or cancels generation.
