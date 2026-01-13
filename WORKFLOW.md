# WORKFLOW — як вести cybermetatheory на різних девайсах

**Версія:** 1.0
**Дата:** 2026-01-10
**Для:** Франко (wizard K)

---

## Філософія workflow

**Принцип:** Quick capture → Process → Archive
- Телефон — швидкий захват (raw data)
- Мак — обробка та структурування
- Айпад — читання та review
- Git — синхронізація між усім

---

## Девайси та їх ролі

### 📱 Телефон (iPhone)

**Для чого:**
- Quick capture (думки, фото, voice notes)
- Emergency commits (коли мака нема)
- Читання priority_queue на ходу

**Tools:**
- **Working Copy** (Git client для iOS) — best option
- **iA Writer** або **1Writer** (markdown editor)
- **Shortcuts** (автоматизація)

**Workflow:**
1. Думка/фото/ідея з'явилася → capture в Working Copy або Notes
2. Створюй файли в папці `raw/` (raw мислі, необроблене)
3. Quick commit з телефону: `quick capture YYYY-MM-DD`
4. Sync до GitHub
5. Потім на маку — process raw → artifacts

**Приклад структури raw/:**
```
raw/
├── 2026-01-10-idea-book-character.md
├── 2026-01-10-photo-hospital.jpg
├── 2026-01-10-voice-manifesto.m4a
└── 2026-01-10-quick-todo.md
```

---

### 💻 Мак (MacBook)

**Для чого:**
- Processing (raw → processed → artifacts)
- Coding та структурування
- Робота з Git (commits, pushes, PRs)
- Робота з Claude/AI асистентами

**Tools:**
- **VS Code** або **Cursor** (для coding та markdown)
- **Obsidian** (для Map of Everything, graph view)
- **Git CLI** або **GitHub Desktop**
- **Terminal** (для scripts та automation)

**Workflow:**
1. Pull latest з GitHub
2. Переглянь `raw/` — що там з телефону
3. Process:
   - Raw думка → structured MD в `artifacts/` або `lore/`
   - Raw фото → переіменувати + metadata → `assets/`
   - Raw voice → transcription → `logs/` або `artifacts/`
4. Оновлюй `meta/`:
   - Додавай ідеї в `open_questions.md`
   - Якщо urgent → додай в `priority_queue.md`
   - Якщо нова сутність → додай в `emotional_graph_v0.X.json`
5. Commit з clear message
6. Push до GitHub

**Приклад commit message:**
```
Session 2026-01-10: Processed 3 raw captures + updated book ideas

- Processed raw/2026-01-10-idea-book-character.md → lore/protagonist-sketch.md
- Added новий концепт "соборність" в open_questions.md
- Updated emotional_graph_v0.3.json (додано MR metareality concept)
```

---

### 📋 Айпад (iPad)

**Для чого:**
- Читання та review (artifacts, lore, logs)
- Annotating (коментування в Obsidian)
- Canvas work (Map of Everything)
- Легке редагування MD файлів

**Tools:**
- **Working Copy** (Git client)
- **Obsidian Mobile**
- **iA Writer** (markdown editor з iCloud sync)
- **Apple Pencil** (якщо є — для canvas та annotations)

**Workflow:**
1. Pull latest з GitHub (Working Copy)
2. Відкрий в Obsidian або iA Writer
3. Читай `priority_queue.md`, `open_questions.md`, artifacts
4. Робий нотатки (inline comments або окремі файли в `raw/`)
5. Canvas режим — працюй з Map of Everything (візуальні зв'язки)
6. Commit changes → push

---

## Git workflow (важливо!)

### Структура branch

- **main** — production, stable
- **claude/** — AI assistant sessions (auto-generated)
- **feature/** — твої фічі (feature/book-worldbuilding, feature/music-setup)

### Як працювати з branches

**На телефоні/айпаді:**
- Працюй безпосередньо в `main` якщо це quick capture
- Або створи `quick-capture` branch для raw даних

**На маку:**
- Створюй feature branches для великих змін
- Приклад: `git checkout -b feature/book-character-development`
- Працюй, commit, push
- Коли готово — merge в main

### Коли commit і push

**Commit часто:**
- Після кожного processing session
- Коли додав/змінив важливу ідею
- Після роботи з AI (Claude session)
- End of day commit (навіть якщо incomplete)

**Push регулярно:**
- Після кожного commit (якщо є інтернет)
- Мінімум 1 раз на день
- Перед виходом з мака (backup!)

### Commit message style

```
[TYPE] Short description

Longer description if needed.
- Change 1
- Change 2

Related: #issue_number (optional)
```

**Types:**
- `SESSION` — AI session з Claude/VERD
- `CAPTURE` — quick capture з телефону
- `PROCESS` — processing raw → artifacts
- `UPDATE` — оновлення existing files
- `NEW` — нові файли/структура
- `FIX` — виправлення помилок
- `ARCHIVE` — створення snapshots

**Приклади:**
```
CAPTURE: 3 raw ideas про книгу з телефону

SESSION: VERD 2026-01-10 — реорганізація meta/ + new workflow

PROCESS: Обробив raw captures → додано в open_questions

ARCHIVE: State snapshot 2026-01-10
```

---

## Синхронізація між девайсами

### Варіант 1: GitHub (рекомендований)

**Pros:**
- Version control
- Доступ з будь-якого девайса
- Backup автоматично
- Claude може допомагати через GitHub

**Cons:**
- Треба commit/push manually
- Потрібен інтернет

**Як:**
1. Телефон: capture → commit → push (Working Copy)
2. Мак: pull → process → commit → push
3. Айпад: pull → read/annotate → commit → push

### Варіант 2: iCloud (для швидкого доступу)

**Pros:**
- Автосинк між Apple пристроями
- Не треба commit/push
- Швидко

**Cons:**
- Немає version control
- Немає history
- Конфлікти якщо редагуєш одночасно

**Як:**
1. Тримай робочу копію в `~/Documents/cybermetatheory-working/` (в iCloud)
2. Працюй там на всіх девайсах
3. 1 раз на день/тиждень — sync в Git repo на маку

### Варіант 3: Hybrid (найкраще!)

**Workflow:**
1. **iCloud для raw captures** (телефон/айпад)
   - Папка `iCloud/cybermetatheory-raw/`
   - Тут швидкі нотатки, фото, ідеї

2. **Git repo для processed та artifacts** (мак)
   - Папка `~/Code/cybermetatheory/`
   - Тут обробка + commit + push

3. **Sync flow:**
   - Телефон → iCloud raw
   - Мак → забирає з iCloud, обробляє, commit в Git
   - Айпад → читає з Git (Working Copy + Obsidian)

---

## Obsidian setup (рекомендації)

### Plugins (must-have)

1. **Dataview** — таблиці, queries, динамічні списки
2. **Graph View** — візуалізація зв'язків
3. **Canvas** — Map of Everything
4. **Git** (якщо на маку) — автопуш
5. **Templater** — templates для нових файлів

### Vault location

**Мак:**
```
~/Code/cybermetatheory/
```

**Телефон/Айпад (через Working Copy):**
```
Working Copy/cybermetatheory/
```

Obsidian може відкривати vault з Working Copy!

### Як налаштувати sync

1. Clone repo в Working Copy (iOS)
2. Obsidian → Open folder as vault → обери Working Copy/cybermetatheory
3. Тепер Obsidian читає з Git
4. Після змін → Working Copy → commit → push
5. На маку pull → бачиш зміни

---

## Typical day workflow

### Ранок (телефон)

1. Прокинувся → відкрив Working Copy → pull
2. Прочитав `meta/priority_queue.md` — що urgent сьогодні
3. Quick capture якщо щось з'явилося:
   - Notes → raw/ → commit "morning capture"

### День (мак + телефон)

1. Мак: pull latest
2. Process raw captures з ранку
3. Працюєш над проєктами (книга, музика, метахата)
4. Commit після кожної значної зміни
5. Телефон: якщо щось важливе → quick capture → push

### Вечір (айпад або мак)

1. Pull latest
2. Читай artifacts, review що зроблено за день
3. Оновлюй `priority_queue.md` якщо щось resolved
4. Додавай нові seeds в `open_questions.md`
5. End of day commit:
   ```
   SESSION: 2026-01-10 daily wrap-up

   - Processed 5 raw captures
   - Updated book ideas (соборність concept)
   - Added music creation question
   ```
6. Push

---

## Automation ideas

### iOS Shortcuts (для телефону)

**Shortcut 1: Quick Capture**
- Input: text або voice
- Action: create file в Working Copy (`raw/YYYY-MM-DD-HH-MM-capture.md`)
- Commit: "quick capture YYYY-MM-DD HH:MM"
- Push

**Shortcut 2: Photo Archive**
- Input: photo
- Action: rename (`YYYY-MM-DD-HH-MM-photo.jpg`), save в `assets/`
- Commit: "photo capture"
- Push

**Shortcut 3: Check Priority Queue**
- Action: відкрити `meta/priority_queue.md` в Working Copy

### macOS Automation (Alfred/Raycast)

**Command: `cm-capture`**
- Prompt для тексту
- Створити файл `raw/YYYY-MM-DD-HH-MM-capture.md`
- Git add + commit + push

**Command: `cm-process`**
- Показати список файлів у `raw/`
- Вибрати що обробити
- Відкрити в VS Code

---

## Typical sessions з AI (Claude)

### Before session

1. Pull latest з GitHub
2. Checkout нову branch: `git checkout -b claude/session-YYYY-MM-DD-description`
3. Готуй контекст: які файли будуть потрібні

### During session

1. Claude допомагає (code, структура, processing)
2. Змінюється багато файлів
3. Claude commit автоматично (якщо через Claude Code CLI)

### After session

1. Review changes: `git diff main`
2. Якщо все окей → merge в main:
   ```bash
   git checkout main
   git merge claude/session-YYYY-MM-DD-description
   git push
   ```
3. Або залиш branch якщо хочеш продовжити пізніше

---

## Коли використовувати що

| Задача | Телефон | Мак | Айпад |
|--------|---------|-----|-------|
| Quick capture | ✅ Best | ❌ | ⚠️ Ok |
| Processing raw → artifacts | ❌ | ✅ Best | ⚠️ Ok |
| Coding (JSON, scripts) | ❌ | ✅ Only | ❌ |
| Читання artifacts | ⚠️ Ok | ✅ Good | ✅ Best |
| Priority queue review | ✅ Good | ✅ Good | ✅ Best |
| Canvas (Map of Everything) | ❌ | ✅ Good | ✅ Best |
| Git operations (complex) | ❌ | ✅ Only | ⚠️ Basic |
| AI sessions (Claude) | ❌ | ✅ Only | ❌ |

---

## Troubleshooting

### Merge conflicts

Якщо редагував один файл на 2 девайсах одночасно:

1. На маку: `git status` (побачиш конфлікт)
2. Відкрий файл, знайди `<<<<<<` і `>>>>>>` markers
3. Вибери яку версію залишити (або обидві)
4. `git add <file>` → `git commit` → `git push`

**Як уникнути:**
- Pull перед початком роботи
- Push коли закінчив
- Не редагуй одні файли одночасно

### Забув push з мака, а тепер на телефоні

1. На телефоні: `git pull` (завантажить зміни з мака якщо вони запушені)
2. Якщо не запушені — нічого не зробиш, чекай доступ до мака
3. **Правило:** завжди push перед виходом з мака!

### iCloud конфлікт з Git

Якщо Git repo в iCloud папці — можуть бути проблеми.

**Рішення:**
- Git repo тримай ПОЗА iCloud (`~/Code/`, не `~/Documents/`)
- iCloud використовуй тільки для `raw/` папки окремо
- Або вимкни iCloud sync для Git папки

---

## Best practices

### Do ✅

- **Pull перед роботою** (завжди!)
- **Commit часто** (маленькі commits краще великих)
- **Push в кінці сесії** (backup!)
- **Clear commit messages** (зрозумілі через 111 років)
- **Raw папка для quick captures** (потім обробляй)
- **Priority queue щодня** (що urgent зараз)
- **End of day review** (що зроблено, що додати)

### Don't ❌

- **Не працюй без pull** (старі дані = конфлікти)
- **Не commit все підряд** (.DS_Store, temp files)
- **Не push прямо в main якщо великі зміни** (використовуй branches)
- **Не видаляй старі файли** (версіонуй замість видалення — Rule of Mysuk)
- **Не забувай про .gitignore** (secrets, temp files)
- **Не mix raw і processed** (структура важлива!)

---

## Quick reference

### Daily routine

```bash
# Ранок
git pull
cat meta/priority_queue.md

# День
# ... work work work ...
git add .
git commit -m "SESSION: daily work 2026-01-10"
git push

# Вечір
cat meta/priority_queue.md
# update if needed
git add meta/priority_queue.md
git commit -m "UPDATE: priority queue 2026-01-10"
git push
```

### Quick commands

```bash
# Status
git status

# Pull
git pull origin main

# Add all
git add .

# Commit
git commit -m "MESSAGE"

# Push
git push

# New branch
git checkout -b feature/new-thing

# Switch branch
git checkout main

# Merge
git merge feature/new-thing

# View log
git log --oneline -10
```

---

## Tools to try (future)

**Automation:**
- **make.com** або **n8n** — automation для raw → processed
- **Zapier** — connect iPhone → GitHub
- **IFTTT** — photo → auto-upload → Git

**Mobile:**
- **Taio** (iOS) — markdown + JavaScript automation
- **Textastic** (iOS) — code editor з Git
- **iSH** (iOS) — Linux shell на iPhone (для Git CLI!)

**Mac:**
- **Hazel** — auto-organize files
- **Alfred/Raycast** — швидкі команди
- **VSCode extensions** — Git Lens, Markdown All in One

---

**Створено:** 2026-01-10
**Куратор:** VERD + Claude
**Статус:** Living document ✨

*Structure > content. Quick capture > perfection. Commit often, push always.*

💚🦋🗝️
