<script lang="ts">
  // Components
  import Menu from "./Menu.svelte"
  // Graphic Assets
  import Logo from "../assets/images/logo.svg"
  import HamburgerIcon from "../assets/images/icon-hamburger.svg"
  import CloseMenuIcon from "../assets/images/icon-close.svg"

  $: isHidden = true

  const toggleMenu = e => { isHidden = !isHidden }
</script>

<nav class="nav">
  <img src={Logo} alt="Monograph Dashboard Navbar Logo" class="nav__logo">
  <Menu isHidden={isHidden}  />
  <img on:click={toggleMenu} src={isHidden ? HamburgerIcon : CloseMenuIcon} alt="Menu Button" class="nav__hamburger">
</nav>

<style lang="scss">
  @use "../styles/variables";
  @use "../styles/queries";

  .nav {
    align-items: center;
    display: flex;
    justify-content: space-between;
    padding: variables.$spacing-l variables.$spacing-m 0 variables.$spacing-m;
    margin-bottom: variables.$spacing-xl;

    @include queries.respond(desktop) {
      padding: variables.$spacing-xl 16.5rem 0 0;
    }

    &__logo {
      width: 2.4rem;
    }

    &__hamburger {
      @include queries.respond(desktop) { display: none; }
    }
  }
</style>