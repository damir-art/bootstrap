# Базовый override
Тогда вот тебе минимальный «брендовый оверрайд» — всего один блок CSS на `:root`, который перекрашивает весь Bootstrap. Скопируй в проект, и сразу увидишь эффект.

```css
:root {
  /* 🎨 Палитра */
  --bs-primary: #ff5722;        /* твой фирменный цвет */
  --bs-secondary: #607d8b;
  --bs-success: #4caf50;
  --bs-info: #2196f3;
  --bs-warning: #ffc107;
  --bs-danger: #f44336;
  --bs-light: #f5f5f5;
  --bs-dark: #212121;

  /* 🖋️ Типографика */
  --bs-font-sans-serif: 'Roboto', 'Segoe UI', system-ui, sans-serif;
  --bs-body-font-family: var(--bs-font-sans-serif);
  --bs-body-font-size: 1rem;
  --bs-body-line-height: 1.5;

  /* 📄 Фон и текст */
  --bs-body-bg: #ffffff;
  --bs-body-color: #212121;
  --bs-heading-color: #111111;
  --bs-link-color: var(--bs-primary);
  --bs-link-hover-color: color-mix(in srgb, var(--bs-primary) 80%, black);
  --bs-code-color: #e83e8c;

  /* 🔲 Бордеры и радиусы */
  --bs-border-color: #e0e0e0;
  --bs-border-radius: .75rem;
  --bs-border-radius-sm: .5rem;
  --bs-border-radius-lg: 1rem;
}
```

### Как это работает

* **Все кнопки** `btn-primary`, `btn-secondary` и т. д. автоматически возьмут новые цвета.
* **Карточки, алёрты, таблицы** перестроятся без правки их CSS — они сидят на `--bs-card-bg`, `--bs-alert-bg`, `--bs-table-bg`, а эти токены Bootstrap вычисляет от базовых переменных.
* **Шрифты и ссылки** обновятся глобально.

Для **тёмной темы** можно добавить ещё один блок:

```css
[data-bs-theme="dark"] {
  --bs-body-bg: #121212;
  --bs-body-color: #e0e0e0;
  --bs-heading-color: #ffffff;
  --bs-link-color: #ff8a50;
  --bs-border-color: #333333;
}
```

Тогда при смене атрибута `<html data-bs-theme="dark">` всё мгновенно перекрасится.

Хочешь, я сделаю готовый HTML-пример со светлой и тёмной темой, плюс кнопкой-переключателем, чтобы можно было просто открыть и кликать?
