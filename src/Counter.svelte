<script>
let contador = 0;
function count(){
    contador ++;
}

</script>

<div class="counter">
    <input type="number" name="counter" id="counter" bind:value="{contador}"/>
    <button on:click="{count}">+1</button>

</div>

