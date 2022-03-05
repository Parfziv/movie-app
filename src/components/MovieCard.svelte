<script>
    export let movie;
</script>

    <div class="movie-list">
        <img src={`https://image.tmdb.org/t/p/w300` + movie.poster_path} alt={movie.name}>
        <div class="description">
            <h2>{movie.name}</h2>
        <p>{movie.first_air_date}</p>
        </div>
    </div>

<style>
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