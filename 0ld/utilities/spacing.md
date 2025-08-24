# Spacing

## margin, padding

    p-1 (от 0 до 5, auto) 0.25rem to 3rem
    pt
    pe
    pb
    ps
    px
    py

    m-1
    mt
    me
    mb
    ms
    mx
    my

Поддерживают брейкпоинты.

## gap

    g-1

Вроде работает и без `d-grid`:

    <div class="d-grid gap-3">
        <div class="p-2 bg-light border"> 1 </div>
        <div class="p-2 bg-light border"> 2 </div>
        <div class="p-2 bg-light border"> 3 </div>
    </div>

## Разное
- mx-auto - центрирование по горизонтали
- mb-3 mb-md-0 // аналог g-4
