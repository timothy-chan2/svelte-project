<script lang="ts">
  import { identity } from 'svelte/internal';
import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'

  const person  = {
    name: "Jim",
    num: 5
  }

  let user = {
    loggedIn: false
  }

  const cats = [
    { id: "78906d3", name: "Kitty" },
    { id: "23354u7", name: "Jiminey" },
    { id: "47866z9", name: "Kat" }
  ]

  function toggle() {
    user.loggedIn = !user.loggedIn
  }
</script>

<main>
  <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer"> 
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer"> 
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  {#if user.loggedIn}
    <button on:click={toggle}>
      Log out
    </button>
  {:else}
    <button on:click={toggle}>
      Log in
    </button>
  {/if}

  <div class="card">
    {#if user.loggedIn}
      <Counter name={"Tom"} num={4}/>
      <Counter {...person}/>
    {:else}
      <Counter />
    {/if}
  </div>

  {#each cats as {id, name}, ind}
    <p>{name} has a collar ID {id} and finished #{ind + 1} in the race.</p>
  {/each}

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
  button {
    color: white;
    background-color: #4CAF50;
  }
</style>