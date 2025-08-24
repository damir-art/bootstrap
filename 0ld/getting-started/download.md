# Загрузка Bootstrap
https://getbootstrap.com/docs/5.3/getting-started/download/

Вместо CDN, Bootstrap можно использовать загрузив его файлы.

Загрузив и распаковав архив с файлами, обычно подключают к проекту `css/bootstrap.css` и `js/bootstrap.bundle.js`.

    <!DOCTYPE html>
    <html lang="ru">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Макет для Bootstrap</title>
      <link rel="stylesheet" href="bootstrap/css/bootstrap.css" />
      <link rel="stylesheet" href="style.css" />
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.3/font/bootstrap-icons.css" />
    </head>
    <body>

      <script src="bootstrap/js/bootstrap.bundle.js"></script>
      <script src="common.js"></script>
    </body>
    </html>
