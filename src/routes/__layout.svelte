<script lang="ts">
  import '../global.postcss'
  import { theme } from './store';
  import { onMount } from 'svelte';
  import MainNav from '$lib/Componenets/Navigation/MainNav.svelte';

  onMount(() => {
    if ($theme === 'dark') {
      document.querySelector('html').classList.add('dark')
    }
  })
</script>
<header>
  <MainNav></MainNav>
</header>
<main>
  <slot />
</main>
