<script>
    import Icon from "../../../../components/Icon.svelte";

    let newItem = '';
    let todoList = [];

    function add() {
        if (newItem !== '') {
            todoList = [
                ...todoList,
                {
                    Task: newItem,
                    Completed: false,
                },
            ]
            newItem = '';
        }
    }

    function remove(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }

    function complete(index) {
        todoList[index].Completed = !todoList[index].Completed;
    }
</script>
<main>
    <h1>My todo list</h1>
    <form on:submit|preventDefault={add}>
        <input bind:value={newItem} placeholder="Enter todo">
        <button class="add-todo" on:click={add}><span>+</span></button>
    </form>
    <div class="todos">
        {#each todoList as item, index}
            <div class="todo" class:completed={item.completed}>
                <span>{item.Task}</span>
                <div class="todo_buttons">
                    <button class="complete" on:click={ () => complete(index)}>
                        <Icon name="check-mark"></Icon>
                    </button>
                    <button class="delete" on:click={ () => remove(index)}>
                        <Icon name="delete"></Icon>
                    </button>
                </div>
            </div>
        {/each}
    </div>
</main>
<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background: #6c6969;
        text-decoration: none;
    }

    form {
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
        background: blue;
    }

    input {
        flex-grow: 1;
        width: 0;
        border: none;
        border-bottom: 1px solid black;
        box-shadow: none;
        font-size: 1.2rem;
        margin: 0;
        outline: none;
    }

    .todos {
        width: 100%;
        max-width: 500px;
    }

    .todo {
        display: flex;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 15px rgb(0 0 0 / 20%);
        background-color: hsla(0 0% 100%);
        margin-top: 1rem;
        font-size: 1.2rem;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }

    .todo_buttons {
        display: flex;
        align-items: center;
        margin-left: 1rem;
    }

    h1 {
        text-align: center;
        font-size: 1.5rem;
        margin: 2em 0;
    }

    .add-todo {
        color: white;
    }

    button {
        background-color: transparent;
        border: none;
    }

    button.delete,
    button.delete:hover {
        height: 2rem;
        width: 2rem;
        color: brown;
        transition: color 100ms ease-out;
    }

    button.complete,
    button.complete:hover {
        height: 2rem;
        width: 2rem;
        color: green;
        transition: color 100ms ease-out;
    }
</style>