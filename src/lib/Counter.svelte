<script lang="ts">
  let count: number = 0
  const increment = () => {
    count += 1
  }
</script>

<button on:click={increment}>
  count is {count}
</button>

<p>
  hello
</p>

<style>
  button {
    color: yellow;
    background-color: blue;
  }
</style>