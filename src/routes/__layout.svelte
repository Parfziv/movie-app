<script>
    import SearchMovies from "../components/SearchMovies.svelte";
    import Nav from "../components/Nav.svelte";
    import global from "../styles.css";
</script>
<svelte:head>
    <title>TV Database</title>
</svelte:head>
<Nav/>
<SearchMovies/>
<slot/>
<footer>
    <p>Made with <span>&#128151</span> by Sudan.</p>
</footer>

<style>
    footer{
        font-size: 1.5rem;
        padding: 2rem;
        text-align: center;
        color: #fff;
        background-color: #800080;
    }
    span{
        color: #800080;
        font-size: 2rem;
    }
</style>