<script>
    export let movie;
</script>

    <div class="container">

        <div class="movie-list">
            <a href={`/tvshow/` +movie.id}>
                <img src={`https://image.tmdb.org/t/p/w300` + movie.poster_path} alt={movie.name}>
            </a>
            <div class="description">
                <h2>{movie.name}</h2>
            <p>{movie.first_air_date}</p>
            </div>
        </div>
    </div>

<style>
    .container{
        display: flex;
        align-items: center;
        justify-content: center;
        border: 2px solid #fff;
        border-radius: 0.2rem;
        box-shadow: 0 3px 10px rgb(0,0,0,0.4);
        margin-bottom: 1rem;
        padding: 0.1rem;
    }
    .container:hover{
        scale: 0.1rem;
    }
   .movie-list{
       display: flex;
       flex-direction: column;
   }
   img{
       height: 50vh;
       border-radius: 0.4rem;
       object-fit: cover;
        margin-bottom: 0.5rem;
   }
   h2{
       font-size: 1rem;
       color: #800080;
   }
   p{
       font-size: 0.8rem;
       color: gray;
   }
</style>