<script lang="ts">
  import AboutMe from '$lib/Componenets/Elements/BioSection.svelte'
  import CurrentRoles from '$lib/Componenets/Elements/CurrentRoles.svelte';
  import { theme } from './store'
</script>

<svelte:head>
  <!-- Primary Meta Tags -->
  <title>Gillis | Web Development & Design</title>
  <meta name="title" content="Gillis | Web Development & Design" />
  <meta name="description" content="Chris Gillis | Web Development & Design portfolio, to show off work for future clients and employers" />
  <!-- <meta name="keywords" content="Svelte, SvelteKit, Svelte-kit, Tailwind, HTML, CSS, JavaScript" /> -->
  <meta name="author" content="@gillisce" />
</svelte:head>

<div class=" flex-col spay-y-4 grid  grid-flow-row auto-rows-max">
  <div>  <AboutMe></AboutMe> </div>
  <hr class="bg-green-600  dark:bg-green-400">
  <div>   <CurrentRoles></CurrentRoles> </div>
</div>
