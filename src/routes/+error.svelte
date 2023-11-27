<script lang="ts">
  import { base } from '$app/paths';
  import { page } from '$app/stores';
  import Navbar from '$lib/components/Navbar.svelte';

  function setTheme() {
    const elemHtmlClasses = document.documentElement.classList;
    const mql = window.matchMedia('(prefers-color-scheme: dark)');

    elemHtmlClasses.toggle('dark', mql.matches);
    elemHtmlClasses.toggle('light', !mql.matches);

    mql.onchange = () => {
      elemHtmlClasses.toggle('dark', mql.matches);
      elemHtmlClasses.toggle('light', !mql.matches);
    };
  }
</script>

<svelte:head>
  <!-- Workaround for a svelte parsing error: https://github.com/sveltejs/eslint-plugin-svelte/issues/492 -->
  {@html `<\u{73}cript nonce="%sveltekit.nonce%">(${setTheme.toString()})();</script>`}
  <title>
    {$page.status} - {$page.error ? $page.error.message : 'Not Found!'}
  </title>
</svelte:head>

<main>
  <div class="error">
    <span class="status">{$page.status}</span>
    <div class="message">
      <h1>{$page.error ? $page.error.message : 'Not Found!'}</h1>
    </div>
  </div>
  <a href="{base}/">Return Home!</a>
</main>

<style>
  main {
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .error {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 1rem;
  }
  .status {
    font-weight: 200;
    font-size: 3rem;
    line-height: 1;
    position: relative;
    top: -0.05rem;
  }
  .message {
    border-left: 1px solid #ccc;
    padding: 0 0 0 1rem;
    margin: 0 0 0 1rem;
    min-height: 2.5rem;
    display: flex;
    align-items: center;
  }
  .message > h1 {
    font-weight: 400;
    font-size: 1em;
    margin: 0;
  }
  a {
    transition: text-decoration 100ms ease-in-out;
    text-decoration: underline;
    text-decoration-color: transparent;
  }
  a:hover {
    text-decoration-color: currentColor;
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
    @apply text-black/80;
    &:hover {
      @apply text-black;
      text-decoration-color: currentColor;
    }

    @media (prefers-color-scheme: dark) {
      @apply text-white/80;
      &:hover {
        @apply text-white;
      }
    }
  }
</style>
