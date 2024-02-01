<script>
    import Movie from "./Movie.svelte";
    let value = ''
    let response = []
    const handleInput = (event) => value = event.target.value
    $: if(value.length > 2) {
        response = fetch(`https://www.omdbapi.com/?s=${value}&apikey=422350ff`)
        .then(res => {
            if (!res.ok) {
                throw new Error('Something went wrong with fetching');
            }
            return res.json();
        })
            .then(apiResponse => apiResponse.Search || [])
    }
</script>

<section>
    <input placeholder="Search movies..." value={value} on:input={handleInput}>
   <div>
        {#await response}
        <h5><strong>Loading...</strong></h5>
        {:then carlos} 
        {#each carlos as {Title: movieTitle, Year, Poster}, index} 
            <Movie
            movieTitle={movieTitle} 
            year={Year}
            poster={Poster}
            index={index}
            />
        {:else}
            <h5><strong>No hay resultados</strong></h5>
        {/each}
        {:catch error}
        <p>Error{error}</p>
        {/await}
   </div>
</section>

<style>
    section{
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-right: -8px;
    }
    div{
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        justify-content: center;
    }
    input{
        padding: 1rem;
        margin: 0;
        margin-bottom: 4rem;
        width: 300px;
    }
    h5 {
        margin: 0;
        font-size: 18px;
        color: white;
    }
</style>

    

