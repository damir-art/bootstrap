# Начинаем работу с Bootstrap
https://getbootstrap.com/docs/5.3/getting-started/introduction/

**Bootstrap** - это мощный, многофункциональный инструмент для фронт-енда. Создавайте что угодно - от прототипа до продакшена - за считанные минуты.

## Быстрый старт
Начните с подключения CSS и JavaScript, Bootstrap файлов через CDN без каких-либо шагов по сборке. Вставьте этот код в свой файл `index.html`.

    <!doctype html>
    <html lang="ru">
      <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Название страницы</title>
      </head>
      <body>
        <h1>Заголовок страницы</h1>
      </body>
    </html>

Подключите CSS и JS-файлы Bootstrap через CDN. Поместите тег `link` в `head` для CSS-файла и тег `script` перед тегом `body` для JavaScript-файла.

    <!doctype html>
    <html lang="ru">
      <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Название страницы</title>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
      </head>
      <body>
        <h1>Hello, world!</h1>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
      </body>
    </html>

`popper.js` и `bootstrap.js` можно подключить отдельно:

    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.min.js"></script>

Откройте страницу в браузере, теперь можете использовать Bootstrap в своей разработке.
