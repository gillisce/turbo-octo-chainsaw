<script lang="ts">
  import { theme } from './store'
  import ToggleTheme from '$lib/ToggleTheme.svelte'
  import Counter from '$lib/Counter.svelte'
  import Timer from '$lib/Timer.svelte'
</script>

<svelte:head>
  <!-- Primary Meta Tags -->
  <title>Gillis | Web Development & Design</title>
  <meta name="title" content="Gillis | Web Development & Design" />
  <meta name="description" content="Chris Gillis | Web Development & Design portfolio, to show off work for future clients and employers" />
  <!-- <meta name="keywords" content="Svelte, SvelteKit, Svelte-kit, Tailwind, HTML, CSS, JavaScript" /> -->
  <meta name="author" content="@gillisce" />
</svelte:head>
<ToggleTheme />

<h1 class="text-5xl font-extrabold mb-2">Welcome to the personal and professional portfolio of Chris Gillis</h1>
<h2 class="text-3xl font-bold mb-4">Web Development & Design in Northeast Ohio</h2>
<blockquote class="text-xl p-2 bg-gray-200 dark:bg-gray-800 mb-2 transition-colors duration-500">
  <a href="https://github.com/gillisce"><b>Github repo</b></a>
</blockquote>


<style lang="postcss">
  p {
    @apply text-lg;
    @apply mt-0 mb-1;
  }
  code {
    @apply transition-colors duration-500;
    @apply px-1;
    @apply bg-gray-200;
    :global(.dark) & {
      @apply bg-gray-800;
    }
  }
  pre {
    @apply transition-colors duration-500;
    @apply text-left p-2 bg-gray-200;
    :global(.dark) & {
      @apply bg-gray-800;
    }
  }
</style>
