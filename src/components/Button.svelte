<script lang="ts">
  export let state: string
  export let content: string
</script>

<button class="btn btn--{state}">{content}</button>

<style lang="scss">
  @use "../styles/variables";

  .btn {
    border: none;
    font-size: variables.$fsize-s;
    text-transform: uppercase;

    &--primary {
      background-color: variables.$color-red;
      border-radius: 5px;
      color: #fff;
      font-weight: 700;
      padding: .8rem 2.4rem;
      letter-spacing: .9px;
    }

    &--secondary {
      background-color: unset;
      color: rgba(variables.$color-blue--very-dark, .5);
      padding-left: 1.5rem;
      letter-spacing: 2.5px;
    }
  }
</style>