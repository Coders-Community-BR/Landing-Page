<script>

    export const githubURL = "https://github.com/Coders-Community-BR"
    export let livrodjx = "../images/livrodjx.png"
    export let gaah = "../images/gaah.jpeg"
    export let coelho = "../images/coelho.jpeg"
    export let vczoika =  "../images/vczoika.jpeg"
    export let exatamente = "../images/exatamente.jpeg"
    export let pedrao = "../images/pedrao.jpeg"
    export let yxqsnz = "../images/yxqsnz.jpeg"
    export let kinash = "../images/kinash.png"
</script>

<div class="section-caption">
    <h1>Membros da Staff</h1>
</div>
<div class="team">
    <div class="team-profile">
        <img src={gaah} alt="">
        <h1>Gabriel Dias</h1>
    </div>

    <div class="team-profile">
        <img src={livrodjx} alt="">
        <h1>Livrodjx</h1>
    </div>

    <div class="team-profile">
        <img src={coelho} alt="">
        <h1>Gabriel Coelho</h1>
    </div>

    <div class="team-profile">
        <img src={vczoika} alt="">
        <h1>Vinicius Sales</h1>
    </div>

    <div class="team-profile">
        <img src={exatamente} alt="">
        <h1>Igor Pereira</h1>
    </div>

    <div class="team-profile">
        <img src={pedrao} alt="">
        <h1>Pedro Henrique</h1>
    </div>

    <div class="team-profile">
        <img src={yxqsnz} alt="">
        <h1>Yxqsnz</h1>
    </div>

    <div class="team-profile">
        <img src={kinash} alt="">
        <h1>Gabriel Kinash</h1>
    </div>
</div>

<style>
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
</style>