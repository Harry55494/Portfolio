
<script>
    export const last_updated = ' 10 Feb 2023'
</script>


<h2>What I'm currently working on</h2>
<p>
    Currently, I'm spending most of my time working on my third year final project at University, which is an AI for the board game <a href="https://en.wikipedia.org/wiki/Catan">Settlers of Catan</a>.
    This involves implementing different strategies for a range of AI players, and comparing which ones work the best. <br><br>
    Outside of University, I'm currently using <a href="https://kit.svelte.dev">SvelteKit</a> to rewrite my Start Page, and will then re-write this website to use SvelteKit instead of Svelte, to allow me to use multiple pages later on.<br><br>
    Finally, my JIE Investment Program (see <a href="#projects">Projects</a> below) is also undergoing a complete re-write from scratch, both changing the core functionality to trade different commodities/stocks, and also adding the use of new technologies such as Docker and Bucket Storage.
</p>
<p class="last_updated">Last Updated: {last_updated}</p>

<style>

    h2 {
        font-size:calc(min(10px + 3vw, 40px));
        font-weight: 500;
        text-align: center;
        letter-spacing: 2px;
        color: white;
        margin: 80px 20px 20px 20px;

    }

    a{
        text-decoration: underline;
        color: white;
    }

    p {
        margin-left:calc(min(-10px + 10vw, 150px));
        margin-right:calc(min(-10px + 10vw, 150px));
        font-size: calc(min(15px + 1vw, 22px));
        text-align: left;
        color: white;
        line-height: 1.5;
        font-weight: 300;
    }

    .last_updated {
        font-size: calc(min(8px + 2vw, 20px));
        color: #999;
        text-align: center;
        margin-bottom: 60px;
    }

</style>