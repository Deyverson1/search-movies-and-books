<script>
    export let movieTitle, poster, year, index;
</script>
<section>
    <article id={index}>
        <h3>{movieTitle}</h3>
        <span>{year}</span>
        <img src={poster} alt={movieTitle}>
    </article>
</section>

<style>
    section{
        display: flex;
       padding: .5rem;
       flex: 1;
       box-sizing: border-box;
    }
    h3{
        max-width: 200px;
        text-align: center;
        margin: 0;
    }
    span{
        margin-bottom: 1rem;
    }
    article{
        display: flex;
        flex-direction: column;
        padding: 1rem 3rem;
        align-items: center;
        justify-content: center;
        border-radius: 10px;
        height: 400px;
        border: 1px solid #ccc;
        background-color: #ccc;
        margin: 2rem;
    }
    img{
        width: 200px;
        height: 342px;
    }
</style>