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
        border: 1px solid #290101;
        border-radius: 50px;
        color: #ff0404;
        font-family: Arial, sans-serif;
        font-size: 2rem;
        padding: 1rem 2rem;
        margin-right: .6rem;
        vertical-align: center;
    }
    .form__field:focus {
        outline: none;
    }
    .form__button {
        background: #00cc99;
        border: none;
        border-radius: 20px;
        color: #ffffff;
        position: absolute;
        display: inline-block;
        font-family: Arial, sans-serif;
        padding: 1.7rem;
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
    .name{
    width: 100%;
    height: 100%;
    text-align: center;
    border-radius: 20px;
    display: block;
    margin-bottom: 2.0rem;
    text-align: center
    
    }
</style>

<h1 class="form__title">Lista de Tarefas</h1>
<input class="name" type="text" placeholder="Seu Nome" />


<form class="form" on:submit|preventDefault={addTask}>
    <input bind:value={task} class="form__field" type="text">
    <button class="form__button" type="submit">Add</button>
    
</form>

<TodoItem list={$tasks} />