<script lang="ts">
  import { base } from '$app/paths';
  import Button from '$lib/components/Button.svelte';
</script>

<svelte:head>
  <title>M1nxy</title>
  <meta name="description" content="Basic demo site for github pages and sveltekit." />
</svelte:head>

<main class="flex flex-col-reverse m-auto text-justify w-full max-w-120 p-4 gap-8 md:(flex-row max-w-220 gap-4)">
  <div class="flex flex-col m-auto gap-1">
    <h1 class="flex font-boldtext-2xl gap-1 items-center">
      Hi I'm
      <span class="text-[#7F85FF]">M1nxy</span>
      <img src="{base}/assets/icons/gb.svg" alt="gb" />
    </h1>
    <p>
      I'm a full-stack developer from the uk. I'm a huge fan of functional programming and have experience with
      sveltekit and rust. You can find most of my work on github under the MIT licence. You can also checkout my
      projects <a href="{base}/projects">here</a>. I also have a <a href="{base}/blog">blog</a> where I talk about current
      projects and sidequests.
    </p>
  </div>
  <img src="{base}/assets/images/profile-christmas.webp" alt="yes" class="rounded-md m-auto w-65 md:w-75" />
</main>
