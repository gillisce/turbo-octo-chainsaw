<script lang="ts">
    import profileImage from '$lib/assets/img/bio_image.jpg' 
    import socialMedia from '$lib/data/social_media';
    import {Bio} from '$lib/data/bioSection_Content';

</script>

    <section class="bg-white dark:bg-gray-800">
        <div class="container px-6 py-8 mx-auto">
            <div class="items-center flex">
                <div class="lg:w-1/2">
                    <h2 class="text-3xl font-bold text-gray-800 dark:text-gray-100">Hi there! I’m Chris Gillis, I’m a web & software developer from Ohio</h2>
                    <div class="mt-4 text-gray-500 dark:text-gray-400 lg:max-w-md">
                        <div class="flex w-full max-w-sm mx-auto overflow-hidden bg-white rounded-lg shadow-md dark:bg-gray-800">        
                            <div class="px-4 py-2 -mx-3">
                                <div class="mx-3">
                                    <div class="text-sm text-gray-600 dark:text-gray-200">Driven full stack developer with a passion for thoughtful design, collaboration, and mentoring. </div>
                                </div>
                            </div>
                        </div>
                        I’ve always sought out opportunities and challenges that are interesting and meaningful to me. With every turn of my professional path, I’ve never stopped engaging my passion to design creative solutions to solve problems.
                        As a developer, I enjoy using my attention to detail, passion for learning new things and my work-ethic to bring solutions to life.  

                        <!-- {@html Bio} -->
                    </div>    

                    <div class="flex items-center mt-6 -mx-2">
                        {#each socialMedia as social}
                            {#if social.OnAboutSection }
                             <a class="mx-2" href="{social.ProfileUrl}" aria-label="{social.Name}">
                                <svg class="w-5 h-5 text-gray-700 fill-current dark:text-gray-200 hover:text-gray-600 dark:hover:text-gray-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                                    <path d={social.AboutSvgPath}/>
                                </svg>
                            </a>
                            {/if}
                        {/each}
                    </div>
                </div>

                <div class="mt-8 lg:mt-0 lg:w-1/2">
                    <div class="flex items-center justify-center lg:justify-end">
                        <div class="max-w-lg">
                            <img class="object-cover object-center w-full h-64 rounded-md shadow" src="{profileImage}" alt="Chris Gillis standing against wall">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>