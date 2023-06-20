<script>
    let sites = [
        {name: 'Home', url: '/'},
        {name: 'About', url: '/about'},
        {name: 'Contact', url: '/contact'}
    ]
    let page = sites.find(site => site.url === window.location.pathname);
    setInterval(() => {
        page = sites.find(site => site.url === window.location.pathname);
    }, 1000);

    // function to put active page in center

    function centeractivePage(){
        let len = sites.length;
        let mid = Math.floor(len/2);
        
    }
</script>


<nav>
    {#each sites as site}
        <a href={site.url}>{site.name}</a>
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