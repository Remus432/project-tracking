<script lang="ts">
  export let state: string
  export let content: string
  export let icon: string
</script>

<button class="btn btn--{state}">
  {content}
  {#if icon}
    <img src={icon} alt="Right Arrow Icon" />
  {/if}
</button>

<style lang="scss">
  @use "../styles/variables";
  @use "../styles/queries";

  .btn {
    border: none;
    cursor: pointer;
    font-size: variables.$fsize-s;
    text-transform: uppercase;

    @include queries.respond(desktop) {
      font-size: variables.$fsize-m;
    }

    &--primary {
      background-color: variables.$color-red;
      border-radius: 5px;
      color: #fff;
      font-weight: 700;
      padding: .8rem 2.4rem;
      position: relative;
      letter-spacing: .9px;
      transition-property: background-color, transform;
      transition: all .5s ease;
      top: 0;

      &::before {
        box-shadow: 0 5px 10px rgba(0, 0, 0, .1);
        bottom: 0;
        content: "";
        height: 100%;
        position: absolute;
        opacity: 0;
        left: 0;
        transition: opacity .5s ease;
        width: 100%;
        z-index: -1;
      }

      &:hover {
        background-color: lighten(variables.$color-red, 8%);
        top: -5px;
      }

      &:hover::before {
        opacity: 1;
      }
    }

    &--secondary {
      align-items: center;
      background-color: unset;
      color: rgba(variables.$color-blue--very-dark, .5);
      display: flex;
      padding-left: 1.5rem;
      letter-spacing: 2.5px;

      & img {
        transition: transform .5s ease;
      }

      &:hover img {
        transform: translateX(5px);
      }
    }
  }
</style>