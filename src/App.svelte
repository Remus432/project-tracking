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
  @use "./main" as *;
  @use "./styles/queries";
  @use "./styles/variables";

  .container {
    overflow-x: hidden;
    padding-bottom: 5rem;
    
    @include queries.respond(desktop) {
      padding-left: 16.5rem;
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
