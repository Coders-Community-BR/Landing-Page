<script>
  import { onMount } from "svelte";

  onMount(async () => {
    const colors = ["#fff", "#ddd", "#ccc"];
    const animationBox = document.querySelector(".balls-animation");
    
    const numBalls = 100;
    const balls = [];

    for (let i = 0; i < numBalls; i++) {
      let ball = document.createElement("div");
      ball.classList.add("ball");
      ball.style.background = colors[Math.floor(Math.random() * colors.length)];
      ball.style.zIndex = 5;
      ball.style.left = `${Math.floor(Math.random() * 100)}vw`;
      ball.style.top = `${Math.floor(Math.random() * 100)}vh`;
      ball.style.transform = `scale(${Math.random()})`;
      ball.style.width = `${Math.random()}em`;
      ball.style.height = ball.style.width;

      balls.push(ball);
      animationBox.append(ball);
      
    }

    // Keyframes
    balls.forEach((el, i, ra) => {
      let to = {
        x: Math.random() * (i % 2 === 0 ? -11 : 11),
        y: Math.random() * 12,
      };

      let anim = el.animate(
        [
          { transform: "translate(0, 0)" },
          { transform: `translate(${to.x}rem, ${to.y}rem)` },
        ],
        {
          duration: (Math.random() + 1) * 2000, // random duration
          direction: "alternate",
          fill: "both",
          iterations: Infinity,
          easing: "ease-in-out",
        }
      );
    });

    const target = document.querySelectorAll("[data-anime]");
    const animationClass = "animate";

    function animeScroll() {
      const windowTop = window.pageYOffset + (window.innerHeight * 3) / 4;

      target.forEach((elem) => {
        if (windowTop > 1200) {
          elem.classList.add(animationClass);
        } else {
          elem.classList.remove(animationClass);
        }
      });
    }

    window.addEventListener("scroll", () => animeScroll());
  });

  export let image1 = "../images/discord.png";
  export let image2 = "../images/discord2.png";
  export let image3 = "../images/discord3.png";
  export let image4 = "../images/discord4.png";
</script>

<div class="about">
  <div class="balls-animation" />

  <div class="about-content" data-anime="left">
    <h1 style="color: #fff">Conheça nosso servidor</h1>

    <p>
      A Coders Community é um servidor no Discord com foco na área de
      programação e suas tecnologias, o mesmo foi criado dia 09/04/2021 com o
      intuito de compartilharmos conhecimentos, esclarecermos dúvidas e nos
      divertir e já contamos com mais de 1000 membros, faça você parte dessa
      comunidade incrível.
    </p>
  </div>

  <div class="images-collections">
    <div class="collection1">
      <div class="image-content">
        <img src={image1} alt="Imagem de divulgação" />
      </div>

      <div class="description">
        <h1>Compartilhe seus wallpapers</h1>

        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essen
        </p>
      </div>
    </div>

    <div class="collection2">
      <div class="description2">
        <h1>Tire suas dúvidas</h1>

        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essen
        </p>
      </div>
      <div class="image-content2">
        <img src={image2} alt="Imagem de divulgação" />
      </div>
    </div>

    <div class="collection3">
      <div class="image-content3">
        <img src={image3} alt="" />
      </div>
      <div class="description3">
        <h1>Bata um papo com outros programadores</h1>
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essen
        </p>
      </div>
    </div>

    <div class="collection4">
      <div class="description4">
        <h1>Estude conosco</h1>
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essen
        </p>
      </div>

      <div class="image-content4">
        <img src={image4} alt="" />
      </div>
    </div>
  </div>
</div>

<style>
  .about {
    position: relative;
    background-color: #222;
    width: 100%;
    height: auto;
    min-height: 2200px;
  }
  .balls-animation {
    height: auto;
    padding-top: 50px;
  }
  :global(.ball) {
    position: absolute;
    border-radius: 100%;
    top: 50%;
    opacity: 0.1;
  }

  .about-content {
    position: relative;
    height: auto;
    padding-top: 150px;
    width: 100%;
    z-index: 55;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }

  .about-content h1 {
    color: #fff;
    font-size: 2.7rem;
    margin-bottom: 30px;
  }
  .about-content p {
    color: #fff;
    width: 700px;
    font-size: 1.2rem;
    font-weight: 400;
    margin-bottom: 200px;
    text-align: center;
  }

  .images-collections {
    padding: 0 40px;
  }
  .images-collections img {
    width: 650px;
    height: 350px;
  }
  [data-anime] {
    opacity: 0;
    transition: 0.3s;
  }

  [data-anime="left"] {
    transform: translate3d(0px, 0, 0);
    animation-duration: 5s;
  }

  :global([data-anime="right"]) {
    transform: translate3d(50px, 0, 0);
  }

  :global([data-anime].animate) {
    transform: translate3d(0, 0px, 0px);
    opacity: 1 !important;
  }

  div.collection1 {
    display: grid;
    width: 100%;
    min-height: 600px;
    height: auto;
    grid-template-columns: 400px 1fr;
    grid-template-areas: "image-content description";
  }

  div.image-content {
    grid-area: image-content;
    position: relative;
  }

  div.description {
    grid-area: description;
    margin-left: 200px;
    padding-left: 70px;
    color: #fff;
  }

  div.description h1 {
    margin-bottom: 20px;
  }

  div.collection2 {
    display: grid;
    width: 100%;
    min-height: 600px;
    height: auto;
    padding: 0px 40px 0px 0px;
    grid-template-columns: 1fr 650px;
    grid-template-areas: "description2 image-content2";
  }

  div.description2 {
    grid-area: description2;
    width: 500px;
    color: #fff;
  }

  div.description2 h1 {
    margin-bottom: 20px;
  }

  div.image-content2 {
    grid-area: image-content2;
  }

  div.collection3 {
    display: grid;
    width: 100%;
    min-height: 600px;
    padding: 0px 40px;
    grid-template-columns: 700px 1fr;
    grid-template-areas: "image-content3 description3";
  }

  div.image-content3 {
    grid-area: image-content3;
  }

  div.description3 {
    grid-area: description3;
    color: #fff;
  }

  div.description3 h1 {
    margin-bottom: 20px;
  }

  div.collection4 {
    display: grid;
    width: 100%;
    min-height: 600px;
    padding: 0px 40px;
    grid-template-columns: 1fr 650px;
    grid-template-areas: "description4 image-content4";
  }

  div.description4 {
    grid-area: description4;
    color: #fff;
  }

  div.description4 h1 {
    margin-bottom: 20px;
  }
  
  div.image-content4 {
    grid-area: image-content4;
  }
</style>
