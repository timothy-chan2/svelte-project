<script lang="ts">
  let count = 0
  $: tripleCount = count * 3

  const incrementCount = () => {
    count += 1
  }
</script>

<button on:click={incrementCount}>
  Count is {count}
</button>

<p>
  {count} * 3 = {tripleCount}
</p>

<style>
  button {
    color: yellow;
    background-color: blue;
  }
</style>