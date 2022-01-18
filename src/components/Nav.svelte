<script lang="ts">
  // Components
  import Menu from "./Menu.svelte"
  // Graphic Assets
  import Logo from "../assets/images/logo.svg"
  import HamburgerIcon from "../assets/images/icon-hamburger.svg"
</script>

<nav class="nav">
  <img src={Logo} alt="Monograph Dashboard Navbar Logo" class="nav__logo">
  <Menu />
  <img src={HamburgerIcon} alt="Menu Button" class="nav__hamburger">
</nav>

<style lang="scss">
  @use "../styles/variables";

  .nav {
    align-items: center;
    display: flex;
    justify-content: space-between;
    padding: variables.$spacing-l variables.$spacing-m 0 variables.$spacing-m;
    margin-bottom: variables.$spacing-xl;

    &__logo {
      width: 2.4rem;
    }
  }
</style>