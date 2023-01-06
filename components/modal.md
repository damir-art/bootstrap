# Modal

Код вызова модального окна:

    <button class="btn btn-primary"
        data-bs-toggle="modal"
        data-bs-target="#reg-modal">
        Модальное окно
    </button>

Модальное окно:

    <!-- modal itself -->
    <div id="reg-modal" class="modal fade" tabindex="-1">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 id="modal-title" class="modal-title">Заголовок модального окна</h5>
                    <button class="btn-close"
                        data-bs-dismiss="modal"
                        type="button"></button>
                </div>
                <div class="modal-body">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Repudiandae sit, ut architecto possimus est autem reiciendis esse error, neque quasi deleniti nisi assumenda blanditiis.</p>
                    <label class="form-label" for="modal-email">Ваш емаил адрес:</label>
                    <input id="modal-email" type="email" class="form-control" placeholder="mail@mail.ru" />
                </div>
                <div class="modal-footer">
                    <button class="btn btn-primary">Отправить</button>
                </div>
            </div>
        </div>
    </div>
