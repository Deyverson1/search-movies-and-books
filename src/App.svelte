<script>
	import SearchMovies from "./Components/SearchMovies.svelte";
	import Books from "./Components/Books.svelte";
	let option;
	let selectedOption;
	function handleClick(){
		selectedOption = option
	}
</script>

<section>
	<select bind:value={option} name="Chose" id="Chose">
		<option value="movies">Movies</option>
		<option value="books">Books</option>
	</select>
	<button on:click={handleClick}> Chose </button>    
</section>

<article class="search-container">
	{#if selectedOption == 'movies'}
		<SearchMovies/>
	{:else if selectedOption == 'books'}
		<Books/>
	{/if}
</article>

<style>
	section{
		display: flex;
		justify-content: center;
		gap: 16px;
		margin: 2rem;
	}
	select{
		font-size: 15px;
		color: black;
		padding: 10px 30px;
	}
	button{
		font-size: 15px;
		color: black;
		padding: 10px 20px;
		cursor: pointer;
	}
	article{
		display: flex;
		justify-content: center;
		margin: 2rem;
	}
</style>

