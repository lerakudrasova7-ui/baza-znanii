# Claude Code Skills

Установленные скиллы в `~/.claude/skills/`

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

## Как использовать

Скиллы подключены к Claude Code и активируются автоматически при запросах на дизайн/UI.

Ручной вызов в Claude Code:
- `/impeccable craft [feature]` — создать фичу
- `/impeccable audit` — аудит качества
- `/impeccable polish` — финальная полировка
