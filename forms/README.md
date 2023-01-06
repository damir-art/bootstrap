# Forms
Работа с формами в Bootstrap: https://getbootstrap.com/docs/5.2/forms/overview/  
Частоиспользуемые классы: form-control, form-label, form-select, input-group, input-group-text, form-floating.

    <form action="#">
        <label class="form-label" for="email">Email:</label>
        <div class="input-group mb-3">
            <span class="input-group-text">
                <i class="bi bi-envelope"></i>
            </span>
            <input id="email" class="form-control" type="email" placeholder="Введите емаил..." />
        </div>

        <label class="form-label" for="name">Name:</label>
        <div class="input-group mb-3">
            <span class="input-group-text">
                <i class="bi bi-person"></i>
            </span>
            <input id="name" class="form-control" type="text" placeholder="Введите имя..." />
        </div>

        <label class="form-label" for="subject">Какую услугу хотите заказать?</label>
        <div class="input-group mb-3">
            <span class="input-group-text">
                <i class="bi bi-chat"></i>
            </span>
            <select id="subject" class="form-select">
                <option value="frontend" selected>Frontend</option>
                <option value="backend">Backend</option>
                <option value="other">Other</option>
            </select>
        </div>

        <div class="form-floating mb-3">
            <textarea id="query" class="form-control" style="height: 140px"></textarea>
            <label for="query">Ваше сообщение...</label>
        </div>

        <div class="text-center">
            <button class="btn btn-secondary">Отправить</button>
        </div>
    </form>
