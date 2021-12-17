<script lang="ts">
  import { theme } from '../../../routes/store'
  import Switch from '$lib/Componenets/Buttons/Switch.svelte'

  function toggleTheme (){
    $theme = checked ? 'dark' : 'light'

    document.querySelector('html').classList.toggle('dark')
  }
  let checked = true;
  let moon = "M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
</script>
<style>
  .switch {
    @apply relative inline-block align-middle cursor-pointer select-none bg-transparent;
  }

  .track {
    @apply w-12 h-6 bg-gray-600 rounded-full shadow-inner;
  }

  .thumb {
    @apply transition-all duration-300 ease-in-out absolute top-0 left-0 w-6 h-6 bg-white border-2 border-gray-600 rounded-full;
  }

  input[type='checkbox']:checked ~ .thumb {
    @apply transform translate-x-full border-green-500;
  }

  input[type='checkbox']:checked ~ .track {
    @apply transform transition-colors bg-green-500;
  }

  input[type='checkbox']:disabled ~ .track {
    @apply bg-gray-500;
  }

  input[type='checkbox']:disabled ~ .thumb {
    @apply bg-gray-100 border-gray-500;
  }

  input[type='checkbox']:focus + .track,
  input[type='checkbox']:active + .track {
    /* @apply shadow-outline; */
  }
</style>

<div class="flex justify-center lg:flex">
  <label for="toggleTheme">
    <div class="switch">
      <input id="toggleTheme" name="toggleTheme" type="checkbox" class="sr-only" bind:checked on:change={toggleTheme} />
      <div class="track"></div>
      <div class="thumb"></div>
    </div>
  </label>
  <span>
      <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24" fill="none"
      xmlns="http://www.w3.org/2000/svg">
      <path
      d={moon}>
    </svg>
  </span>
</div>
<!-- <section>
   <pre>{JSON.stringify($store, undefined, '  ')}</pre>
  <pre>{JSON.stringify($theme, undefined, '  ')}</pre>
  <pre>{JSON.stringify(checked, undefined, '  ')}</pre>
</section> -->
