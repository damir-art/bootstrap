# Настройка
Узнайте как настраивать и расширять Bootstrap с помощью Sass, изменять глобальные параметров, системные цветов и многого другое, вплоть до создания собственных тем Bootstrap.

## Способы настройки Bootstrap
Существует несколько способов настройки Bootstrap. Ваш лучший путь может зависеть от вашего проекта, сложности ваших инструментов сборки, версии Bootstrap, которую вы используете, поддержки браузера и многого другого.

Есть два рекомендуемых метода:
- Использование Bootstrap через менеджер пакетов, чтобы вы могли использовать и расширять наши исходные файлы
- Использование скомпилированных файлов дистрибутива Bootstrap или jsDelivr (CDN), чтобы вы могли добавлять или переопределять стили Bootstrap

## Как применять?
Все работы производимые в этом разделе `customize` в основном относятся к изменению/переопределнию исходных файлов Sass или CSS переменных, например это относится к цветам.

## Разное (Customizing)
Настройка Bootstrap. Переопределение значений Bootstrap по-умолчанию.
https://www.youtube.com/watch?v=nCX3QVl_PiI&list=PL4cUxeGkcC9joIM91nLzd_qaH_AimmdAR&index=19

- можно создать свою собственную таблицу стилей
- можно переопределелить значения SASS-переменных: цвета, отступы, поля, размер шрифта и т.д.
    - через npm устанавливаем bootstrap без `--save-dev`
    - открываем SCSS файлы `_variables.scss` смотрим переменные
    - создаём собственный файл `/sass/main.scss` и переопределяем переменные Bootstrap