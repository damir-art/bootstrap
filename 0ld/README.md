# Bootstrap 5
Руководство Bootstrap 5  
Создавайте быстрые адаптивные сайты с помощью **Bootstrap**.

Сайт: https://getbootstrap.com  
Примеры макетов: https://getbootstrap.com/docs/5.3/examples/  
Примеры сеток: https://getbootstrap.com/docs/5.3/examples/grid/  
Иконки: https://icons.getbootstrap.com/  
Премиальные темы, плагины, компоненты: https://themes.getbootstrap.com/

Bootstrap - это мощный, расширяемый и многофункциональный CSS-фреймворк. Создавайте и настраивайте с помощью Sass, используйте готовую систему сеток и компоненты и воплощайте проекты в жизнь с помощью мощных плагинов JavaScript.

Начать работу можно любым удобным для вас способом: CDN, npm или загрузите исходные файлы.

Bootstrap имеет свой набор SVG иконок, более 1800 штук, иконки можно использовать даже вне Bootstrap.

## Установка Bootstrap
Качаем файлы: https://getbootstrap.com/docs/5.2/getting-started/introduction/

Вставляем шаблон:

    <!DOCTYPE html>
    <html lang="ru">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Макет для Bootstrap</title>
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.3/font/bootstrap-icons.css" />
      <link rel="stylesheet" href="bootstrap/css/bootstrap.css" />
      <link rel="stylesheet" href="style.css" />

    </head>
    <body>

      <script src="bootstrap/js/bootstrap.bundle.js"></script>
      <script src="common.js"></script>
    </body>
    </html>

## Разное
- атрибуты `aria-*` можно не добавлять, они нужны для удобства чтения с экрана и других вспомогательных вещей.
- нужен дизайн от края до края? Удалите родительский `.container` или `.container-fluid` и добавьте .`mx-0` в `.row`, чтобы предотвратить переполнение.
