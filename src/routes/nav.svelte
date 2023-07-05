<script>
// @ts-nocheck

    
    import { onMount } from 'svelte';
    import { flip } from "svelte/animate";
	import Layout from './+layout.svelte';
    

    let curpage;

    let sites = [
        {name: 'Chess', url: '/Chess'},
        {name: 'Projects', url: '/Projects'},
        {name: 'Home', url: '/'},
        {name: 'Eduaction', url: '/Education'},
        {name: 'Contact', url: '/contact'}
    ]

    onMount(() => {
        curpage = sites.find(site => site.url === window.location.pathname);
        center(curpage);
    })
    

    function center(page){
        let temp = sites;
        temp = temp.filter(site => site.url !== page.url);
        let left = [temp[0], temp[1]];  
        let right = [temp[2], temp[3]];
        sites = [...left, page, ...right];
    }
</script>


<nav>
    {#each sites as site (site)}
        <a animate:flip href={site.url} on:click={() => {center(site)}}>{site.name}</a>
    {/each}
</nav>


<style>
    nav{
        display: flex;
        justify-content: space-around;
        align-items: center;
        background-color: #170545;
        color: #fff;
        padding: 1rem;
        border-radius: 3rem;
        box-shadow: white 0px 0px 10px 0px;
        width: 50%;
    }

    nav a{
        text-decoration: none;
        color: #fff;
        padding: 0.5rem;
        border-radius: 2rem;
        font-size: 1.2rem;
    }

    
</style>