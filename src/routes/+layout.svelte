<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
</script>

<div
  class="h-screen bg-[#F9F8F8] grid ease-in-out grid-rows-[auto_1fr] transition-all-[250ms] overflow-hidden dark:(bg-[#080B0D] text-white)"
>
  <Navbar />
  <slot />
</div>

<style lang="scss">
  @font-face {
    font-family: 'wotfard';
    src: url('/assets/fonts/wotfard-regular-webfont.eot');
    src:
      url('/assets/fonts/wotfard-regular-webfont.eot?#iefix') format('embedded-opentype'),
      url('/assets/fonts/wotfard-regular-webfont.woff2') format('woff2'),
      url('/assets/fonts/wotfard-regular-webfont.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
  }
  div {
    font-family:
      ui-sans-serif,
      system-ui,
      -apple-system,
      BlinkMacSystemFont,
      'Segoe UI',
      Roboto,
      'Helvetica Neue',
      Arial,
      'Noto Sans',
      sans-serif,
      'Apple Color Emoji',
      'Segoe UI Emoji',
      'Segoe UI Symbol',
      'Noto Color Emoji';
  }

  :global(a) {
    text-decoration: underline;
    text-decoration-color: transparent;
    transition: all ease-in-out 200ms;
    @apply text-[#7F85FF];
    &:hover {
      text-decoration-color: currentColor;
      @apply text-[#9ca0ff];
    }
  }
</style>
