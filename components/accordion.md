# Accordion
https://getbootstrap.com/docs/5.2/components/accordion/

Пример кода:

    <div class="accordion" id="chapters">
        <div class="accordion-item">
            <h2 class="accordion-header">
                <button class="accordion-button" type="button"
                    data-bs-toggle="collapse"
                    data-bs-target="#chapter-1">
                    Вопрос 1
                </button>
            </h2>
            <div id="chapter-1" class="accordion-collapse collapse show"
                data-bs-parent="#chapters">
                <div class="accordion-body">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi ratione officia mollitia laborum vitae rerum officiis enim ea dolor. Quos natus iste veniam nisi?
                </div>
            </div>
        </div>
        <div class="accordion-item">
            <h2 class="accordion-header">
                <button class="accordion-button collapsed" type="button"
                    data-bs-toggle="collapse"
                    data-bs-target="#chapter-2">
                    Вопрос 2
                </button>
            </h2>
            <div id="chapter-2" class="accordion-collapse collapse"
                data-bs-parent="#chapters">
                <div class="accordion-body">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Optio labore mollitia velit totam, consequuntur perferendis numquam incidunt a natus. Dolor blanditiis quam repellat cupiditate?
                </div>
            </div>
        </div>
    </div>
