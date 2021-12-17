<script lang="ts">
    $: $theme, LogoSwitcher()

    import { theme } from '../../../../src/routes/store'
    import  DarkThemeLogo from  '$lib/assets/branding/png/color_last_name_nobkg.png'
    import LightThemeLogo from '$lib/assets/branding/png/last_name_black_nobkg.png'
    import socialMedia from '$lib/data/social_media';
    import {ContactInfo} from '$lib/data/contactInfo';
    import {Github} from '$lib/data/externalNavLinks'

    let date = new Date()
    let copyrightYear = date.getFullYear()
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
    <footer class="bg-white dark:bg-gray-800">
        <div class="container px-6 py-4 mx-auto">
            <div class="lg:flex">
                <div class="w-full -mx-6 lg:w-2/5">
                    <div class="px-6">
                        <div class="flex">
                            <a href="/" class="text-xl font-bold text-gray-800 dark:text-white hover:text-gray-700 dark:hover:text-gray-300">
                                    <img src="{logo}" alt="Gillis" width="200px" height="50px" >
                            </a>
                        </div>                        
                        <div class="flex mt-4 -mx-2">
                            {#each socialMedia as social}
                            {#if social.OnFooter }
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
                </div>

                <div class="mt-6 lg:mt-0 lg:flex-1">
                    <div class="grid grid-cols-2 gap-6 sm:grid-cols-3 md:grid-cols-4">
                        <div>
                            <a href="/resume" class="block mt-2 hover:underline">
                                <h3 class="text-gray-700 uppercase dark:text-white">Resume</h3>
                            </a>
                        </div>
                        <div>
                            <a href="{Github.Link}" class="block mt-2 hover:underline">
                                <h3 class="text-gray-700 uppercase dark:text-white">{Github.LinkText}</h3>
                            </a>
                        </div>       
                        <!-- <div>
                            <a href={ResumeDownload.Url} class="block mt-2 hover:underline">
                                <h3 class="text-gray-700 uppercase dark:text-white">{ResumeDownload.LinkText}</h3>
                            </a>
                        </div> -->
                        <div>
                            <h3 class="text-gray-700 uppercase dark:text-white">Contact Me</h3>
                            <span class="block mt-2 text-sm text-gray-600 dark:text-gray-400 hover:underline"> {ContactInfo.Phone} </span>
                            <a href="mailto:{ContactInfo.Email}" class="block mt-2 text-sm text-gray-600 dark:text-gray-400 hover:underline">{ContactInfo.Email}</a>
                            <span class="block mt-2 text-sm text-gray-600 dark:text-gray-400 hover:underline"> {ContactInfo.Address.City}, {ContactInfo.Address.State} </span>
                        </div>
                    </div>
                </div>
            </div>

            <hr class="h-px my-6 bg-gray-300 border-none dark:bg-gray-700">

            <div>
                <p class="text-center text-gray-800 dark:text-white">© {ContactInfo.FirstName} {ContactInfo.LastName} {copyrightYear} - All rights reserved</p>
            </div>
        </div>
    </footer>