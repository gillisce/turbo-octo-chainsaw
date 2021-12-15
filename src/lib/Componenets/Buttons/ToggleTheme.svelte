<script lang="ts">
  import { theme } from '../../../routes/store'
  import Switch from '$lib/Componenets/Buttons/Switch.svelte'

  const toggleTheme = () => {
    $theme = isLight ? 'light' : 'dark'

    document.querySelector('html').classList.toggle('dark')
  }
  let isLight = false;
</script>

<!-- <button on:click={toggleTheme} class="mx-2 text-gray-600 dark:text-gray-300 hover:text-gray-500 dark:hover:text-gray-300"> 
  <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24" fill="none"
    xmlns="http://www.w3.org/2000/svg">
    <path data-name="layer1"
    d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path>
  </svg>
</button> -->
<div class="flex justify-between mt-5">
  <Switch bind:checked="{isLight}" id="theme" text="Light Theme" on:change={toggleTheme} />
</div>