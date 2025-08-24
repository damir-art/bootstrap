# prefers-color-scheme

`prefers-color-scheme` — это **CSS-медиа-запрос**, который браузер подсовывает вёрстке в зависимости от того, какую тему выбрал пользователь в системе (светлую или тёмную).

То есть: если у человека на Windows, macOS, Android или iOS включён **dark mode**, браузер скажет сайту: «я предпочитаю тёмную схему». Если светлый — соответственно наоборот.

### Синтаксис

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #121212;
    color: #e0e0e0;
  }
}

@media (prefers-color-scheme: light) {
  body {
    background: #ffffff;
    color: #212121;
  }
}
```

### Значения

* `light` → у пользователя включена светлая тема.
* `dark` → тёмная тема.
* `no-preference` → если система не сообщает предпочтение.

### Как это связано с Bootstrap

В Bootstrap 5.3 сделали очень удобно: можно вешать тему на `<html data-bs-theme="...">`.
Чтобы это автоматически подстраивалось под системную тему, можно сделать так:

```css
@media (prefers-color-scheme: dark) {
  :root {
    color-scheme: dark;
  }
  html {
    --bs-body-bg: #121212;
    --bs-body-color: #e0e0e0;
    --bs-heading-color: #ffffff;
    --bs-link-color: #ff8a50;
    --bs-border-color: #333333;
    /* и любые другие --bs-* */
    /* или просто: */
    /* html { data-bs-theme: dark } через JS */
  }
}
```

А ещё есть фича: свойство `color-scheme`. Если написать `color-scheme: light dark;`, то даже **браузерные элементы** (скроллбар, инпуты, дата-пикеры) подстроятся.

---

Хочешь, я покажу рабочий пример с Bootstrap, где тема автоматически переключается в зависимости от системной настройки, но при этом можно кнопкой вручную переопределить?
