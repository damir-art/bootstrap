# Темизация Bootstrap
Коротко: `--bs-*` — это CSS-переменные Bootstrap 5+, которые управляют:
- цветами,
- типографикой,
- отступами,
- внешним видом компонентов и т.д.

Их можно переопределять глобально, по теме (`[data-bs-theme]`) или локально на компоненте — без пересборки Sass.

### Мини-демо: светлая/тёмная тема на лету

Скопируй этот файл и открой в браузере — кнопка переключает тему через `data-bs-theme`, а всё держится на `--bs-*`.

```html
<!doctype html>
<html lang="ru" data-bs-theme="light">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bootstrap --bs-* demo</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    /* Глобальные значения по умолчанию */
    :root {
      --bs-font-sans-serif: ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
      --bs-primary: #6750a4;
      --bs-body-bg: #ffffff;
      --bs-body-color: #212529;
      --bs-border-color: #dee2e6;
      --bs-border-radius: .75rem;
      --bs-link-color: var(--bs-primary);
    }

    /* Переопределения для тёмной темы */
    [data-bs-theme="dark"] {
      --bs-body-bg: #0b0f17;
      --bs-body-color: #e2e8f0;
      --bs-primary: #8ab4f8;
      --bs-border-color: #2b3340;
      --bs-link-color: #9ec3ff;
      --bs-heading-color: #f1f5f9;
      --bs-code-color: #ffd580;
    }

    /* Локальная темизация компонента Card через его переменные */
    .card.custom {
      --bs-card-bg: var(--bs-body-bg);
      --bs-card-color: var(--bs-body-color);
      --bs-card-border-color: var(--bs-border-color);
      --bs-card-cap-bg: color-mix(in oklab, var(--bs-primary) 12%, transparent);
    }

    /* Кастомная кнопка на переменных кнопок */
    .btn-brand {
      --bs-btn-font-weight: 600;
      --bs-btn-bg: var(--bs-primary);
      --bs-btn-border-color: var(--bs-primary);
      --bs-btn-hover-bg: color-mix(in oklab, var(--bs-primary) 85%, black);
      --bs-btn-hover-border-color: color-mix(in oklab, var(--bs-primary) 85%, black);
      --bs-btn-active-bg: color-mix(in oklab, var(--bs-primary) 75%, black);
      --bs-btn-active-border-color: color-mix(in oklab, var(--bs-primary) 75%, black);
      --bs-btn-color: #fff;
      --bs-btn-hover-color: #fff;
    }
  </style>
</head>
<body class="p-4">
  <div class="d-flex gap-2 mb-4">
    <button id="toggleTheme" class="btn btn-outline-primary">Сменить тему</button>
    <button class="btn btn-brand">Brand кнопка</button>
  </div>

  <div class="card custom mb-3">
    <div class="card-header">Карточка на --bs-card-*</div>
    <div class="card-body">
      <h5 class="card-title">Заголовок</h5>
      <p class="card-text">
        Это текст, который автоматически подстраивается под тему.
        Ссылка выглядит как <a href="#">--bs-link-color</a>,
        а код — <code>--bs-code-color</code>.
      </p>
    </div>
  </div>

  <div class="alert alert-primary" role="alert">
    Это alert. Его фон, бордер и текст тоже сидят на переменных alert’а.
  </div>

  <script>
    const root = document.documentElement;
    const btn = document.getElementById('toggleTheme');
    btn.addEventListener('click', () => {
      const next = root.getAttribute('data-bs-theme') === 'dark' ? 'light' : 'dark';
      root.setAttribute('data-bs-theme', next);
    });
  </script>
</body>
</html>
```

### Где и какие переменные есть

Глобальные (ядро):

* `--bs-body-bg`, `--bs-body-color`, `--bs-body-font-family` (или `--bs-font-sans-serif`),
* `--bs-primary`, `--bs-secondary`, `--bs-success`, `--bs-info`, `--bs-warning`, `--bs-danger`, `--bs-light`, `--bs-dark`,
* `--bs-border-color`, `--bs-border-width`, `--bs-border-radius`,
* `--bs-link-color`, `--bs-link-hover-color`, `--bs-heading-color`, `--bs-code-color`.

Компонентные (на каждом виджете свой набор):

* Кнопки: `--bs-btn-bg`, `--bs-btn-color`, `--bs-btn-border-color`, `--bs-btn-hover-bg`, `--bs-btn-active-bg`, …
* Карточки: `--bs-card-bg`, `--bs-card-color`, `--bs-card-border-color`, `--bs-card-cap-bg`, …
* Таблицы: `--bs-table-bg`, `--bs-table-color`, `--bs-table-border-color`, `--bs-table-striped-bg`, …
* Алёрты: `--bs-alert-bg`, `--bs-alert-color`, `--bs-alert-border-color`, …
* Навбар, модалки, тултипы и т.д. тоже имеют свои `--bs-<component>-*`.

### Паттерны использования

1. **Глобально:** переопредели на `:root` или на `[data-bs-theme="…"]` для разных тем.
2. **Локально:** повесь класс на конкретный блок/компонент и меняй только его переменные.
3. **Динамически:** меняй атрибут `data-bs-theme` или конкретные `style.setProperty('--bs-primary', '#...')` из JS.

Если нужно, соберу тебе таблицу часто используемых `--bs-*` именно для твоих компонентов и цветов, или добавлю переключение системной темы по `prefers-color-scheme`.

---

# Темизация в Бутстрап - это переопределение --bs- переменных
В Bootstrap 5 и новее темизация держится на **CSS custom properties** (`--bs-*`). Это главный механизм, позволяющий менять внешний вид без пересборки Sass.

Но тут есть два слоя:

1. **Глобальные переменные ядра**
   Они определяют базовые вещи: цветовую палитру (`--bs-primary`, `--bs-success`, `--bs-body-bg`, `--bs-body-color`), типографику (`--bs-font-sans-serif`, `--bs-body-font-size`), бордеры, радиусы и т. д.
   — Если их переопределить на `:root` или `[data-bs-theme="dark"]`, все компоненты автоматически перестроятся.

2. **Компонентные переменные**
   Каждый компонент (кнопки, карточки, таблицы, алёрты) имеет свой набор `--bs-<component>-*`.
   — Например, кнопка `btn-primary` тянет `--bs-btn-bg`, `--bs-btn-border-color`, `--bs-btn-hover-bg`.
   — Карточка использует `--bs-card-bg`, `--bs-card-color`, `--bs-card-border-color`.
   Их можно менять отдельно для конкретного блока, не трогая глобальные цвета.

3. **Sass-переменные (более глубокий уровень)**
   По сути, всё наследуется из Sass. Если нужен **полный контроль** и своя палитра с новыми токенами — проще пересобрать Bootstrap через Sass, а не только на `--bs-*`.
   Но для живого переключения тем (например, светлая/тёмная) используют именно `--bs-*`.

То есть:

* **Быстрая темизация и динамическая смена темы → `--bs-*`.**
* **Глубокая кастомизация и создание своей сборки → Sass-переменные.**

Хочешь, я соберу для тебя список «ядра» самых важных `--bs-*`, которые реально чаще всего переопределяют при темизации?

---

Да! Это будет как карта «главных рычагов управления» Bootstrap.

### Самые важные `--bs-*` для темизации

**Цвета палитры**

* `--bs-primary`, `--bs-secondary`, `--bs-success`, `--bs-info`, `--bs-warning`, `--bs-danger`, `--bs-light`, `--bs-dark`
  → основная палитра бренда. Их меняешь — и весь Bootstrap перекрашивается.

**Фон и текст**

* `--bs-body-bg` → фон страницы.
* `--bs-body-color` → основной цвет текста.
* `--bs-heading-color` → заголовки.
* `--bs-link-color` и `--bs-link-hover-color` → ссылки.
* `--bs-code-color` → цвет `<code>`.

**Типографика**

* `--bs-font-sans-serif` → шрифт по умолчанию.
* `--bs-body-font-family` → базовый шрифт текста.
* `--bs-body-font-size` → размер текста.
* `--bs-body-line-height` → межстрочный интервал.

**Бордеры и радиусы**

* `--bs-border-color` → цвет границ.
* `--bs-border-radius` → общий радиус скругления.
* `--bs-border-radius-sm`, `--bs-border-radius-lg`, `--bs-border-radius-xl`, `--bs-border-radius-xxl` → размеры скруглений.

**Компонентные токены (часто трогают)**

* `--bs-btn-bg`, `--bs-btn-color`, `--bs-btn-hover-bg` → кнопки.
* `--bs-card-bg`, `--bs-card-color`, `--bs-card-border-color` → карточки.
* `--bs-alert-bg`, `--bs-alert-color` → алёрты.
* `--bs-table-bg`, `--bs-table-color` → таблицы.

---

Если переопределить вот эти переменные, уже получается **полностью свой стиль**: фирменные цвета, шрифты, фон, ссылки, кнопки и карточки.

Хочешь, я соберу для тебя пример «базового override», где одной секцией CSS на `:root` меняются только эти ключевые `--bs-*`, и весь Bootstrap сразу становится брендированным?

---

