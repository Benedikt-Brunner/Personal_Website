<script>
    import Naruto from "$lib/naruto.jpg"
    import Mathe from "$lib/Mathe.jpg"
    import Sketch from "$lib/ske.png"
    import SP from "$lib/SP.png"
</script>


<div class="cards">
<div class="card">
    <span>Education</span>
    <img src={Naruto} alt="naruto"></div>
<div class="card">
    <span>Chess</span>
    <img src={Mathe} alt="Mathe"></div>
<div class="card">
    <span>Biking</span>
    <img src={Sketch} alt="Sketch"></div>
<div class="card">
    <span>Finance</span>
    <img src={SP} alt="SP"></div>
</div>


<style>
.cards{
display: grid;
grid-template-columns: 1fr 1fr;
grid-template-rows: 1fr 1fr;
gap: 15%;
width: fit-content;    
height: fit-content;
align-content: start;
justify-content: center;
margin-top: 10%;
}


img{
    width: 0%;
    height: 0%;
    border-radius: 50px;
    transition: 1s;
}

.card:hover >img{
    transition: 1s;
width: 100%;
height: 100%;
}

.card:hover >span{
    font-size: larger;
    text-decoration: underline;
    transition: 1s ;
    margin-bottom: 5%;
}

.card:hover{
    background-color: transparent;
    transition: 1s;
}

.card{
    object-fit: cover;
    width: 15vw;
    height: 40vh;
    background-color: black;
    border-radius: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

span{
    color: white;
}
</style>