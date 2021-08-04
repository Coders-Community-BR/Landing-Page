<script>
  import Header from "./components/Header.svelte";
  import About from './components/About.svelte'
  import Team from './components/Team.svelte'
  import Footer from "./components/Footer.svelte";
  import { scrollto } from "svelte-scrollto"
  
  export let count = 1;
  export function handleClick() {
    count += 1;
  }
</script>

<main>
  <Header />
  <div class="animation-area" id="bg">
    <ul class="box-area">
      <li />
      <li />
      <li />
      <li />
      <li />
      <li />
    </ul>

    <div class="banner-text">
      <h2>Coders Community</h2>
      <p>O melhor servidor de programação !</p>

      <a class="know-more" href="/" use:scrollto={'#about'}>Conhecer</a>
      <div class="social-media">
        <a
          href="https://discord.gg/CodersCommunity"
          target="_blank"
          rel="noreferrer"
          style="color: #fff; font-size: 50px;cursor: 'pointer'"
        >
          <i class="fab fa-discord" />
        </a>
      </div>
    </div>
  </div>
  <About />
  <Team />
  <Footer />
</main>

<style>
  @keyframes animate {
    0% {
      transform: translateY(0) rotate(0deg);
      opacity: 1;
    }
    100% {
      transform: translateY(-800px) rotate(360deg);
      opacity: 0;
    }
  }

  main {
    position: relative;
    width: 100%;
    height: auto;
    min-height: 2000px;
  }

  #bg {
    background: url("../images/bg.png") repeat fixed 100%;
    width: 100%;
    height: 100vh;
    /*min-height: 2000px;*/
    position: relative;
  }

  .box-area {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }
  .box-area li {
    position: absolute;
    display: block;
    list-style: none;
    width: 25px;
    height: 25px;
    background: whitesmoke;
    animation: animate 20s linear infinite;
    bottom: -150px;
  }
  .box-area li:nth-child(1) {
    left: 86%;
    width: 80px;
    height: 80px;
    animation-delay: 0s;
  }
  .box-area li:nth-child(2) {
    left: 12%;
    width: 30px;
    height: 30px;
    animation-delay: 1.5s;
    animation-duration: 10s;
  }
  .box-area li:nth-child(3) {
    left: 70%;
    width: 100px;
    height: 100px;
    animation-delay: 5.5s;
  }
  .box-area li:nth-child(4) {
    left: 42%;
    width: 150px;
    height: 150px;
    animation-delay: 0s;
    animation-duration: 15s;
  }
  .box-area li:nth-child(5) {
    left: 65%;
    width: 40px;
    height: 40px;
    animation-delay: 0s;
  }
  .box-area li:nth-child(6) {
    left: 15%;
    width: 110px;
    height: 110px;
    animation-delay: 3.5s;
  }

  .banner-text {
    width: 100%;
    position: absolute;
    z-index: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }
  .banner-text h2 {
    text-align: center;
    color: #fff;
    font-size: 70px;
    margin-top: 15%;
  }
  .banner-text p {
    text-align: center;
    color: #fff;
    font-size: 20px;
    margin-top: 10px;
  }
  .banner-text .know-more {
    margin: 20px 0;
    padding: 16px 40px;
    background: whitesmoke;
    text-decoration: none;
    color: #333;
    border-radius: 3px;
  }
  .banner-text .know-more:hover {
    background-color: #c6c6c6;
    transition: 0.5s;
  }
</style>
