<script lang="ts">
  export let isHidden: boolean

  if (window.innerWidth > 1440) isHidden = false
</script>

{#if !isHidden}
<ul class="menu">
  <li class="menu__item">
    <a href="/product" class="menu__link">Product</a>
  </li>
  <li class="menu__item">
    <a href="/product" class="menu__link">Features</a>
  </li>
  <li class="menu__item">
    <a href="/product" class="menu__link">Pricing</a>
  </li>
  <li class="menu__item">
    <a href="/product" class="menu__link">Login</a>
  </li>
</ul>
{/if}

<style lang="scss">
  @use "../styles/variables";
  @use "../styles/queries";

  .menu {
    background-color: #fff;
    box-shadow: 0 5px 10px rgba(0,0,0, .1);
    padding: variables.$spacing-ms;
    position: fixed;
    left: 50vw;
    text-align: center;
    transform: translate(-50%, -50%);
    top: calc((variables.$spacing-l * 2) + variables.$spacing-s + variables.$spacing-m + (variables.$spacing-ms * 3));
    width: calc(100vw - variables.$spacing-l - variables.$spacing-s);
    z-index: 2;

    @include queries.respond(desktop) {
      padding: unset;
      background-color: unset;
      box-shadow: unset;
      display: flex;
      left: unset;
      position: unset;
      transform: unset;
      top: unset;
      width: unset;
    }

    &__item {
      list-style: none;

      &:not(:last-child) {
        margin-bottom: variables.$spacing-ms;
        
        @include queries.respond(desktop) {
          margin-bottom: unset;

          &:not(:nth-child(3)) {
            margin-right: 4rem;
          }

          &:nth-child(3) {
            margin-right: 9rem;
          }
        }
      }

      &:last-child {
        border-top: 1px solid rgba(variables.$color-blue--very-dark, .15);
        padding-top: variables.$spacing-ms;

        @include queries.respond(desktop) {
          border-top: unset;
          padding-top: unset;
        }

        a {
          color: variables.$color-blue--grayish;
        }
      }
    }

    &__link {
      color: variables.$color-blue--very-dark;
      font-weight: 700;
      text-decoration: none;
      text-transform: uppercase;

      @include queries.respond(desktop) {
        &:hover { text-decoration: underline; }
      }
    }
  }
</style>