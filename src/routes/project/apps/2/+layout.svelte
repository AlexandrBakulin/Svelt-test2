<div class="container">
    <a href="/project">Go back to project</a>
    <p style="font-weight: bold">Выводится название места расходов, а ниже количество потраченных денег.
    Можно написать бесконечное множество сумм под одним названием места.
    При вводе другого места суммы записываются под ним.
    Кнопка действия очищает ВВОДИМЫЕ значения для всех элементов.
    </p>
    <slot />
</div>
<style>
    .container {
        margin: 50px auto;
        max-width: 800px;
        padding: 0 20px;
        background: whitesmoke;
        border: 1px solid grey;
    }
    a {
        font-weight: bold;
    }
</style>