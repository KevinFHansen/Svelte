<script>
  import svelteLogo from './assets/svelte.svg'
  import Counter from './lib/Counter.svelte'
  import Nested from './Nested.svelte';
  
  let name = 'world';
  let src = '/images/Studiebilled1.jpg'
  let string = `this string contains some <strong>HTML!!!</strong>`;
  let count = 0;
  $: doubled = count * 2;
  $: {
	console.log('the count is ' + count);
	alert('I SAID THE COUNT IS ' + count);
}
$: if (count >= 10) {
	alert('count is dangerously high!');
	count = 9;
}
  function incrementCount() {
	count += 1;
  }

  let numbers = [1, 2, 3, 4];

  function addNumber() {
	numbers = [...numbers, numbers.length + 1];
}
$: sum = numbers.reduce((t, n) => t + n, 0);
</script>

  
<main>


  <p>{numbers.join(' + ')} = {sum}</p>

  <button on:click={addNumber}>
    Add a number
  </button>

  <p>{count} doubled is {doubled}</p>
  <button on:click={incrementCount}>Clicked {count} {count === 1 ? 'time' : 'times'}</button>
  <p>{string}</p>
  <p>{@html string}</p>

<p>This is a paragraph.</p>
  <Nested/>

  <h1>Hello {name}!</h1>
  <img {src} alt="A man dances">



  <style>
    p {
      color: purple;
      font-family: 'Comic Sans MS', cursive;
      font-size: 2em;
    }
  </style>


  <div>
    <a href="https://vitejs.dev" target="_blank"> 
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank"> 
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank">SvelteKit</a>, the official Svelte app framework powered by Vite!
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
</style>
