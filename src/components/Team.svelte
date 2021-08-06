<script>
    export let livrodjx = "../images/livrodjx.png"
    export let gaah = "../images/gaah.jpeg"
    export let coelho = "../images/coelho.jpeg"
    export let vczoika =  "../images/vczoika.jpeg"
    export let exatamente = "../images/exatamente.jpeg"
    export let pedrao = "../images/pedrao.jpeg"
    export let yxqsnz = "../images/yxqsnz.jpeg"
    export let kinash = "../images/kinash.png"
</script>

<div class="section-caption" id="staff">
    <h1>Membros da Staff</h1>
    
</div>
<div class="team">
    <div id="particles-js"></div>
    <div class="team-profile">
        <img src={gaah} alt="">
        <h1>Gabriel Dias</h1>
        <p>Dono</p>
    </div>

    <div class="team-profile">
        <img src={livrodjx} alt="">
        <h1>Livrodjx</h1>
        <p>Administrador</p>
    </div>

    <div class="team-profile">
        <img src={coelho} alt="">
        <h1>Gabriel Coelho</h1>
        <p>Administrador</p>
    </div>

    <div class="team-profile">
        <img src={vczoika} alt="">
        <h1>Vinicius Sales</h1>
        <p>Administrador</p>
    </div>

    <div class="team-profile">
        <img src={exatamente} alt="">
        <h1>Igor Pereira</h1>
        <p>Moderador</p>
    </div>

    <div class="team-profile">
        <img src={pedrao} alt="">
        <h1>Pedro Henrique</h1>
        <p>Moderador</p>
    </div>

    <div class="team-profile">
        <img src={yxqsnz} alt="">
        <h1>Yxqsnz</h1>
        <p>Supervisor</p>
    </div>

    <div class="team-profile">
        <img src={kinash} alt="">
        <h1>Gabriel Kinash</h1>
        <p>Supervisor</p>
    </div>
</div>

<style>
    #particles-js {
        z-index: 3;
        position: absolute;
        height: 700px;
        background-color: #222;
    }
    div.section-caption {
        display: flex;
        width: 100%;
        height: auto;
        background-color: #222;
        color: #fff;
        align-items: center;
        justify-content: center;
        padding-bottom: 70px;
    }
    div.section-caption h1 {
        font-size: 2.7rem;
    }

    div.team {
        z-index: 4;
        width: 100%;
        height: auto;
        background-color: #222;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        padding-bottom: 100px;
    }

    div.team-profile {
        z-index: 4;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 20px 80px;
    }

    div.team-profile img {
        width: 175px;
        height: 175px;
        border-radius: 50%;
    }

    div.team-profile h1 {
        color: whitesmoke;
        margin: 10px 0;
        font-size: 1.3rem !important;
    }
    div.team-profile p {
        color: whitesmoke;
        margin: 0px 0;
      
    }

    @media (max-width: 600px) {

        #particles-js {
            height: 2500px;
            background-color: #222;
        }
    }

    @media (max-width: 370px) {
        .section-caption h1 {
            text-align: center;
        }
    }
</style>