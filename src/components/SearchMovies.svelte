<script>
    let inputValue = '';
    let active = false;
    import { goto } from '$app/navigation';
    import {fly} from 'svelte/transition';
    function cancelActive(){
        if(inputValue){
            active = !active;
        }
    }
    function submitSearch(){
        goto('/search/' + inputValue);
    }
</script>

<div class="home">
    <form on:submit|preventDefault={submitSearch}>
        <input bind:value={inputValue}
        on:blur={cancelActive}
        on:focus={()=> active = true}
        class={active ? 'selected' :''}
         type="search"
        placeholder="Search Tv shows..">
        {#if inputValue}
        <button in:fly={{ y: 0, duration: 500}} out:fly={{ y: 0, duration: 500}}>Search </button>
        {/if}
    </form>
</div>

<style>
    .home{
        display: flex;
        justify-content: flex-end;
        padding: 1rem;
    }
    input{
        border: 1px solid #800080;
        outline: none;
        padding: 0.3rem;
        border-radius: 0.2rem;
        width: 100%;
    }
    form{
        display: flex;
        align-items: center;
        gap: 0.2rem;
    }
    input::placeholder{
        padding: 0.5rem;
        color: #800080;
        letter-spacing: 0.1rem;
    }
    button{
        padding: 0.3rem;
        background: #800080;
        color: #fff;
        outline: none;
        border: none;
        font-size: 1rem;
        border-radius: 0.3rem;
        cursor: pointer;
    }
    input.selected{
        background: #800080;
        color: #fff;
    }
</style>