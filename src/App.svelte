<script lang="ts">
  // Components
  import Nav from "./components/Nav.svelte"
  import Hero from "./components/Hero.svelte"
</script>

<main class="container">
  <Nav />
  <Hero />
</main>

<style lang="scss" global>
  @use "./styles/variables";
  @import "./main";

  .container {
    overflow-x: hidden;
    padding-bottom: 5rem;
  }

  body::before {
    background-color: variables.$color-blue--light-grayish;
    border-bottom-left-radius: 6rem;
    content: "";
    height: 55vh;
    position: absolute;
    right: 0;
    top: 0;
    width: 45vw;
    z-index: -1;
  }
</style>
