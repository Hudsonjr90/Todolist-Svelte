<script>
    export let list
</script>

<style>
    .list__item {
        color: rgb(17, 14, 204);
        font-family: Arial, sans-serif;
        font-size: 1.5rem;
        list-style: none;
        margin: .5rem 0;
    }
</style>

<ul class="list">
    {#each list as item}
        <li class="list__item">{ item }</li>
    {/each}
</ul>