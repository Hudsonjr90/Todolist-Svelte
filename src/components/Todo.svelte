<script>
    import TodoItem from './TodoItem.svelte'
    import { tasks } from '../store.js'
    let task = ''
    const addTask = () => {
        tasks.update(() => [...$tasks, task ])
        task = ''
    }
</script>

<style>
    .form__field {
        border: 1px solid #dcdcdc;
        border-radius: 50px;
        color: #333333;
        font-family: Arial, sans-serif;
        font-size: 2rem;
        padding: 1rem 2rem;
        margin-right: .5rem;
        vertical-align: middle;
    }
    .form__field:focus {
        outline: none;
    }
    .form__button {
        background: #00cc99;
        border: none;
        border-radius: 10px;
        color: #ffffff;
        position: absolute;
        display: inline-block;
        font-family: Arial, sans-serif;
        padding: 1.5rem;
    }
    .form__button:focus {
        outline: none;
    }
    .form__button:hover {
        cursor: pointer;
    }
 
    .form__title{
    width: 100%;
    height: 100%;
    text-align: center;
    }
</style>

<h1 class="form__title">TO DO LIST</h1>

<form class="form" on:submit|preventDefault={addTask}>
    <input bind:value={task} class="form__field" type="text">
    <button class="form__button" type="submit">Add</button>
</form>
<TodoItem list={$tasks} />