# Navbar
Адаптивное меню: https://getbootstrap.com/docs/5.2/components/navbar/. Многое можно изменять: цвет, элементы, положение и мн.др.

- navbar - класс меню
- navbar-expand-md - означает что меню схлопнется на размере `md`, можно поставить `lg` и т.д.
- nav.navbar.navbar-expand-lg.bg-dark.navbar-dark - пример для темного меню со светлым текстом
- bg-dark или bg-primary - цвет фона
- navbar-dark - светлый текст
- fixed-top - закрепляем меню сверху, также нужно сделать отступ сверху
- .container - контейнер обычно помещают внутрь тега `nav`

Отступ сверху при фиксированном меню:

    body::before {
        display: block;
        content: '';
        height: 56px;
    }

Простой пример меню:

    <!-- navbar -->
    <nav class="navbar navbar-expand-lg bg-dark navbar-dark">
        <div class="container">
            <a href="#" class="navbar-brand">Brand</a>
            <button class="navbar-toggler" type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbar-main">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbar-main">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a href="#learn" class="nav-link">Learn</a>
                    </li>
                    <li class="nav-item">
                        <a href="#questions" class="nav-link">Questions</a>
                    </li>
                    <li class="nav-item">
                        <a href="#instructors" class="nav-link">Instructors</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

Еще пример:

    <!-- navbar -->
    <nav class="navbar navbar-expand-md bg-light">
        <div class="container">
            <a class="navbar-brand" href="#intro"><span class="fw-bold text-secondary">Brand</span></a>
            <!-- toggle button for mobile nav -->
            <button class="navbar-toggler" type="button"
                data-bs-toggle="collapse"
                data-bs-target="#main-nav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <!-- navbar links -->
            <div class="collapse navbar-collapse justify-content-end align-center" id="main-nav">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <a class="nav-link" href="#topics">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#reviews">Reviews</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contact">Contact</a>
                    </li>
                    <li class="nav-item d-md-none">
                        <a class="nav-link" href="#pricing">Pricing</a>
                    </li>
                    <li class="nav-item ms-2 d-none d-md-inline">
                        <a class="btn btn-secondary" href="#pricing">Buy now</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
