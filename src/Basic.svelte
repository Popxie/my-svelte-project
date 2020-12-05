<script>
    import BasicOne from './BasicOne.svelte';
    let count = 0
    function handleClick() {
        count += 1
    }
    const userInfo = {
        name: 'xiehuaqiang',
        age: 28
    }
    $: doubled = count * 2
    $: console.log('$$props3:', $$props)
    // $: console.log(`the count is ${count}`)

    // $: {
    //     console.log(`the doubled is ${doubled}`)
    // }
    $: if (count >= 10) {
	    alert(`count is dangerously high!`);
        count = 9;
    }


    let numbers = [1, 2, 3, 4]
    function addNumber() {
        // numbers.push(numbers.length + 1) // it's won't work
        numbers = [...numbers, numbers.length +1]
    }
    $: sum = numbers.reduce((t, n) => t + n, 0)
</script>

<p>{count} doubled is {doubled}</p>
<button on:click="{handleClick}">
    Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<hr>
<p>{numbers.join(' + ')} = {sum}</p>
<button on:click="{addNumber}">
    Add a number
</button>

<hr>
<BasicOne answer={42}/>
