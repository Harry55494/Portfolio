
<script>

    export let parentCardClicked = () => {};

    function flip_card(event){
        parentCardClicked();
        const card = event.currentTarget;
        if (card.style.transform === "rotateY(180deg)"){
            card.style.transform = "rotateY(0deg)";
        }
        else{
            card.style.transform = "rotateY(180deg)";
        }
    }

</script>


<div id = "catan_card" class="container">
    <div class="card" on:click={flip_card}>
        <div class="front">
            <h2>Conquerors of Catan</h2>
        </div>
        <div class="back">
            <h4>Conquerors of Catan</h4>
            <p>Conquerors of Catan is my third year project for my CS degree, aimed at using the MiniMax algorithm to play Settlers, along with comparing various strategies. </p>
            <p><a href="https://github.com/Harry55494/Conquerors-of-Catan" target="_blank">Source Code (GitHub)</a></p>
        </div>
    </div>
</div>




<style>

    .container{
        width: 500px;
        height: 300px;
        transition: transform 500ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
        margin-top: 15px;
        margin-left: 20px;
        margin-right: 20px;
        padding: 15px;
    }

    :global(.card){
        width: 100%;
        height: 100%;
        border-radius: 20px;
        transform-style: preserve-3d;
        transition: all 0.5s ease;
        cursor: pointer;
    }


    .front{
        background-image: url("/static/Catan-Background.png");
        background-size: 100% 100%;
        background-position: center;
        background-repeat: no-repeat;
        overflow: hidden;
        border-radius: 20px;
        position: absolute;
        backface-visibility: hidden;
        width: 100%;
        height: 100%;
    }

    .back{
        background-size: 100% 100%;
        overflow: hidden;
        position: absolute;
        background: url("/static/Catan-Background-2.png") no-repeat center;
        background-size: cover;
        border-radius: 20px;
        backface-visibility: hidden;
        width: 100%;
        height: 100%;
        transform: rotateY(180deg);
        color: white;
    }

    .container:hover{
        transform: scale3d(1.1, 1.1, 1.1);
    }

    h2{
        position: absolute;
        top: 0;
        left: 0;
        font-family: 'Alkalami', serif;
        font-size: calc(min(20px + 6vw, 60px));
        color: white;
        text-align: center;
        margin-top: 100px;
        backdrop-filter: blur(5px);
    }

    h4, p{
        color: white;
        text-align: center;
    }

    h4{
        font-size: 45px;
        font-weight: 600;
        font-family: 'Alkalami', serif;
        margin-bottom: 25px;
        margin-top: 40px;
    }

    p{
        margin: 12px;
        font-size: calc(min(10px + 2vw, 20px));
        font-family: 'Alkalami', serif;
    }

    a {
        color: white;
    }

    @media (max-width: 600px){
        .container{
            width: 250px;
            height: 160px;
            margin-left: 0;
            margin-right: 0;
        }

    }


    @media (max-width: 700px){
        .container{
            width: 300px;
            height: 180px;
            margin-left: 0;
            margin-right: 0;
        }

    }

    @media (max-width: 768px){
        .container{
            width: 400px;
            height: 200px;
            margin-left: 0;
            margin-right: 0;
        }

        h2{
            margin-top: 60px;
        }

        h4{
            display: none;
        }

    }



</style>