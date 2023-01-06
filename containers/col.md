# Col
Bootstrap исполльзует сетку из 12 колонок `col`.

Все 4 колонки займут одинаковое пространство по 3 ячейки:

    <div class="container">
        <h1>Заголовок</h1>
        <div class="row">
            <div class="col">
                <div class="py-2 bg-primary text-light">1</div>
            </div>
            <div class="col">
                <div class="py-2 bg-primary text-light">2</div>
            </div>
            <div class="col">
                <div class="py-2 bg-primary text-light">3</div>
            </div>
            <div class="col">
                <div class="py-2 bg-primary text-light">4</div>
            </div>
        </div>
    </div>

Первая колонка займет 4 ячейки, вторая 8:

        <div class="col-4">1</div>
        <div class="col-8">2</div>

При ширине экрана больше 992px `lg` колонки будут занимать по 3 ячейки, при ширине экрана от 768px до 992px `md` колонки будут занимать по 6 ячеек, если не установить количесвто колонок для ширины меньше 768px `sm`, `col-число`, то колонки будут занимать 100%:

    <div class="col-md-6 col-lg-3">
        <div class="py-2 bg-primary text-light">1</div>
    </div>
    <div class="col-md-6 col-lg-3">
        <div class="py-2 bg-primary text-light">2</div>
    </div>
    <div class="col-md-6 col-lg-3">
        <div class="py-2 bg-primary text-light">3</div>
    </div>
    <div class="col-md-6 col-lg-3">
        <div class="py-2 bg-primary text-light">4</div>
    </div>

## justify-content-`value`
Работаем с `flexbox` и `justify-content` в Bootstrap. Создадим 3 столбца занимающие по 3 ячейки:

    <div class="row justify-content-between">
        <div class="col-3">
            <div class="py-2 bg-primary text-light">1</div>
        </div>
        <div class="col-3">
            <div class="py-2 bg-primary text-light">2</div>
        </div>
        <div class="col-3">
            <div class="py-2 bg-primary text-light">3</div>
        </div>
    </div>
