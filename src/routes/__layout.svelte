<script lang="ts">
  import '../global.postcss'
  import { theme } from './store'
  import { onMount } from 'svelte'
  import MainNav from 'src/components/navigation/MainNav.svelte'

  onMount(() => {
    if ($theme === 'dark') {
      document.querySelector('html').classList.add('dark')
    }
  })
</script>

<main>
  <MainNav></MainNav>
  <slot />
</main>
