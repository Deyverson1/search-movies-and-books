<script>
  import SearchMovies from "./SearchMovies.svelte";
  import Books from "./Books.svelte";
  let option;
  let selectedOption;
  function handleClick() {
    selectedOption = option;
  }
</script>

<section>
  <div>
    <select bind:value={option} name="Chose" id="Chose">
      <option value="movies">Movies</option>
      <option value="books">Books</option>
    </select>
  </div>
  <button on:click={handleClick}> Choose </button>
</section>

<article class="search-container">
  {#if selectedOption == "movies"}
    <SearchMovies />
  {:else if selectedOption == "books"}
    <Books />
  {/if}
</article>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 16px;
    margin: 2rem;
    height: 100px;
  }
  select {
    font-size: 15px;
    color: black;
    padding: 10px 30px;
    margin: 0;
  }
  button {
    font-size: 15px;
    color: black;
    background-color: #00ced1;
    border-color: #00ced1;
    padding: 10px 20px;
    cursor: pointer;
    margin: 0;
    transition: background-color, .5s;
    border-radius: 2px;
  }
  button:hover {
    background-color: #00e5e8 ;
    padding: 12px 22px;
  }
  article {
    display: flex;
    justify-content: center;
    margin: 2rem;
  }
</style>
