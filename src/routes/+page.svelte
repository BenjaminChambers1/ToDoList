<div class="text-center">Basic To Do App</div>
<hr/>
<div class="center-block text-center">
    <input type="text" placeholder="enter somthing to do" bind:value={input_todo}>
    <button on:click={add_todo_item}>+</button>

    {#each todo_list as item, i}
    <div>
        { item }
        <button on:click={() => remove_from_todo(i)}>x</button>
    </div>
    {/each}
</div>

<script>
    let input_todo = '';
    /**
     * @type {any[]}
     */
    let todo_list = [];
    const add_todo_item = function() {
        todo_list.push(input_todo);
        todo_list = todo_list;
    }
    const remove_from_todo = function(/** @type {number} */ i) {
        todo_list.splice(i, 1);
        todo_list = todo_list;
    }
</script>
<style>
.center-block {
    margin: auto;
    width: 50%;
}

.text-center {
    text-align: center;
}
</style>