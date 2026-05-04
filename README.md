# Marketing Wiki

Персональная база знаний по маркетингу, которую ведёт Claude Code.

Принцип: **источники → агент пишет страницы → ты задаёшь вопросы страницам**. Сырьё лежит в `sources/`, твоя структурированная wiki — в `pages/`. Когда задаёшь вопрос, агент отвечает по `pages/`, а не лезет в каждую статью заново.

---

## Быстрый старт

1. Открой эту папку как vault в Obsidian (`File → Open vault → выбрать ~/wiki-marketing/`).
2. В терминале (Ghostty или Terminal):
   ```bash
   cd ~/wiki-marketing
   claude
   ```
3. Внутри Claude Code:
   - `/ingest sources/web/моя-статья.md` — обработать новый источник
   - `/query "что я знаю про CAC?"` — задать вопрос
   - `/lint` — проверить здоровье wiki
   - `/weekly` — еженедельный обзор

---

## Как добавить материал

| Тип | Куда положить | Как |
|---|---|---|
| Веб-статья | `sources/web/` | Obsidian Web Clipper (расширение для браузера) |
| PDF | `sources/pdf/` | перетащить файл, потом `/ingest` |
| Голосовая заметка | `sources/voice/` | сначала транскрипт (whisper или Plaud), потом `/ingest` |
| Быстрая мысль | `sources/notes/` | `Имя.md` рукой или через `/ingest` |

После добавления → `claude` → `/ingest <путь>` и агент сам разнесёт по страницам.

---

## Структура папок

- `sources/` — сырьё (не редактируй после добавления)
- `pages/` — страницы, которые пишет агент:
  - `concepts/` — фреймворки (JTBD, AARRR, AIDA…)
  - `channels/` — каналы (SEO, контекст, email…)
  - `brands/` — компании
  - `people/` — эксперты и авторы
  - `campaigns/` — кейсы кампаний
  - `metrics/` — метрики (CAC, LTV…)
  - `audiences/` — персоны и сегменты
- `queries/` — сохранённые ответы на вопросы
- `index.md` — каталог всех страниц
- `log.md` — журнал действий агента

---

## Backup

Wiki — обычный git-репо. Push в приватный GitHub:
```bash
git -C ~/wiki-marketing remote add origin git@github.com:USERNAME/wiki-marketing.git
git -C ~/wiki-marketing push -u origin main
```
Дальше агент сам коммитит после каждого ingest.

---

## Что делать когда зашла, а wiki ещё не открыта в Obsidian

Открыть Obsidian → если vault не виден, `Open vault → ~/wiki-marketing`. Дальше vault помнится автоматически.

---

Все правила работы агента — в `CLAUDE.md`. Можешь править под себя.
