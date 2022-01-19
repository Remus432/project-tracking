<script lang="ts">
  // Third Party
  import { gsap } from "gsap"
  // Core
  import { onMount } from "svelte"
  // Components
  import Nav from "./components/Nav.svelte"
  import Hero from "./components/Hero.svelte"


  onMount(() => {
    const tl = gsap.timeline({ default: { duration: 1, ease: "power3.easeOut" }})

    tl
    .from(".first-shape", {
      scale: 0,
      opacity: 0,
      transformOrigin: "center"
    })
    .from(".third-shape", {
      scale: 0,
      opacity: 0,
      trasformOrigin: "center"
    })
    .from(".second-shape", {
      scale: 0,
      opacity: 0,
      transformOrigin: "center"
    })
    .from(".intro__text", {
      x: -150,
      opacity: 0,
      ease: "power3.easeInOut"
    })
    .to(".intro", {
      "clip-path": "polygon(0% 100%, 100% 100%, 100% 100%, 0% 100%)",
      delay: 1,
    })
    .eventCallback("onComplete", () => document.body.style.overflowY = "unset")

  })
</script>

<main class="container">
  <div class="intro">
    <svg class="intro__icon" width="137" height="137" viewBox="0 0 137 137" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path class="first-shape" d="M136.895 0H0V136.895L136.895 0Z" fill="#2E2C2C"/>
      <path class="second-shape" d="M136 12L76.5 71.5L136 131V12Z" fill="#2E2C2C"/>
      <path class="third-shape" d="M131 137L70 76L8.99997 137H131Z" fill="#2E2C2C"/>
    </svg>    
    <p class="intro__text">
      <span>Monograph</span> 
      <span>Dashboard</span>
    </p>
  </div>
  <Nav />
  <Hero />
</main>

<style lang="scss" global>
  @use "./main" as *;
  @use "./styles/queries";
  @use "./styles/variables";

  body { overflow-y: hidden; }

  .container {
    overflow-x: hidden;
    padding-bottom: 5rem;
    
    @include queries.respond(desktop) {
      padding-left: 16.5rem;
    }
  }

  .intro {
      align-items: center;
      background-color: variables.$color-red;
      clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%);
      display: flex;
      min-height: 100vh;
      justify-content: center;
      left: 0;
      position: absolute;
      top: 0;
      width: 100%;
      z-index: 3;

      &__icon {
        position: relative;
        margin-right: variables.$spacing-l;
        z-index: 2;
      }

      &__text {
        display: flex;
        flex-direction: column;
        
        span {
          color: #fff;
          font-size: variables.$fsize-xl;
          font-weight: 500;
        }
      }
    
  }

  body::before {
    background-color: variables.$color-blue--light-grayish;
    border-bottom-left-radius: 6rem;
    content: "";
    min-height: 50vh;
    max-height: 55vh;
    position: absolute;
    right: 0;
    top: 0;
    width: 45vw;
    z-index: -1;
  }
</style>
