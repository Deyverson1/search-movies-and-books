<script>
    export let movieTitle, poster, year, index;
</script>

<section>
    <article id={index}>
        <picture>
            <img src={poster} alt={movieTitle} />
        </picture>
        <div class="content">
            <h3>{movieTitle}</h3>
            <span>{year}</span>
        </div>
    </article>
</section>

<style>
    section {
        display: flex;
        padding: 0.5rem;
        justify-content: center;
        flex: 1;
        box-sizing: border-box;
    }
    .content {
        display: flex;
        flex-direction: column;
        justify-content: center; 
        align-items: center; 
        padding: 1rem; 
    }
    h3 {
        max-width: 300px;
        text-align: center;
        margin: 0;
        color: white;
    }
    span {
        margin-bottom: 1rem;
        color: white;
    }
    article {
        border-radius: 0.5rem;
        border: 1px solid #4a5568; /* gray-700 */
        box-shadow:
            0 4px 6px -1px rgba(0, 0, 0, 0.1),
            0 2px 4px -1px rgba(0, 0, 0, 0.06);
        background-color: #2d3748; /* gray-800 */
        border-color: #4a5568; /* gray-700 */
        transition: all 0.3s ease-in-out;
        display: flex;
        flex-direction: column;
    }
    article:hover {
        transform: scale(1.05);
        background-color: #4a5568; 
        border-color: #2d3748;
    }
    picture {
        display: flex;
        justify-content: center;
        padding: 1rem;
    }
    img {
        width: 300px;
        height: 350px;
    }
</style>
