# Tooltips
Всплывающие подсказки: https://getbootstrap.com/docs/5.2/components/tooltips/

Сначала размещаем код в JavaScript:

    const tooltips = document.querySelectorAll('.tt')
    tooltips.forEach(t => {
        new bootstrap.Tooltip(t)
    })

Затем HTML-код:

    <!-- tooltip -->
    <span class="tt" data-bs-placement="bottom" title="Программист Иванов И.И.">
        <img class="img-fluid" src="img/bmw.jpg" alt="BMW" />
    </span>

    <!-- tooltip -->
    <span class="input-group-text">
        <span class="tt" data-bs-placement="top" title="Введите своё имя!">
            <i class="bi bi-question-circle text-muted"></i>
        </span>
    </span>
