<script>
  import Page from './components/Page.svelte';
  let pages = [0, 1];

</script>

<main>
  {#each Array.from(pages.entries()) as [i, page]}
    <Page/>
    <button on:click={() => {pages.splice(i, 1); pages=pages}}>Удалить страницу</button>
  {/each}
  <button on:click={() => {pages = pages.concat(Page)}}>Новая страница</button>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>