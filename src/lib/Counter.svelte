<script lang="ts">
  export let name = "The stranger";
  export let num = 2;

  import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

  let count = 0
  // Reactive declaration: Re-run this line of code whenever any of the referenced values change
  $: multiplicationCount = count * num

  const incrementCount = () => {
    count += 1

    dispatch('popUpMessage', {
			text: 'Power Up!'
		});
  }
</script>

<button on:click={incrementCount}>
  {name}'s count is {count}
</button>

<p>
  {name}'s math equation: {count} * {num} = {multiplicationCount}
</p>

<style>
  button {
    color: yellow;
    background-color: blue;
  }
</style>