<script>
    export let title,
        publishedDate,
        description,
        infoLink,
        imageLinks = {},
        authors = {};
</script>

<section>
    <article>
        <section>
            <h3>{title}</h3>
            <p>
                {description !== null && description?.length > 750
                    ? description?.slice(0, 750) + "..."
                    : description}
            </p>
        </section>
        <div>
            <h4>{authors[0]}</h4>
            <h5>{publishedDate}</h5>
            <picture>
                <img src={imageLinks.thumbnail} alt={title} />
            </picture>
            <a target="_blank" href={infoLink}>Visit</a>
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
    p {
        display: none;
    }
    article:hover a {
        display: block;
    }
    article:hover p {
        display: flex;
        font-size: 15px;
        font-weight: 300;
        color: var(--primary-color);
        text-align: start;
    }
    article:hover h3,
    article:hover h4,
    article:hover h5,
    article:hover picture {
        display: none;
    }
    h3 {
        color: var(--primary-color);
        font-weight: 800;
        max-width: 300px;
        text-align: center;
        margin: 0;
    }
    h4,
    h5 {
        color: var(--gray-light);
        font-weight: 300;
        max-width: 300px;
        text-align: center;
        margin: 0;
    }
    p {
        max-width: 500px;
        color: var(--primary-color);
    }
    picture {
        display: flex;
        justify-content: center;
        padding: 1rem;
    }
    article {
        border-radius: 0.5rem;
        border: 1px solid var(--gray-medium);
        box-shadow:
            0 4px 6px -1px rgba(0, 0, 0, 0.1),
            0 2px 4px -1px rgba(0, 0, 0, 0.06);
        background-color: #2d3748;
        border-color: var(--gray-medium);
        transition: all 0.3s ease-in-out;
        display: flex;
        flex-direction: column;
        padding: 4rem;
        padding-top: 1rem;
        width: 250px;
        height: 450px;
    }
    article:hover {
        transform: scale(1.05);
        background-color: #4a5568;
        border-color: #2d3748;
    }
    div {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img {
        width: 200px;
        height: 350px;
    }
    a {
        display: none;
        font-size: 15px;
        color: black;
        background-color: var(--dark-turquoise);
        border-color: var(--dark-turquoise);
        padding: 10px 20px;
        cursor: pointer;
        margin: 0;
        transition: background-color, 0.5s;
        text-decoration: none;
        border-radius: 5px;
    }
</style>
