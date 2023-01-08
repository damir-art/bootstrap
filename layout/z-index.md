# Z-index
Хотя z-индексы не являются частью сетки Bootstrap, они играют важную роль в том, как наши компоненты накладываются друг на друга и взаимодействуют друг с другом.

Некоторые компоненты Bootstrap используют `z-index`, свойство CSS, которое помогает управлять макетом, предоставляя третью ось для упорядочения содержимого. Мы используем шкалу z-индекса по умолчанию в Bootstrap, которая была разработана для правильной навигации по слоям, всплывающих подсказок и всплывающих окон, модальных окон и многого другого.

Эти более высокие значения начинаются с произвольного числа, высокого и достаточно определенного, чтобы в идеале избежать конфликтов. Нам нужен их стандартный набор для наших многоуровневых компонентов - всплывающие подсказки, всплывающие окна, панели навигации, раскрывающиеся списки, модальные окна - чтобы мы могли быть достаточно последовательными в поведении. Нет причин, по которым мы не могли бы использовать `100+` или `500+`.

Мы не поощряем настройку этих отдельных значений; если вы измените один, вам, вероятно, придется изменить их все.

    $zindex-dropdown:                   1000;
    $zindex-sticky:                     1020;
    $zindex-fixed:                      1030;
    $zindex-offcanvas-backdrop:         1040;
    $zindex-offcanvas:                  1045;
    $zindex-modal-backdrop:             1050;
    $zindex-modal:                      1055;
    $zindex-popover:                    1070;
    $zindex-tooltip:                    1080;
    $zindex-toast:                      1090;

Для обработки перекрывающихся границ внутри компонентов (например, кнопок и элементов ввода в группах ввода) мы используем низкие однозначные значения `z-index` `1`, `2` и `3` для состояний по умолчанию, наведения и активного состояния. При наведении/фокусе/активности мы выводим конкретный элемент на передний план с более высоким значением `z-index`, чтобы показать его границу над элементами соседнего элемента.