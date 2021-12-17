
<script lang="ts">
    $: $theme, LogoSwitcher()
    import { theme } from '../../../../src/routes/store'
    import DarkThemeLogo from  '$lib/assets/branding/png/color_no_background.png'
    import LightThemeLogo from '$lib/assets/branding/png/black_no_background.png'
    import ToggleTheme from '../Buttons/ToggleTheme.svelte'
    import {Github} from '$lib/data/externalNavLinks'
    import socialMedia from '$lib/data/social_media'


    let logo
    function LogoSwitcher(){
        if($theme == 'dark'){
            logo = DarkThemeLogo
        }else{
            logo = LightThemeLogo
        }
    }
    LogoSwitcher();

</script>

<nav class="bg-white shadow dark:bg-gray-800">
    <div class="container px-6 py-4 mx-auto lg:flex lg:justify-between lg:items-center">
        <div class="lg:flex lg:items-center">
            <div class="flex items-center justify-between">
                <div>
                    <a class="text-2xl font-bold text-gray-800 dark:text-white lg:text-3xl hover:text-gray-700 dark:hover:text-gray-300" href="/">
                        <img src="{logo}" alt="Chris Gillis (Logo)" width="400px" >
                    </a>
                </div>

                <!-- Mobile menu button -->
                <div class="flex lg:hidden">
                    <button type="button" class="text-gray-500 dark:text-gray-200 hover:text-gray-600 dark:hover:text-gray-400 focus:outline-none focus:text-gray-600 dark:focus:text-gray-400" aria-label="toggle menu">
                        <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
                            <path fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"></path>
                        </svg>
                    </button>
                </div>
            </div>

            <div class="flex flex-col text-gray-600 capitalize dark:text-gray-300 lg:flex lg:px-16 lg:-mx-4 lg:flex-row lg:items-center">
                <a href="/resume" class="mt-2 lg:mt-0 lg:mx-4 hover:text-gray-800 dark:hover:text-gray-200">Resume</a>
                <a href={Github.Link} class="mt-2 lg:mt-0 lg:mx-4 hover:text-gray-800 dark:hover:text-gray-200">{Github.LinkText}</a>
                
                <!-- <a href="/blog" class="mt-2 lg:mt-0 lg:mx-4 hover:text-gray-800 dark:hover:text-gray-200">Blog</a> -->

                <!-- <div class="relative mt-4 lg:mt-0 lg:mx-4">
                    <span class="absolute inset-y-0 left-0 flex items-center pl-3">
                        <svg class="w-4 h-4 text-gray-600 dark:text-gray-300" viewBox="0 0 24 24" fill="none">
                            <path d="M21 21L15 15M17 10C17 13.866 13.866 17 10 17C6.13401 17 3 13.866 3 10C3 6.13401 6.13401 3 10 3C13.866 3 17 6.13401 17 10Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
                        </svg>
                    </span>

                    <input type="text" class="w-full py-1 pl-10 pr-4 text-gray-700 placeholder-gray-600 bg-white border-b border-gray-600 dark:placeholder-gray-300 dark:focus:border-gray-300 lg:w-56 lg:border-transparent dark:bg-gray-800 dark:text-gray-300 focus:outline-none focus:border-gray-600" placeholder="Search">
                </div> -->
            </div>
        </div>

        <div class="flex justify-center mt-6 lg:flex lg:mt-0 lg:-mx-2">
           <div class="mx-2">            
               <ToggleTheme ></ToggleTheme>
           </div>
               {#each socialMedia as social}
                    {#if social.OnHeaderNav }
                    <a href={social.ProfileUrl} class="mx-2 text-gray-600 dark:text-gray-300 hover:text-gray-500 dark:hover:text-gray-300"
                        aria-label={social.Name}>
                        <svg class="w-5 h-5 fill-current" xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 24 24">    
                            <path d={social.SvgPath}></path>
                        </svg>
                    </a>
                    {/if}
               {/each}
        </div>
    </div>
  </nav>