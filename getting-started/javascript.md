# JavaScript (bootstrap.js)
Оживите сайты на Bootstrap с помощью наших плагинов JavaScript. Узнайте о каждом подключаемом модуле, данных и параметрах нашего API и многом другом.

## Индивидуальные или скомпилированные
Плагины можно включать по отдельности *(используя отдельные `js/dist/*.js` Bootstrap)* или все сразу, используя `bootstrap.js` или минимизированный `bootstrap.min.js`.

Если вы используете упаковщик (Webpack, Parcel, Vite и т.п.), вы можете использовать файлы `/js/dist/*.js`, которые готовы к UMD.

## Использование с фреймворками JavaScript
В то время как Bootstrap CSS `bootstrap.css` можно использовать с любым фреймворком, Bootstrap JavaScript `bootstrap.js` не полностью совместим с фреймворками JavaScript, такими как React, Vue и Angular, которые предполагают полный контроль над DOM. И Bootstrap, и фреймворк могут попытаться видоизменить один и тот же элемент DOM, что может привести к ошибкам, таким как например выпадающие списки, "зависшие" в открытом положении.

Лучшей альтернативой для тех, кто использует фреймворки, является использование пакета для конкретного фреймворка вместо Bootstrap JavaScript `bootstrap.js`.

Вот некоторые из самых популярных вариантов:
- React: React Bootstrap
- Vue: BootstrapVue (в настоящее время поддерживает только Vue 2 и Bootstrap 4)
- Angular: ng-bootstrap

## data-атрибуты
Почти все плагины Bootstrap можно включать и настраивать через data-атрибуты. Обязательно используйте только один набор атрибутов данных для одного элемента (например, вы не можете вызвать всплывающую подсказку и модальное окно с одной и той же кнопки).

Поскольку параметры можно передавать через data-атрибуты или JavaScript, вы можете добавить имя параметра к `data-bs-`, например, `data-bs-animation="{value}"`. При задании имени data-атрибуту используйте "kebab-case" вместо "camelCase".

Начиная с Bootstrap 5.2.0, все компоненты поддерживают экспериментальный зарезервированный атрибут данных data-bs-config, который может содержать простую конфигурацию компонента в виде строки JSON. Когда элемент имеет атрибуты `data-bs-config='{"delay":0, "title":123}'` и `data-bs-title="456"`, окончательное значение заголовка будет `456`, отдельные data-атрибуты переопределяют значения, указанные в `data-bs-config`. Кроме того, существующие data-атрибуты могут содержать значения JSON, например `data-bs-delay='{"show":0, "hide":150}'`.

## jQuery
Вам не нужен jQuery в Bootstrap 5, но все же можно использовать наши компоненты с jQuery. Если Bootstrap обнаружит jQuery в коде страницы, он добавит все наши компоненты в систему плагинов jQuery.

    $('#myTooltip').tooltip('show')

### jQuery события
Bootstrap обнаружит jQuery, если jQuery присутствует в объекте `window`, а `body` не установлен атрибут `data-bs-no-jquery`. Если jQuery найден, Bootstrap будет генерировать события jQuery. Поэтому, если вы хотите прослушивать события Bootstrap, вам придется использовать методы jQuery `(.on, .one)` вместо `addEventListener`.

    $('#myTab a').on('shown.bs.tab', () => {
      // do something...
    })
