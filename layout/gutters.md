# Gutters
- `row g-0` - убираем padding у колонок
- `row g-4` - добавляем паддинг колонкам со все сторон, например снизу когда на маленьких экранах нам нужен зазор между колонками выстроенными сверху вниз
- `row row-cols-2 row-cols-lg-5 g-2 g-lg-3` - у брекпоинта lg в строке будет 5 столбцов с шириной зазора 3

Числа от 0 до 5, размеры от 0 до 3 rem, у сеток 1.5 rem.  
0, .25, .5, $spacer, 1.5, 3,

Переменная Sass `$spacers` по-умолчанию равна 1 rem.

**Gutters** (промежутки, желоба, зазоры) - это отступы между вашими столбцами, используемые для гибкого размещения и выравнивания содержимого в сеточной системе Bootstrap.

## Как они работают
- Желоба - это промежутки между содержимым столбцов, созданные горизонтальным заполнением. Мы устанавливаем `padding-right` и `padding-left` для каждого столбца и используем отрицательное поле, чтобы сместить его в начале и конце каждой строки `.row`, чтобы выровнять содержимое.
- Желоба начинаются с ширины 1,5 rem (24 пикселя). Это позволяет нам сопоставить нашу сетку с масштабом отступов и полей.
- Желоба можно гибко регулировать. Используйте классы желобов для конкретных точек останова, чтобы изменить горизонтальные желоба, вертикальные желоба и все желоба.

## Horizontal gutters
Классы `.gx-*` можно использовать для управления шириной горизонтального поля. Родительский элемент `.container` или `.container-fluid`, возможно, потребуется скорректировать, если также используются более крупные желоба, чтобы избежать нежелательного переполнения, используя соответствующую утилиту заполнения. Например, в следующем примере мы увеличили отступ с помощью `.px-4`:

    <div class="container px-4 text-center">
      <div class="row gx-5">
        <div class="col">
        <div class="p-3">Custom column padding</div>
        </div>
        <div class="col">
          <div class="p-3">Custom column padding</div>
        </div>
      </div>
    </div>

Альтернативное решение - добавить оболочку вокруг `.row` с классом `.overflow-hidden`:

## Vertical gutters
Классы `.gy-*` можно использовать для управления шириной вертикального поля внутри строки, когда столбцы переносятся на новые строки. Как и горизонтальные промежутки, вертикальные промежутки могут вызвать переполнение ниже `.row` в конце страницы. Если это происходит, вы добавляете оболочку вокруг `.row` с классом `.overflow-hidden`:

    <div class="container overflow-hidden text-center">
      <div class="row gy-5">
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
      </div>
    </div>

## Horizontal & vertical gutters
Классы `.g-*` можно использовать для управления горизонтальной шириной желоба, в следующем примере мы используем меньшую ширину желоба, поэтому нет необходимости добавлять класс-оболочку `.overflow-hidden`.

    <div class="container text-center">
      <div class="row g-2">
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div>
      </div>
    </div>

## Row columns gutters
Классы Gutter также можно добавлять в столбцы строк. В следующем примере мы используем адаптивные столбцы строк и адаптивные классы промежутков.

    <div class="container text-center">
      <div class="row row-cols-2 row-cols-lg-5 g-2 g-lg-3">
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
        <div class="col">
          <div class="p-3">Row column</div>
        </div>
      </div>
    </div>

## No gutters
Промежутки между столбцами в наших предопределенных классах сетки можно удалить с помощью `.g-0`. Это удаляет отрицательные `margin` из `.row` и горизонтальное заполнение `padding` из всех непосредственных дочерних столбцов `.col`.

Нужен дизайн от края до края? Удалите родительский `.container` или `.container-fluid` и добавьте .`mx-0` в `.row`, чтобы предотвратить переполнение.

На практике вот как это выглядит. Обратите внимание, что вы можете продолжать использовать это со всеми другими предопределенными классами сетки (включая ширину столбцов, адаптивные уровни, изменение порядка и т. д.).

    <div class="row g-0 text-center">
      <div class="col-sm-6 col-md-8">.col-sm-6 .col-md-8</div>
      <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    </div>


## Change the gutters
Классы строятся из карты `$gutters` Sass, которая унаследована от карты `$spacers` Sass.

    $grid-gutter-width: 1.5rem;
    $gutters: (
      0: 0,
      1: $spacer * .25,
      2: $spacer * .5,
      3: $spacer,
      4: $spacer * 1.5,
      5: $spacer * 3,
    );
