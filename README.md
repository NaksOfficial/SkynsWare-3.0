# Project Title
Roblox Place Map GUI — Lightweight Luau Script

---

> **Short description:** A lightweight Luau script that creates a custom draggable GUI and a near-1:1 map preview of a selected place. The script is minimal: it is triggered by a single button; all other behavior is handled inside the game scripts. This repository contains a GitHub- and Monocode-friendly README in English and Russian.

---

## Badges

![Roblox](https://img.shields.io/badge/platform-Roblox-blue)
![Lua](https://img.shields.io/badge/language-Luau-orange)
![License](https://img.shields.io/badge/license-MIT-green)

---

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [One-button behavior — Important note](#one-button-behavior)
4. [How it works (high level)](#how-it-works-high-level)
5. [Installation / Usage (for GitHub & Monocode)](#installation--usage)
6. [Security & Obfuscation Disclosure](#security--obfuscation-disclosure)
7. [Roblox Compliance & TOS](#roblox-compliance--tos)
8. [Limitations & What it DOES NOT do](#limitations--what-it-does-not-do)
9. [FAQ](#faq)
10. [License](#license)
11. [Contact / Support](#contact--support)

---

## Overview
This Luau script creates a **custom GUI** (programmatically) that adapts to the client screen, is draggable/clickable and contains a close button. It also generates a **visual map preview** of the selected place using only safe in-game data (terrain shape, approximate object positions). The script is intentionally minimal in surface interactions: *you press a single UI button to initialize the system, then the rest is handled by server/client scripts inside the place.*

The main goals are:
- Simple integration into your place
- Minimal attack surface (no external communication)
- Protect author IP via obfuscation while remaining compliant and transparent

---

## Features
- Programmatically created GUI that scales to screen and DPI
- Draggable UI frame; close button
- Map preview: near-1:1 top-down layout based on place data (terrain and object locations)
- Single-button activation (the user only needs to click one button in-game)
- Fully runs inside Roblox (no external HTTP or executors required)

---

## One-button behavior — Important note
**This product intentionally operates from a single in-game button.**
- To use: the player joins the place and clicks the UI button (provided by the place). After click — the rest of the GUI/map system runs automatically on the client and via in-place scripts.
- The repository contains the GUI generator and the supporting scripts, but the only user-facing control required is this single button.

This design simplifies user experience, reduces permission prompts, and lowers the chance of accidental misuse.

---

## How it works (high level)
1. A place script spawns the button in the player's GUI when they join.
2. The button fires a local script that runs the GUI builder: the builder creates frames, sets up automatic scaling, drag handlers, and the close button.
3. On activation, the system queries allowed in-place data (terrain, public parts, or simplified metadata exposed by the developer) and renders a top-down visual representation.
4. Rendering is done using safe, native Roblox UI objects (Frames, ImageLabels, etc.) — no models are copied, no assets are downloaded.

**Note:** The system only uses data the place owner already has access to. It does not fetch or copy external assets or protected models.

---

## Installation / Usage (for GitHub & Monocode)
**Repository contents:**
- `src/` — main Luau scripts (client + server as needed)
- `README.md` — this file
- `examples/` — optional example setup showing the single-button placement

**Quick start:**
1. Open Roblox Studio and your place.
2. Import `src/` scripts into appropriate folders (StarterGui for client LocalScripts, ServerScriptService for server helpers if present).
3. Place the provided `ButtonStarter` (or use the example) where players will get the single button in their GUI on join.
4. Publish and test: join the place and press the button.

**Monocode tips:**
- Monocode is primarily a snippet viewer — paste the `README.md` and main `src/` LocalScript code snippet into your Monocode page for easy sharing.
- Ensure the example LocalScript is visible in Monocode so reviewers can quickly see that the script only constructs UI and reads in-place data.

---

## Security & Obfuscation Disclosure
- The code in this repository may contain obfuscated Luau intended to **protect intellectual property**: unique layout math and rendering logic. Obfuscation is applied **only to protect original implementation** and not to conceal malicious behavior.
- The script **does not** perform external network calls, does not require executors, and does not access user personal data.
- If you are a reviewer (on GitHub or Monocode) and want to audit the logic, contact the author — a non-obfuscated review copy can be provided under the conditions in the `CONTRIBUTING` section.

### Why obfuscate?
- Prevent unauthorized copying or republishing of a novel GUI and map rendering algorithm.
- Protect the time and effort of the developer.

If you are a platform moderator and require additional evidence of safety, contact the repository owner for an audit copy.

---

## Roblox Compliance & TOS
This project is built to comply with Roblox Terms of Service and Community Standards:
- No exploitative or cheating behavior
- No copying of third-party assets
- No external HTTP calls to bypass restrictions
- All code executes within the Roblox sandbox

If you suspect any part of the code violates rules, please open an issue and the author will respond and provide clarifications.

---

## Limitations & What it DOES NOT do
- ✖ Does NOT copy models/assets from other places
- ✖ Does NOT download or install external code or modules
- ✖ Does NOT require or use external executors or elevated permissions
- ✖ Does NOT access player private data (contacts, device IDs, IP addresses, etc.)

---

## FAQ
**Q: Is this an exploit or a cheat?**
A: No. The script uses only Roblox-native UI and in-place data.

**Q: Why is the code obfuscated?**
A: To protect unique algorithms and UI behavior. The author can provide a clear copy for audit purposes.

**Q: Can I use this in games I don't own?**
A: No. Use only in your own games or with explicit permission from the place owner.

**Q: Will this be accepted by Roblox moderation?**
A: The author designed it to be compliant. If moderators have concerns, the author will cooperate.

---

## Contributing
If you want to contribute or request an audit:
- Open an issue describing your request.
- Provide a short rationale for needing a de‑obfuscated copy.
- The author may provide a non-obfuscated review copy to trusted moderators or collaborators under an agreement.

---

## License
This repository is licensed under the **MIT License** — see `LICENSE` for details.

---

## Contact / Support
If you need a review copy, screenshots, or more details, open an issue or contact the repository owner on GitHub.

---

# Русская версия (Russian version)

## Название проекта
Roblox Place Map GUI — лёгкий Luau‑скрипт

## Краткое описание
Скрипт создаёт кастомный перетаскиваемый GUI и визуализацию карты плейса (почти 1:1) и прост в использовании: **всё управляется одной кнопкой**, остальное — внутренние скрипты плейса.

## Функции
- Программное создание GUI, адаптация под экран
- Перетаскиваемая панель, кнопка закрытия
- Визуализация карты на основе данных плейса
- Одна кнопка для запуска (все взаимодействия внутри плейса)
- Работает полностью в пределах Roblox

## Важное — одна кнопка
Игроку нужно только нажать одну кнопку в GUI при входе в игру. После этого система автоматически строит интерфейс и визуализацию карты. Такой подход упрощает UX и уменьшает риски.

## Как это работает (в общих чертах)
1. Скрипт создаёт кнопку в GUI игрока при подключении.
2. Локальный скрипт при клике строит GUI: фреймы, адаптацию, обработчики перетаскивания, кнопку закрытия.
3. Система рендерит упрощённую топ‑даун карту, используя только доступные данные плейса (террейн, публичные детали).
4. Используются только нативные UI‑элементы Roblox — ничего не копируется и не загружается извне.

## Установка / Использование
- Поместите `src/` скрипты в соответствующие папки (StarterGui для LocalScripts и т.д.)
- Вставьте `ButtonStarter` или используйте пример из `examples/`
- Опубликуйте плейс и протестируйте: зайдите в игру и нажмите кнопку

**Monocode**: вставьте README и пример LocalScript в Monocode для быстрого просмотра кода.

## Безопасность и обфускация
- Обфускация используется только для защиты интеллектуальной собственности (уникальная логика), а не для сокрытия вредных действий.
- Скрипт не делает HTTP‑запросов, не использует эксплойты и не запрашивает личные данные.
- По запросу автор может предоставить не обфусцированную версию для модерации.

## Соответствие правилам Roblox
Скрипт разработан с соблюдением правил Roblox: нет читов, нет сторонних загрузок, всё выполняется в песочнице.

## Ограничения
- Не копирует чужие модели
- Не скачивает код извне
- Не требует внешних чит‑инструментов
- Не собирает приватные данные игроков

## FAQ
**Q: Это эксплойт?** — Нет.
**Q: Почему обфускация?** — Защита IP.
**Q: Можно применять в чужих играх?** — Нет.

## Лицензия
MIT — см. `LICENSE`.

## Связь
Открывайте issue на GitHub для запросов аудита или скриншотов.

---

> **Ready to publish:**
> - This document is formatted for GitHub README.md and is compact for Monocode snippet pages. Paste it into your repo or Monocode page directly.
