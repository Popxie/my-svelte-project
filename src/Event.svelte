<script>
    import EventSon from './EventSon.svelte'
    let m = { x: 0, y: 0 }
    function handleMousemove(event) {
        m.x = event.clientX;
		m.y = event.clientY;
    }
</script>

<div on:mousemove={handleMousemove}>
    <div>The mouse position is {m.x} x {m.y}</div>
    <EventSon on:message/>
</div>

<style>
    div {
        height: 100px;
        background-color: lightblue;
    }
</style>