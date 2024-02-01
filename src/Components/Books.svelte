<script>
    import Book from "./Book.svelte";
    let content = "";
    let contentResponse = [];
    // const handleClick = (event) => value = event.target.value
    function handleClick() {
        contentResponse = fetch(
            `https://www.googleapis.com/books/v1/volumes?q=${content}`,
        )
            .then((res) => res.json())
            .then((apiResponse) => {
                console.log(apiResponse.items);
                contentResponse = apiResponse.items;
            });
    }
</script>

<section>
    <input placeholder="Search books..." bind:value={content} />
    <button on:click={handleClick}>Buscar</button>
    <div>
        {#await contentResponse}
            <h5><strong>Loading...</strong></h5>
        {:then carlos}
            {#each carlos as { volumeInfo }}
                <Book
                    title={volumeInfo.title}
                    imageLinks={volumeInfo.imageLinks}
                    authors={volumeInfo.authors}
                    publishedDate={volumeInfo.publishedDate}
                    infoLink={volumeInfo.infoLink}
                    description={volumeInfo.description}
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
    section {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
    button {
        font-size: 15px;
        color: black;
        background-color: #00ced1;
        border-color: #00ced1;
        padding: 10px 20px;
        cursor: pointer;
        margin: 0;
        transition: background-color, 0.3s;
    }
    button:hover {
        background-color: #00e5e8;
        padding: 12px 22px;
    }
    div {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        justify-content: center;
        gap: 2rem;
    }
    input {
        padding: 1rem;
        margin: 0;
        width: 300px;
    }
    h5 {
        margin: 0;
        font-size: 18px;
        color: white;
    }
</style>
