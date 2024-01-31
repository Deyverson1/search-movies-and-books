<script>
    export let title,publishedDate,description,infoLink, imageLinks = {}, authors = {};
    
</script>
<section>
    <article>
        <section>
            <h3>{title}</h3>
            <p>{description}</p>
        </section>
        <div>
            <h4>{authors}</h4>
            <h5>{publishedDate}</h5>
            <img src={imageLinks.thumbnail} alt={title}>
            <a target="_blank" href={infoLink}>Visit</a>
        </div>
    </article>
</section>

<style>
    section{
        display: flex;
        flex-direction: column;
        padding: .5rem;
        box-sizing: border-box;
        align-items: center;
    }
    h3{
        
        text-align: center;
        margin: 0;
    }
    p{
        max-width: 500px;

    }
    article{
        display: flex;
        padding: 1rem 3rem;
        align-items: center;
        gap: 10px;
        border-radius: 10px;
        height: auto;
        border: 1px solid #ccc;
        background-color: #ccc;
        margin: 1rem;
    }
    div{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img{
       max-width: 192px;
    }
</style>