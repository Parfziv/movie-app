<script>
    import MovieCard from "./MovieCard.svelte"; 
    export let movies;
</script>

<h1>Popular TV shows</h1>
<section class="movie-wrapper">
    {#each movies as movie}
    <MovieCard {movie}></MovieCard> 
    {/each}
</section>
<style>
    h1{
        font-size: 2rem;
        text-align: center;
        font-family: sans-serif;
        color: #800080;
        letter-spacing: 0.1rem;
    }
     .movie-wrapper{
         display: grid;
         grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
         grid-column-gap: 0.3rem;
         padding: 0.5rem 0.4rem;
    }
</style>