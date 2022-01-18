<script lang="ts">
  // Components
  import Button from "./Button.svelte"
  // Graphic Assets
  import DevicesIllustration from "../assets/images/illustration-devices.svg"
</script>

<section class="hero">
  <img src={DevicesIllustration} alt="" class="hero__illustration">
  <article class="hero__content">
    <p class="hero__product-name">
      <span>New</span>
      <span>Monograph Dashboard</span>
    </p>
    <h1 class="hero__product-headline">Powerful Insights Into Your Team</h1>
    <h2 class="hero__product-subheadline">Project planning and time tracking for agile teams</h2>
    <div class="hero__cta">
      <Button state="primary" content="Schedule a demo" />
      <Button state="secondary" content="To see a preview" />
    </div>
  </article>
</section>

<style lang="scss">
  @use "../styles/variables";

  .hero {
    padding-left: variables.$spacing-m;

    &__illustration {
      transform: scale(clamp(1.2, 1.1, 1.3)) translateX(4vw);
    }

    &__content {
      margin-top: 10rem;
    }

    &__product-name {
      text-transform: uppercase;

      & > span:first-child {
        background-color: variables.$color-blue--very-dark;
        border-radius: 1.6rem;
        color: #fff;
        font-weight: 700;
        padding: .4rem 1rem .5rem 1rem;
        margin-right: variables.$spacing-xs;
      }

      & > span:last-child {
        color: rgba(variables.$color-blue--very-dark, .5);
        font-size: variables.$fsize-s;
        letter-spacing: .5rem;
      }
    }

    &__product-headline {
      color: variables.$color-blue--very-dark;
      font-size: variables.$fsize-xl;
      padding-right: variables.$spacing-m;
      margin-top: variables.$spacing-xs;
      line-height: 4rem;
    }

    &__product-subheadline {
      color: rgba(variables.$color-blue--very-dark, .75);
      font-family: "Barlow", sans-serif;
      font-weight: 400;
      font-size: variables.$fsize-l;
      margin-top: variables.$spacing-xs;
      line-height: 2.6rem;
      width: 85%;
    }

    &__cta {
      margin-top: variables.$spacing-s;
    }
  }
</style>