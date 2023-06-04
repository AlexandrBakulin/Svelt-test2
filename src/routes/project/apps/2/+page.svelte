<main>
    <h1>Учёт расходов</h1>
    <form><table>
        {#each todoList as item, index}
            <div class="todo" class:completed={item.completed}></div>
            <span class="todo_text">{item.Task}</span>
            <span class="todo_buttons">
                <button class="remove1" on:click={ () => remove1(index)}>Delete</button>
            </span>
        {/each}

        <tr><th class="table-slot">Названия:</th><th class="table-slot">Сумма:</th><th class="table-slot">Действия:</th></tr>
        <tr><td class="table-slot">{tag}</td><td class="table-slot">{sum}</td><td class="table-slot"><button class="remove" on:click={ () => remove(tag, sum)}>Удалить</button></td></tr>
    </table>
        <div class="tag">Название:
            <form on:submit|preventDefault={add}>
                <input bind:value={tag} placeholder="Enter tag">
                <button class="add-todo" on:click={add}><span>+</span></button>
            </form>
        </div>
        <div class="sum">Сумма:</div>
        <form on:submit|preventDefault={add1}>
            <input bind:value={sum} placeholder="Enter sum">
            <button class="add-todo" on:click={add}><span>+</span></button>
        </form>
    </form>
</main>
<script>
    let tag = '';
    let sum = '';
    let todoList = [];
    function add() {
        if (tag !== '') {
            todoList = [
                ...todoList,
                {
                    Task: tag,
                    Completed: false
                }
            ]
            tag = '' - sum;
            tag = '';
        }
    }
    function add1() {
        if (sum !== '') {
            todoList = [
                ...todoList,
                {
                    Task: sum,
                    Completed: false
                }
            ]
            sum = '';
        }
    }
    function remove() {
        tag = '';
        sum = '';
    }
    function remove1(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }
    function complete(index) {
        todoList[index].Completed = !todoList[index].Completed;

    }

</script>
<style>
    .table-slot {
        height: 50px;
        width: 150px;
        border: 1px solid black;
        text-align: center;
    }
    .remove {
        width: 50%;
        height: 50%;
        margin: auto;
    }
    .todo_buttons {
        width: content-box;
        height: content-box;
    }
    .remove1 {
        width: 50px;
        height: 20px;

    }
</style>
