<script>

    let array = [
        { name: '001', age: 1 },
        { name: '002', age: 2 },
        { name: '003', age: 3 },
        { name: '004', age: 4 }
    ]
    function handleClick() {
        array = array.slice(1)
        console.log('array: ', array)
    }
</script>

{#each array as item (item.age)}
    <div>name:{item.name}, age:{item.age}</div>
{/each}
<button on:click="{handleClick}">删除第一个</button>
