<script lang="ts">
  import { base } from '$app/paths';
  import Button from '$lib/components/Button.svelte';
</script>

<svelte:head>
  <title>M1nxy</title>
  <meta name="description" content="Basic demo site for github pages and sveltekit." />
</svelte:head>

<main class="m-auto w-full max-w-180 grid gap-4 grid-cols-2 lg:max-w-280">
  <div class="flex flex-col m-auto gap-1">
    <h1 class="flex font-boldtext-2xl gap-1 items-center">
      Hi I'm
      <span class="text-[#7F85FF]">M1nxy</span>
      <img src="{base}/assets/icons/gb.svg" alt="gb" class="mt-1" />
    </h1>
    <p>
      I'm a full-stack developer from the uk. I'm a huge fan of functional programming and have experience with
      sveltekit and rust. You can find most of my work on github under the MIT licence. You can also checkout my
      projects <a href="{base}/projects">here</a>. I also have a blog where I talk about current projects and sidequests
    </p>
    <div>
      <Button class="bg-[#7F85FF] text-black">Button</Button>
    </div>
  </div>
  <img src="https://picsum.photos/400/400" alt="yes" class="m-auto" />
</main>
