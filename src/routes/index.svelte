
<script context="module">
    export async function load({fetch}){
        const res = await fetch(
            `https://api.themoviedb.org/3/tv/popular?api_key=37cf6a7517265e39cc58fa576a2e6de0&language=en-US&page=1`
        );
        const data = await  res.json();
        if(res.ok){
            return{
                props:
                {movies : data.results}
            }
        }
        return{
            error: new Error('Results not found..'),
        }
    }

</script>

<script>
    import Movies from  "../components/Movies.svelte";
    import SearchMovies from "../components/SearchMovies.svelte";
import Error from "./__error.svelte";
import {fly} from 'svelte/transition';
    export let movies;
    
</script>

<section in:fly={{ y: 50, duration: 500, delay:500}} out:fly={{ duration: 500}}>
    <SearchMovies/>
    <Movies {movies}/>
</section>