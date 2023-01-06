# Options
https://getbootstrap.com/docs/5.3/customize/options/

Настраивайте Bootstrap с помощью встроенных переменных, чтобы переопределять глобальные настройки CSS для управления стилем и поведением.

Настройте Bootstrap с помощью встроенного файла пользовательских переменных и переключайте глобальные настройки CSS с помощью новых переменных `$enable-*` Sass. Переопределите значение переменной и при необходимости перекомпилируйте с помощью `npm run test`.

Вы можете найти и настроить эти переменные для ключевых глобальных параметров в файле Bootstrap `scss/_variables.scss`

- `$spacer` - 1rem (default), or any value > 0 - *Указывает значение разделителя по умолчанию для программного создания наших утилит разделителя*
- `$enable-dark-mode` - true (default) or false - *Включает встроенную поддержку темного режима в проекте и его компонентах*
- `$enable-rounded` - true (default) or false - *Включает предопределенные стили `border-radius` для различных компонентов*
- `$enable-shadows` - true or false (default) - *Включает предопределенные стили для декоративной `box-shadow` различных компонентов. Не влияет на `box-shadow`, используемый для состояний фокуса*
- `$enable-gradients` - true or false (default) - *Включает предопределенные градиенты с помощью стилей `background-image` для различных компонентов*
- `$enable-transitions` - true (default) or false - *Включает предопределенные `transitions` для различных компонентов*
- `$enable-reduced-motion` - true (default) or false - *Включает медиа-запрос с `prefers-reduced-motion`, который подавляет определенные анимации/переходы в зависимости от предпочтений браузера/операционной системы пользователя*
- `$enable-grid-classes` - true (default) or false - *Позволяет генерировать классы CSS для системы сетки (например, `.row`, `.col-md-1` и т. д.)*
- `$enable-container-classes` - true (default) or false - *Позволяет создавать классы CSS для контейнеров макета. (Новое в версии 5.2.0)*
- `$enable-caret` - true (default) or false - *Включает каретку псевдоэлемента на `.dropdown-toggle`*
- `$enable-button-pointers` - true (default) or false - *Добавить курсор "hand" к non-disabled элементам кнопки*
- `$enable-rfs` - true (default) or false - *Глобально включает RFS*
- `$enable-validation-icons` - true (default) or false - *Включает иконки `background-image` в текстовом вводе и некоторых пользовательских формах для состояний проверки*
- `$enable-negative-margins` - true or false (default) - *Позволяет генерировать отрицательный `margin` в utilities Bootstrap*
- `$enable-deprecation-messages` - true (default) or false - *Установите значение `false`, чтобы скрыть предупреждения при использовании любых устаревших миксинов и функций, которые планируется удалить в `v6`*
- `$enable-important-utilities` - true (default) or false - *Включает суффикс `!important` в служебных классах (utility)*
- `$enable-smooth-scroll` - true (default) or false - *Применяет поведение прокрутки: гладкое `(scroll-behavior: smooth)` глобально, за исключением пользователей, запрашивающих уменьшение движения с помощью медиа-запроса `prefers-reduced-motion`*
