<script>
  import { onMount } from "svelte";
  import { scrollto } from "svelte-scrollto"

  onMount(async () => {
    const hamburger = document.querySelector(".hamburger");
    const myHeader = document.querySelector(".header");
    const navMenu = document.querySelector(".nav-menu");

    hamburger.addEventListener("click", mobileMenu);

    function mobileMenu() {
      hamburger.classList.toggle("active");
      navMenu.classList.toggle("active");
    }

    const navLink = document.querySelectorAll(".nav-link");

    navLink.forEach((n) => n.addEventListener("click", closeMenu));

    function closeMenu() {
      hamburger.classList.remove("active");
      navMenu.classList.remove("active");
    }

    window.onscroll = () => {
      window.scrollY > 500
        ? myHeader.classList.add("sticky")
        : myHeader.classList.remove("sticky");
    };
  });

  export let logo = "../images/logo.png";
</script>

<header class="header">
  <nav class="navbar">
    <a href="/" class="nav-logo">
      <img src={logo} class="logo-image" alt="" />
    </a>
    <ul class="nav-menu">

      <li class="nav-item">
        <a use:scrollto={'#about'} href="/" class="nav-link">Sobre</a>
      </li>

      <li class="nav-item">
        <a use:scrollto={'#staff'} href="/" class="nav-link">Staff</a>
      </li>

      <li class="nav-item">
        <a
          href="https://github.com/Coders-Community-BR"
          target="_blank"
          class="nav-link"
          rel="noreferrer"
          style="color: #fff; font-size: 30px;cursor: 'pointer'
          ; display: inline-flex; align-items: center;
          padding-right: 100px;"
        >
          <i class="fab fa-github" />
          <p style="font-size: 16px !important; margin-left: 20px;">Github</p>
        </a>
      </li>
    </ul>
    <div class="hamburger">
      <span class="bar" />
      <span class="bar" />
      <span class="bar" />
    </div>
  </nav>
</header>

<style>
  @keyframes fade {
    from {
      opacity: 0;
      transform: scale(0.9);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }
  .header {
    z-index: 10;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 0 50px;
  }

  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  :global(.header.sticky) {
    display: none;
    border-bottom: 1px solid #023a8d0a;
    padding: 20px 50px;
    margin: 0;
    padding-top: 0;
    height: 120px;
    color: #fff !important;
    background-color: transparent;
    z-index: 999;
  }

  .logo-image {
    width: 150px;
    height: 150px;
  }
  .hamburger {
    display: none;
  }

  .bar {
    display: block;
    width: 25px;
    height: 3px;
    margin: 5px auto;
    -webkit-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
    background-color: whitesmoke;
  }
  .nav-menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-item {
    margin-left: 5rem;
  }

  .nav-link {
    height: 2.3rem;
    width: 2.3rem;
    font-size: 1.2rem;
    font-weight: 500;
    color: #fff;
  }

  .nav-link:hover {
    color: #ddd;
  }

  .nav-logo {
    font-size: 2.1rem;
    font-weight: 500;
    color: #fff;
  }
  @media only screen and (max-width: 768px) {
    .nav-menu {
      position: fixed;
      left: -100%;
      top: 0;
      flex-direction: column;
      justify-content: center !important;
      background-color: #222;
      color: #222 !important;
      width: 100%;
      min-height: 100vh;
      text-align: center;
      transition: 0.3s;
      box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
    }

    :global(.nav-menu.active) {
      left: 0;
    }

    .nav-item {
      margin: 2rem 0;
      color: #222 !important;
    }

    .hamburger {
      display: block;
      z-index: 15;
      cursor: pointer;
    }

    :globa(.hamburger.active .bar:nth-child(2)) {
      opacity: 0;
    }

    :globa(.hamburger.active .bar:nth-child(1)) {
      transform: translateY(8px) rotate(45deg);
    }

    :global(.hamburger.active .bar:nth-child(3)) {
      transform: translateY(-8px) rotate(-45deg);
    }
  }
</style>
