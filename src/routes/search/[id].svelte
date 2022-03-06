<script context="module">
    export async function load({fetch, params}){
        const res = await fetch(
            `https://api.themoviedb.org/3/search/tv?api_key=37cf6a7517265e39cc58fa576a2e6de0&language=en-US&query=${params.id}&page=1&include_adult=false`
        );
        const data = await  res.json();
        if(res.ok){
            return{
                props:
                {searchTv: data.results}
            }
        }
    }

</script>
<script>
    import MovieCard from "../../components/MovieCard.svelte";
    export let searchTv;
</script>

<section class="movie-wrapper">
    {#each searchTv as movie}
    <MovieCard {movie}></MovieCard> 
    {/each}
</section>

<style>
    .movie-wrapper{
         display: grid;
         grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
         grid-column-gap: 0.3rem;
         padding: 1rem 0.4rem;
    }
</style>