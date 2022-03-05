
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
    }

</script>

<script>
    import Movies from  "../components/Movies.svelte";
    export let movies;
</script>

<section>
    <Movies {movies}/>
</section>