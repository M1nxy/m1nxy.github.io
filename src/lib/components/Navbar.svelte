<script lang="ts">
  import { base } from '$app/paths';
</script>

<div class="flex flex-row text-lg py-1 px-2 justify-between">
  <a href="/"><h1 class="font-bold">M1nxy</h1></a>
  <nav class=" flex gap-2">
    <!-- External site link -->
    <a href="/blog">Blog</a>
    <a href="{base}/projects">Projects</a>
    <a href="{base}/contact">Contact</a>
  </nav>
</div>

<style lang="scss">
  div {
    font-family:
      'wotfard',
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
</style>
