# Container
Центрирует контент (макет).

- `container` используется для обертки содержимого, может использоваться вне сетки.
- `max-width: 1320px` при ширине экрана `>= 1400px`
- `container-fluid` занимает всю ширину экрана

HTML-код:

    <div class="container">
        <h2>Заголовок</h2>
        <p>Параграф.</p>
    </div>

CSS-правила:

    .container {
        max-width: 1320px;
    }

    .container {
        --bs-gutter-x: 1.5rem;
        --bs-gutter-y: 0;
        width: 100%;
        padding-right: calc(var(--bs-gutter-x) * 0.5);
        padding-left: calc(var(--bs-gutter-x) * 0.5);
        margin-right: auto;
        margin-left: auto;
    }
