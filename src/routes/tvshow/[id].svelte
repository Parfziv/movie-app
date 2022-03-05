<script context="module">
    export async function load({fetch, params}){
        const res = await fetch(
            ` https://api.themoviedb.org/3/tv/${params.id}?api_key=37cf6a7517265e39cc58fa576a2e6de0&language=en-US`
        );
        const tvDetail = await  res.json();
        if(res.ok){
            return{
                props:
                {tvDetail}
            }
        }
    }

</script>

<script>
    export let tvDetail;
</script>
<div class="container">

    <div class="image-container">
        <img src={`https://image.tmdb.org/t/p/original` + tvDetail.backdrop_path} alt={tvDetail.name}>
    </div>
    <div class="description">
        <h2>{tvDetail.name} ({tvDetail.first_air_date})</h2>
        <p>{tvDetail.overview}</p>
        <p><span>Number of episodes: </span>{tvDetail.number_of_episodes}</p>
        <p><span>Total seasons:</span>{tvDetail.seasons.length}</p>
    </div>
</div>

<style>
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border: 2px solid #fff;
        border-radius: 0.2rem;
        box-shadow: 0 3px 10px rgb(0,0,0,0.4);
        margin-bottom: 1rem;
        padding: 1rem;
    }
    .image-container{
        width:100%;
    }
    img{
        width:100%;
        border-radius: 0.4rem;
    }
    h2{
        color: #800080;
        margin: 0.4rem;
    }
    p{
        font-size: 1rem;
        margin: 0.4rem;
    }
    p>span{
        font-weight: bold;
        color: #800080;
    }
</style>