# Sass
Используйте наши исходные файлы Sass, чтобы воспользоваться преимуществами переменных, карт, миксинов и функций, которые помогут вам быстрее создавать и настраивать свой проект.

## Файловая структура
По возможности избегайте изменения основных файлов Bootstrap. Для Sass это означает создание собственной таблицы стилей, которая импортирует Bootstrap, чтобы вы могли изменять и расширять ее. Предполагая, что вы используете менеджер пакетов, такой как npm, у вас будет такая файловая структура:

    project/
      scss/
        custom.scss
      node_modules/
        bootstrap/
            js/
            scss/

Если вы загрузили наши исходные файлы и не используете менеджер пакетов, вы можете вручную создать что-то похожее на эту структуру, сохраняя исходные файлы Bootstrap отдельно от ваших собственных.

    project/
      scss/
        custom.scss
      bootstrap/
        js/
        scss/

## Импорт
В `custom.scss` вы импортируете исходные файлы Bootstrap Sass. У вас есть два варианта: включить весь Bootstrap или выбрать нужные вам части. Мы рекомендуем последнее, хотя имейте в виду, что существуют некоторые требования и зависимости между нашими компонентами. Вам также потребуется включить JavaScript для наших плагинов.

Пример №1

  // custom.scss
  // Вариант A: включить весь Bootstrap
  // Включите здесь любые переопределения переменных по умолчанию (хотя функции будут недоступны)

  @import "../node_modules/bootstrap/scss/bootstrap";

  // Затем добавьте сюда дополнительный пользовательский код

Пример №2

    // Custom.scss
    // Вариант Б: включить части Bootstrap

    // 1. Сначала подключите функции (чтобы вы могли манипулировать цветами, SVG, расчетами и т. д.)
    @import "../node_modules/bootstrap/scss/functions";

    // 2. Включите здесь любые переопределения переменных по умолчанию

    // 3. Включите остальные требуемые таблицы стилей Bootstrap (включая любые отдельные таблицы стилей цветового режима)
    @import "../node_modules/bootstrap/scss/variables";
    @import "../node_modules/bootstrap/scss/variables-dark";

    // 4. Включите сюда любые переопределения карты по умолчанию

    // 5. Включить остальные необходимые части
    @import "../node_modules/bootstrap/scss/maps";
    @import "../node_modules/bootstrap/scss/mixins";
    @import "../node_modules/bootstrap/scss/root";

    // 6. При необходимости включите любые другие части
    @import "../node_modules/bootstrap/scss/utilities";
    @import "../node_modules/bootstrap/scss/reboot";
    @import "../node_modules/bootstrap/scss/type";
    @import "../node_modules/bootstrap/scss/images";
    @import "../node_modules/bootstrap/scss/containers";
    @import "../node_modules/bootstrap/scss/grid";
    @import "../node_modules/bootstrap/scss/helpers";

    // 7. При необходимости включайте утилиты API последними, чтобы генерировать классы на основе карты Sass в _utilities.scss
    @import "../node_modules/bootstrap/scss/utilities/api";

    // 8. Добавьте сюда дополнительный пользовательский код

С этой настройкой вы можете начать изменять любые переменные и карты Sass в вашем файле `custom.scss`. Вы также можете начать добавлять части Bootstrap в раздел `// Option` по мере необходимости. Мы предлагаем использовать полный стек импорта из нашего файла bootstrap.scss в качестве отправной точки.

## Переменные по умолчанию
Каждая переменная Sass в Bootstrap включает флаг `!default`, позволяющий вам переопределить значение переменной по умолчанию в вашем собственном Sass без изменения исходного кода Bootstrap. Скопируйте и вставляйте переменные по мере необходимости, измените их значения и удалите флаг `!default`. Если переменная уже была назначена, она не будет переназначена значениями по умолчанию в Bootstrap.

Вы найдете полный список переменных Bootstrap в файле `scss/_variables.scss`. Некоторые переменные имеют значение `null`, эти переменные не выводят свойство, если они не переопределены в вашей конфигурации.

Переопределения переменных должны выполняться после импорта наших функций, но до остальных операций импорта.

Вот пример изменения цвета фона и цвета `body` при импорте и компиляции Bootstrap через npm:

    // Необходимый
    @import "../node_modules/bootstrap/scss/functions";

    // Переопределение переменных по умолчанию
    $body-bg: #000;
    $body-color: #111;

    // Необходимый
    @import "../node_modules/bootstrap/scss/variables";
    @import "../node_modules/bootstrap/scss/variables-dark";
    @import "../node_modules/bootstrap/scss/maps";
    @import "../node_modules/bootstrap/scss/mixins";
    @import "../node_modules/bootstrap/scss/root";

    // Необязательные компоненты Bootstrap здесь
    @import "../node_modules/bootstrap/scss/reboot";
    @import "../node_modules/bootstrap/scss/type";
    // и т.д

При необходимости, повторите для любой переменной в Bootstrap, включая глобальные параметры ниже.

## Карты и циклы
Bootstrap включает в себя несколько карт Sass, пар ключ-значение, которые упрощают создание семейств связанных CSS. Bootstrap использует карты Sass для цветов, брекпоинтов сетки и многого другого. Как и переменные Sass, все карты Sass включают флаг `!default` и могут быть переопределены и расширены.

Некоторые из карт Sass по умолчанию объединены в пустые. Это сделано для того, чтобы упростить расширение данной карты Sass, но за счет того, что удаление элементов с карты немного усложняется.

## Изменение карты
Все переменные в карте `$theme-colors` определены как автономные переменные. Чтобы изменить существующий цвет в нашей карте `$theme-colors`, добавьте в свой собственный файл Sass следующее:

    $primary: #0074d9;
    $danger: #ff4136;

Позже эти переменные устанавливаются в карте Bootstrap `$theme-colors`:

    $theme-colors: (
      "primary": $primary,
      "danger": $danger
    );

## Добавление в карту
Добавьте новые цвета в `$theme-colors` или любую другую карту, создав новую карту Sass с вашими пользовательскими значениями и объединив ее с исходной картой. В этом случае мы создадим новую карту `$custom-colors` и объединим ее с `$theme-colors`.

    // Create your own map
    $custom-colors: (
      "custom-color": #900
    );

    // Merge the maps
    $theme-colors: map-merge($theme-colors, $custom-colors);

## Удалить с карты
Чтобы удалить цвета из `$theme-colors` или любой другой карты, используйте `map-remove`. Имейте в виду, что вы должны вставить `$theme-colors` между нашими требованиями сразу после его определения в переменных и до его использования в картах:

    // Required
    @import "../node_modules/bootstrap/scss/functions";
    @import "../node_modules/bootstrap/scss/variables";
    @import "../node_modules/bootstrap/scss/variables-dark";

    $theme-colors: map-remove($theme-colors, "info", "light", "dark");

    @import "../node_modules/bootstrap/scss/maps";
    @import "../node_modules/bootstrap/scss/mixins";
    @import "../node_modules/bootstrap/scss/root";

    // Optional
    @import "../node_modules/bootstrap/scss/reboot";
    @import "../node_modules/bootstrap/scss/type";
    // etc

## Необходимые ключи
Bootstrap предполагает наличие определенных ключей в картах Sass, которые мы использовали и расширяли сами. При настройке включенных карт вы можете столкнуться с ошибками при использовании определенного ключа карты Sass.

Например, мы используем ключи `primary`, `success`, `danger` из `$theme-colors` для ссылок, кнопок и состояний форм. Замена значений этих ключей не должна вызвать проблем, но их удаление может вызвать проблемы с компиляцией Sass. В этих случаях вам нужно будет изменить код Sass, который использует эти значения.

## Functions
Наряду с картами Sass, которые у нас есть, цвета темы также можно использовать как автономные переменные, такие как `$primary`.

    .custom-element {
      color: $gray-100;
      background-color: $dark;
    }

Вы можете осветлить или затемнить цвета с помощью функций Bootstrap `tint-color()` и `shadow-color()`. Эти функции будут смешивать цвета с черным или белым, в отличие от собственных функций Sass `lighten()` и `darken()`, которые изменяют яркость на фиксированную величину, что часто не приводит к желаемому эффекту.

    // Осветляем цвет: смешиваем цвет с белым
    @function tint-color($color, $weight) {
      @return mix(white, $color, $weight);
    }

    // Затеняем цвет: смешиваем цвет с черным
    @function shade-color($color, $weight) {
      @return mix(black, $color, $weight);
    }

    // Затеняем цвет, если вес положительный, иначе осветляем
    @function shift-color($color, $weight) {
      @return if($weight > 0, shade-color($color, $weight), tint-color($color, -$weight));
    }

На практике вы бы вызвали функцию и передали параметры цвета и веса.

    .custom-element {
      color: tint-color($primary, 10%);
    }

    .custom-element-2 {
      color: shade-color($danger, 30%);
    }

## Цветовой контраст
Чтобы соответствовать требованиям к контрастности `Руководства по доступности веб-контента (WCAG)`, авторы должны обеспечить минимальную цветовую контрастность текста `4.5 : 1` и минимальную контрастность не текстовых цветов `3 : 1`, за очень немногими исключениями.

Чтобы помочь с этим, мы включили функцию `color-contrast()` в Bootstrap. Он использует алгоритм коэффициента контрастности WCAG для вычисления пороговых значений контрастности на основе относительной яркости в цветовом пространстве sRGB, чтобы автоматически возвращать светлый (#fff), темный (#212529) или черный (#000) контрастный цвет на основе указанного базового цвета. Эта функция особенно полезна для примесей или циклов, когда вы создаете несколько классов.

Пример, генерирация образцов цвета из карты `$theme-colors`:

    @each $color, $value in $theme-colors {
      .swatch-#{$color} {
        color: color-contrast($value);
      }
    }

Его также можно использовать для разовых нужд контраста:

    .custom-element {
      color: color-contrast(#000); // returns `color: #fff`
    }

Вы также можете указать базовый цвет с помощью наших функций карты цветов:

    .custom-element {
      color: color-contrast($dark); // returns `color: #fff`
    }

## Экранирование SVG
Мы используем функцию `escape-svg()`, чтобы экранировать символы `<`, `>` и `#` для фоновых изображений SVG. При использовании функции `escape-svg()`, URI данных необходимо заключать в кавычки.

## Функции сложения и вычитания
Мы используем функции сложения (add) и вычитания (subtract), чтобы обернуть функцию CSS `calc()`. Основная цель этих функций - избежать ошибок, когда "безразмерное" значение 0 передается в выражение `calc()`. Такие выражения, как calc(10px - 0), будут возвращать ошибку во всех браузерах, несмотря на то, что они математически правильны.

Пример, когда вычисление действителен:

    $border-radius: .25rem;
    $border-width: 1px;

    .element {
      // Output calc(.25rem - 1px) is valid
      border-radius: calc($border-radius - $border-width);
    }

    .element {
      // Output the same calc(.25rem - 1px) as above
      border-radius: subtract($border-radius, $border-width);
    }

Пример, когда вычисление недействительно:

    $border-radius: .25rem;
    $border-width: 0; // без указания px

    .element {
      // Output calc(.25rem - 0) is invalid
      border-radius: calc($border-radius - $border-width);
    }

    .element {
      // Output .25rem
      border-radius: subtract($border-radius, $border-width);
    }

## Миксины
В каталоге `scss/mixins/` есть множество миксинов, которые являются частью Bootstrap, а также могут использоваться в вашем проекте.

## Цветовые схемы
Доступен сокращенный миксин для медиа-запроса `preferences-color-scheme` с поддержкой светлых, темных и пользовательских цветовых схем. См. документацию по цветовым режимам (https://getbootstrap.com/docs/5.3/customize/color-modes/) для получения информации о миксине цветового режима.

    @mixin color-scheme($name) {
      @media (prefers-color-scheme: #{$name}) {
        @content;
      }
    }

    .custom-element {
      @include color-scheme(dark) {
        // Insert dark mode styles here
      }

      @include color-scheme(custom-named-scheme) {
        // Insert custom color scheme styles here
      }
    }
