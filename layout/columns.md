# Columns
Узнайте, как изменять столбцы с помощью нескольких параметров выравнивания, порядка и смещения благодаря системе сетки flexbox. Кроме того, узнайте, как использовать классы столбцов для управления шириной элементов, не являющихся элементами сетки.

## Как они работают
- **Столбцы основаны на архитектуре flexbox сетки.** Flexbox означает, что у нас есть опции для изменения отдельных столбцов и изменения групп столбцов на уровне строки. Вы выбираете, как столбцы увеличиваются, уменьшаются или иным образом изменяются.
- **При создании макетов сетки весь контент размещается в столбцах.** Иерархия сетки Bootstrap идет от контейнера к строке, столбцу и вашему контенту. В редких случаях вы можете комбинировать контент и столбец, но помните, что это может привести к непредвиденным последствиям.
- **Bootstrap включает предопределенные классы для создания быстрых и отзывчивых макетов.** С шестью точками останова и дюжиной столбцов на каждом уровне сетки у нас есть десятки классов, уже созданных для вас, чтобы вы могли создавать желаемые макеты. Это можно отключить через Sass, если хотите.

## Alignment
Используйте утилиты выравнивания flexbox для вертикального и горизонтального выравнивания столбцов.

### Vertical alignment
- `align-items-start` - прижать столбцы к верху
- `align-items-center` - прижать столбцы к середине
- `align-items-end` - прижать столбцы к низу

Измените вертикальное выравнивание с помощью любого из адаптивных классов `align-items-*`.

    <div class="container text-center">
      <div class="row align-items-start">
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
      </div>
    </div>

Изменять выравнивание можно каждого столбца по отдельности `align-self-*`:

    <div class="container text-center">
      <div class="row">
        <div class="col align-self-start">
          One of three columns
        </div>
        <div class="col align-self-center">
          One of three columns
        </div>
        <div class="col align-self-end">
          One of three columns
        </div>
      </div>
    </div>

- `align-self-start` - прижать столбец к верху
- `align-self-center` - прижать столбец к середине
- `align-self-end` - прижать столбец к низу

### Horizontal alignment
Горизонтальное выравнивание столбцов `justify-content-*`.

    <div class="container text-center">
      <div class="row justify-content-start">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-end">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-around">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-between">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-evenly">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
    </div>

- `justify-content-start` - выровнить столбцы слева
- `justify-content-center` - выровнить столбцы по центру
- `justify-content-end` - выровнить столбцы справа
- `justify-content-around` - выровнить столбцы равномерно
- `justify-content-between` - прижать столбцы по краям
- `justify-content-evenly` - выровнить столбцы равномерно

### Column wrapping
Если в одной строке размещено более 12 столбцов, каждая группа дополнительных столбцов будет как единое целое переноситься на новую строку.

    <div class="container">
      <div class="row">
        <div class="col-9">.col-9</div>
        <div class="col-4">.col-4<br>Since 9 + 4 = 13 &gt; 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.</div>
        <div class="col-6">.col-6<br>Subsequent columns continue along the new line.</div>
      </div>
    </div>

### Column breaks
Для переноса столбцов на новую строку в flexbox требуется небольшой хак: добавьте элемент с `width: 100%` везде, где вы хотите перенести столбцы на новую строку. Обычно это достигается с помощью нескольких строк `.row`, но не каждый метод реализации может это учитывать.

    <div class="container text-center">
      <div class="row">
        <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
        <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>

        <!-- Force next columns to break to new line -->
        <div class="w-100"></div>

        <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
        <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
      </div>
    </div>

Вы также можете применить этот разрыв в определенных точках останова с помощью наших утилит адаптивного отображения.

    <div class="w-100 d-none d-md-block"></div>

Разрыв появляется в точке останова md и выше.

## Reordering
Изменение порядка.

### Order classes
Используйте классы `.order-` для управления визуальным порядком вашего контента. Эти классы являются адаптивными, поэтому вы можете установить порядок по контрольной точке (например, `.order-1`, `order-md-2`). Включает поддержку от 1 до 5 на всех шести уровнях сетки. Если вам нужно больше классов `.order-*`, вы можете изменить номер по умолчанию с помощью переменной Sass.

- `.order-*` - от 1 до 5
- `.order-breakpoint-number`

Пример:

    <div class="container text-center">
      <div class="row">
        <div class="col">
          First in DOM, no order applied
        </div>
        <div class="col order-5">
          Second in DOM, with a larger order
        </div>
        <div class="col order-1">
          Third in DOM, with an order of 1
        </div>
      </div>
    </div>

Существуют также отзывчивые классы `.order-first` и `.order-last`, которые изменяют порядок элементов, применяя `order: -1` и `order: 6` соответственно. Эти классы также можно смешивать с пронумерованными классами `.order-*` по мере необходимости.

    <div class="container text-center">
      <div class="row">
        <div class="col order-last">
          First in DOM, ordered last
        </div>
        <div class="col">
          Second in DOM, unordered
        </div>
        <div class="col order-first">
          Third in DOM, ordered first
        </div>
      </div>
    </div>

### Offsetting columns
Вы можете смещать столбцы сетки двумя способами:
- Offset classes
- Margin utilities

с помощью наших адаптивных сеточных классов и `.offset-` и с помощью наших утилит для отступов `margin`. Классы сетки имеют размер, соответствующий столбцам, в то время как поля более полезны для быстрых макетов, где ширина смещения является переменной.

#### Offset classes
Переместите столбцы вправо, используя классы `.offset-md-*`. Эти классы увеличивают левое поле `margin` столбца на `*` столбцов. Например, `.offset-md-4` перемещает `.col-md-4` на четыре столбца.

    <div class="container text-center">
      <div class="row">
        <div class="col-md-4">.col-md-4</div>
        <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
      </div>
      <div class="row">
        <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
        <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
      </div>
      <div class="row">
        <div class="col-md-6 offset-md-3">.col-md-6 .offset-md-3</div>
      </div>
    </div>

В дополнение к очистке столбцов в контрольных точках реагирования вам может потребоваться сбросить смещения. Посмотрите это в действии на примере сетки.

    <div class="container text-center">
      <div class="row">
        <div class="col-sm-5 col-md-6">.col-sm-5 .col-md-6</div>
        <div class="col-sm-5 offset-sm-2 col-md-6 offset-md-0">.col-sm-5 .offset-sm-2 .col-md-6 .offset-md-0</div>
      </div>
      <div class="row">
        <div class="col-sm-6 col-md-5 col-lg-6">.col-sm-6 .col-md-5 .col-lg-6</div>
        <div class="col-sm-6 col-md-5 offset-md-2 col-lg-6 offset-lg-0">.col-sm-6 .col-md-5 .offset-md-2 .col-lg-6 .offset-lg-0</div>
      </div>
    </div>

#### Margin utilities
- `.ms-auto`
- `.ms-md-auto`
- `.me-auto`

С переходом на flexbox в версии 4 вы можете использовать `margin utilities`, такие как `.me-auto`, чтобы отделить соседние столбцы друг от друга.

    <div class="container text-center">
      <div class="row">
        <div class="col-md-4">.col-md-4</div>
        <div class="col-md-4 ms-auto">.col-md-4 .ms-auto</div>
      </div>
      <div class="row">
        <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>
        <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>
      </div>
      <div class="row">
        <div class="col-auto me-auto">.col-auto .me-auto</div>
        <div class="col-auto">.col-auto</div>
      </div>
    </div>

## Standalone column classes
Автономные классы столбцов. Классы столбцов `.col-*` также можно использовать вне `.row`, чтобы задать элементу определенную ширину. Всякий раз, когда классы столбцов используются в качестве непрямых дочерних элементов строки, отступы опускаются.

    <div class="col-3 p-3 mb-2">
      .col-3: width of 25%
    </div>

    <div class="col-sm-9 p-3">
      .col-sm-9: width of 75% above sm breakpoint
    </div>

Классы можно использовать вместе с утилитами для создания адаптивных плавающих изображений. Не забудьте обернуть содержимое в оболочку `.clearfix`, чтобы очистить обтекание, если текст короче.

    <div class="clearfix">
      <img src="..." class="col-md-6 float-md-end mb-3 ms-md-3" alt="...">

      <p>
        A paragraph of placeholder text. We're using it here to show the use of the clearfix class. We're adding quite a few meaningless phrases here to demonstrate how the columns interact here with the floated image.
      </p>

      <p>
        As you can see the paragraphs gracefully wrap around the floated image. Now imagine how this would look with some actual content in here, rather than just this boring placeholder text that goes on and on, but actually conveys no tangible information at. It simply takes up space and should not really be read.
      </p>

      <p>
        And yet, here you are, still persevering in reading this placeholder text, hoping for some more insights, or some hidden easter egg of content. A joke, perhaps. Unfortunately, there's none of that here.
      </p>
    </div>
