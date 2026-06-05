# Claude Code Skills

Установленные скиллы в `~/.claude/skills/` — **4 штуки**. Все про создание сайтов и интерфейсов (+ разработку через спецификации).

> 🎯 Быстрый ответ «что брать» — внизу, в разделе [Какой скилл для какой задачи](#-какой-скилл-для-какой-задачи).

---

## 1. Emil Design Engineering
**Путь:** `~/.claude/skills/emil-design-eng/`
**GitHub:** https://github.com/emilkowalski/skill.git
**Имя скилла:** `design-taste-frontend` (внутри `skills/emil-design-eng/SKILL.md`)

Философия UI-полировки от Emil Kowalski. Фокус на анимациях, деталях и ощущении интерфейса.

### Ключевые принципы:
- Анимации только с четкой целью (иерархия, сторителлинг, фидбек, переход состояний)
- Только `transform` и `opacity` — GPU-ускорение
- Кастомные easing-кривые вместо стандартных CSS
- Spring-анимации для drag и живых элементов
- `ease-out` для входа, `ease-in-out` для движения на экране
- Никогда не анимировать `scale(0)` — начинать от `scale(0.95) + opacity:0`
- Popovers масштабируются из триггера (`transform-origin`)
- Tooltips: задержка на первом, мгновенно на последующих
- CSS transitions вместо keyframes для прерываемых UI
- `@starting-style` для входа без JS

---

## 2. Impeccable
**Путь:** `~/.claude/skills/impeccable/`
**GitHub:** https://github.com/pbakaus/impeccable.git
**Имя скилла:** `impeccable` (`.claude/skills/impeccable/SKILL.md`)

Фреймворк для production-grade frontend интерфейсов. 23 команды под `/impeccable`.

### Команды:
| Группа | Команды |
|--------|---------|
| Build | `craft`, `shape`, `init`, `document`, `extract` |
| Evaluate | `critique`, `audit` |
| Refine | `polish`, `bolder`, `quieter`, `distill`, `harden`, `onboard` |
| Enhance | `animate`, `colorize`, `typeset`, `layout`, `delight`, `overdrive` |
| Fix | `clarify`, `adapt`, `optimize` |
| Iterate | `live` |

### Ключевые правила:
- Два регистра: **brand** (лендинг, портфолио) и **product** (дашборды, инструменты)
- Запрещены: gradient text, glassmorphism как дефолт, hero-metric шаблон, одинаковые карточки-сетки, eyebrow над каждой секцией
- OKLCH для цвета
- Проверка контраста WCAG AA обязательна
- Тело текста: `--color-ink` (10% lightness), не `--color-charcoal`

---

## 3. Taste Skill (коллекция)
**Путь:** `~/.claude/skills/taste-skill/`
**GitHub:** https://github.com/Leonxlnx/taste-skill.git

Коллекция из 12 скиллов. Основной: `skills/taste-skill/SKILL.md`

### Все скиллы в коллекции:
- `taste-skill` — основной анти-слоп фронтенд скилл
- `minimalist-skill` — минимализм
- `brutalist-skill` — брутализм
- `soft-skill` — мягкий стиль
- `redesign-skill` — редизайн
- `brandkit` — бренд-кит
- `image-to-code-skill` — картинка в код
- `imagegen-frontend-web` — генерация web UI
- `imagegen-frontend-mobile` — генерация mobile UI
- `stitch-skill` — вспомогательный
- `output-skill` — вспомогательный
- `taste-skill-v1` — v1

### Ключевые правила taste-skill:
- **3 дайала:** `DESIGN_VARIANCE` (1-10), `MOTION_INTENSITY` (1-10), `VISUAL_DENSITY` (1-10). Базовые: 8/6/4
- Читать бриф перед генерацией — объявлять "Design Read" одной строкой
- Запрещены: AI-purple градиенты, Inter как дефолт, Fraunces/Instrument_Serif, кремовый фон (#f5f1ea и семья), em-dash (—) везде и всегда
- Запрещены: 3 одинаковые карточки, div-based fake screenshots, fake числа
- Serif только если бренд явно требует
- `min-h-[100dvh]` вместо `h-screen`
- Герой: макс 2 строки заголовка, макс 20 слов подтекста, макс 4 элемента
- Pre-flight чеклист из ~60 пунктов перед сдачей

---

## 4. Spec Kit
**Путь:** `~/.claude/skills/spec-kit/`
**GitHub:** https://github.com/github/spec-kit.git
**Тип:** toolkit от GitHub (не `SKILL.md`, а набор slash-команд + CLI `specify`)

**Spec-Driven Development** — разработка через спецификации. Сначала описываешь, *что* должно получиться (спецификация), а агент генерирует рабочий код из неё. Для крупных проектов, где важна предсказуемость, а не «vibe coding с нуля».

### Команды (slash):
| Команда | Что делает |
|---------|-----------|
| `/speckit.constitution` | задать принципы проекта (качество, тесты, UX, производительность) |
| `/speckit.specify` | описать, ЧТО строим (сценарии, без технических деталей) |
| `/speckit.plan` | технический план реализации |
| `/speckit.tasks` | разбить план на конкретные задачи |
| `/speckit.implement` | сгенерировать код по задачам |

### CLI:
```bash
# установка (нужен uv)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
# новый проект
specify init my-project
```

---

## 🎯 Какой скилл для какой задачи

| Задача | Что брать |
|--------|-----------|
| Сделать лендинг / сайт-визитку для бренда | `taste-skill` (задать стиль) → затем `impeccable` (довести до продакшена) |
| Выбрать визуальный стиль | `taste-skill`: `minimalist` / `brutalist` / `soft` |
| Собрать бренд-кит (цвета, шрифты, лого) | `taste-skill` → `brandkit` |
| Живые анимации, отполировать «ощущение» интерфейса | `emil-design-eng` |
| Превратить скриншот / картинку в рабочий код | `taste-skill` → `image-to-code-skill` |
| Сгенерировать макет под мобильный экран | `taste-skill` → `imagegen-frontend-mobile` |
| Проверить/раскритиковать готовый дизайн | `/impeccable audit`, `/impeccable critique` |
| Финальная полировка перед публикацией | `/impeccable polish`, `/impeccable harden` |
| Сделать дизайн смелее / тише | `/impeccable bolder` · `/impeccable quieter` |
| Большой проект с нуля (приложение, сервис) | `spec-kit`: сначала спецификация, потом код |

---

## 🧰 Встроенные скиллы Claude (документы и контент)

Эти возможности **встроены** — устанавливать ничего не нужно. Claude подключает их сам, когда просишь сделать соответствующий файл.

| Скилл | Что делает | Пример под твою работу |
|-------|-----------|------------------------|
| 📄 **docx** | документы Word | бриф на съёмку, медиакит, сценарий в текстовом виде |
| 📊 **xlsx** | таблицы Excel / CSV | контент-план, календарь публикаций, учёт статистики Reels |
| 🖼️ **pptx** | презентации | медиакит и питч-деки для брендов и рекламодателей |
| 📑 **pdf** | работа с PDF | читать/объединять договоры и брендбуки, собрать гайд-лид-магнит для подписчиков |

**Как пользоваться:** просто попроси Claude словами — например, «сделай контент-план на месяц в Excel» или «собери медиакит в виде презентации». Готовый файл можно сохранить хоть в папку `ресурсы` твоей базы.

---

## Как использовать

Скиллы подключены к Claude Code и **активируются автоматически** при запросах на дизайн/UI/разработку — отдельно вызывать не обязательно.

Ручной вызов (если нужно конкретное действие):
- `/impeccable craft [фича]` — создать фичу
- `/impeccable audit` — аудит качества
- `/impeccable polish` — финальная полировка
- `/speckit.specify [описание]` — начать проект со спецификации
