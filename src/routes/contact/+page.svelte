<script>
    import { onMount } from 'svelte';
    import { flip } from "svelte/animate";
    
    /**
	 * @type {{ name: string; url: string; } | undefined}
	 */
    let page;
    let sites = [
        {name: 'Home', url: '/'},
        {name: 'About', url: '/about'},
        {name: 'Contact', url: '/contact'}
    ]

    onMount(() => {
        page = sites.find(site => site.url === window.location.pathname);
        setInterval(() => {
            page = sites.find(site => site.url === window.location.pathname);
        }, 1000);
        setInterval(() => {
            center();
        }, 1000);
    })
    

    function center(){
        if(!page){
            return;
        }
        let center = sites.splice(sites.findIndex(site => site.url === page?.url), 1);
        let left = sites.slice(0, Math.floor(sites.length/2));
        let right = sites.slice(Math.floor(sites.length/2), sites.length);
        sites = [...left, ...center, ...right];
    }
    center();
</script>


<nav>
    {#each sites as site (site)}
        <a animate:flip href={site.url}>{site.name}</a>
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
        width: 50%;
        margin: 0 auto;
        border-radius: 3rem;
        box-shadow: white 0px 0px 10px 0px;
    }

    nav a{
        text-decoration: none;
        color: #fff;
        padding: 0.5rem;
        border-radius: 2rem;
        font-size: 1.2rem;
    }

    
</style>