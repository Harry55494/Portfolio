
<script>

    import StartPage_ProjectCard from "./ProjectCards/StartPage_ProjectCard.svelte";
    import JeffersonIE_ProjectCard from "./ProjectCards/JeffersonIE_ProjectCard.svelte";
    import Portfolio_ProjectCard from "./ProjectCards/Portfolio_ProjectCard.svelte";
    import Catan_ProjectCard from "./ProjectCards/Catan_ProjectCard.svelte";
    import Galahad_ProjectCard from "./ProjectCards/Galahad_ProjectCard.svelte";

    function isInViewport(element){
        /**
         * Helper function to check if an element is on screen
         * Taken from https://www.javascripttutorial.net/dom/css/check-if-an-element-is-visible-in-the-viewport/
         * @type {DOMRect}
         */
        const rect = element.getBoundingClientRect()
        return (
            rect.top >= 0 &&
            rect.left >= 0 &&
            rect.bottom <= (window.innerHeight || document.document.clientHeight) &&
            rect.right <= (window.innerWidth || document.document.clientWidth)
        )
    }

    let card_clicked = false;
    let timer;
    let timerRunning;

    function checkForProjectClickTooltip(){

        if (card_clicked){
            clearTimeout(timer)
            return;
        }

        if (isInViewport(document.getElementById('start_page_card')) ||
            isInViewport(document.getElementById('portfolio_card')) ||
            isInViewport(document.getElementById('jie_card')) ||
            isInViewport(document.getElementById('catan_card'))
        ){

            if (!timerRunning && !card_clicked){
                timerRunning = true
                timer = setTimeout(() => {
                    document.getElementById('project_card_tooltip').style.opacity = '1';
                }, 4000)
            }

        } else {
            clearTimeout(timer)
            timerRunning = false
            console.log('Timer Cancelled')
        }
    }

    document.addEventListener('scroll', checkForProjectClickTooltip)

</script>


<div class="container" id="projects">
    <h1>Projects</h1>

    <p class="regular_text">These are some of my projects. <br>
        They are all in various stages of completion, as I work on them around my University schedule.<br><br>
        Click on a card to find out more!

    </p>

    <div class = "card_container">
        <Catan_ProjectCard parentCardClicked={()=>{card_clicked = true; checkForProjectClickTooltip()}}/>
        <Galahad_ProjectCard parentCardClicked={()=>{card_clicked = true; checkForProjectClickTooltip()}}/>
        <Portfolio_ProjectCard parentCardClicked={()=>{card_clicked = true; checkForProjectClickTooltip()}}/>
        <!-- <JeffersonIE_ProjectCard parentCardClicked={()=>{card_clicked = true; checkForProjectClickTooltip()}}/> -->
        <!-- <StartPage_ProjectCard parentCardClicked={()=>{card_clicked = true; checkForProjectClickTooltip()}}/> -->

    </div>

</div>




<style>
    .container{
        margin: 2vh 4vw 4vw 4vw;
        color: white;
        line-height: 1.1;
    }

    h1 {
        font-size: calc(min(25px + 8vw, 80px));
        font-weight: 600;
        text-align: center;
        letter-spacing: 2px;
    }

    .card_container{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
    }

    :global(#project_card_tooltip){
        opacity: 0;
        transition: opacity 2s;
    }

</style>