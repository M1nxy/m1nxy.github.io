<script lang="ts">
  import { base } from '$app/paths';

  type Project = { title: string; date: Date; desc: string; url: string };

  const projects: Array<Project> = [
    {
      title: 'Helios',
      date: new Date('2022-10'),
      desc: 'A multi-functional discord bot with scam checking and more!',
      url: 'https://github.com/m1nxy/helios'
    },
    {
      title: 'Selene',
      date: new Date('2022-10'),
      desc: 'A class based Command / Event handler for discord.js',
      url: 'https://github.com/m1nxy/Selene'
    },
    {
      title: 'Wallpaper Engine Preview (Linux)',
      date: new Date('2022-10'),
      desc: 'My first rust project enabling preview of wallpaper engine backgrounds via an interactive cli.',
      url: 'https://github.com/m1nxy/Selene'
    },
    {
      title: 'Consolify',
      date: new Date('2023-11'),
      desc: 'A WIP minecraft mod made with fabric that aims to replicate the console edition experience on java edition.',
      url: 'https://github.com/m1nxy/consolify'
    },
    {
      title: 'Blog',
      date: new Date('2023-11'),
      desc: 'A blog made using next and markdown. I use this to document side quests and projects listed here.',
      url: `${base}/blog`
    },
    {
      title: 'Libby',
      date: new Date('2023-09'),
      desc: 'A WIP comic/book/manga library manager and reader using rust and sql with sveltekit.',
      url: 'https://github.com/m1nxy/libby'
    },
    {
      title: 'Gib',
      date: new Date('2022-10'),
      desc: 'A toy nodejs project manager with license generation, dependency management and other QOL tools.',
      url: 'https://github.com/M1nxy/gib'
    },
    {
      title: 'ScamBeGone',
      date: new Date('2022-02'),
      desc: 'A multipurpose discord bot with scam avoidance and other moderation tools.',
      url: 'https://github.com/M1nxy/ScamBeGone'
    }
  ];
  const sortedProjects = projects.sort((a, b) => a.date.getTime() - b.date.getTime()).reverse();
</script>

<main class="container mx-auto m-2 w-full grid px-2 grid-rows-[auto_1fr] overflow-auto scroll-gutter justify-between">
  <h2 class="font-bold p-3 text-5xl">Projects</h2>
  <div class="flex flex-wrap h-[fit-content] p-2">
    {#each sortedProjects as project}
      <div class="w-auto p-1 grow basis-1/1 lg:basis-1/3">
        <div class="rounded-lg flex flex-col h-full bg-base-100 border-white/20 border-[1px] shadow-xl p-2">
          <h2 class="font-sm font-bold text-highlight">
            {project.date.toLocaleDateString('en-GB', { month: 'short', year: 'numeric' })}
          </h2>
          <h2 id="work" class="font-bold text-current text-2xl">{project.title}</h2>
          <p class="h-full">{project.desc}</p>
          <a href={project.url} target="_blank">Visit the project</a>
        </div>
      </div>
    {/each}
  </div>
</main>

<style lang="scss">
  .scroll-gutter {
    scroll-padding: auto;
  }
  img {
    @apply rounded-md;
  }
  *::-webkit-scrollbar {
    background-color: transparent;
    width: 15px;
  }
  *::-webkit-scrollbar-track {
    background-color: transparent;
  }
  *::-webkit-scrollbar-thumb {
    @apply bg-black/20;
    border-radius: 20px;
    border: 4px solid transparent;
    background-clip: content-box;
  }
  @media (prefers-color-scheme: dark) {
    *::-webkit-scrollbar-thumb {
      @apply bg-white/20;
    }
  }
</style>
