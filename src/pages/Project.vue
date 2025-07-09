
<template>
    <section>
        <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
            <header class="text-center">
                <h2 class="font-moul text-xl font-bold text-gray-900 sm:text-3xl">{{ $t('my_project') }}  {{ projects.length }}</h2>

                <p class="mx-auto mt-4 max-w-md text-gray-500 sm:text-xl">
                    {{ $t('project_des') }} 
                </p>
            </header>

            <ul class="mt-8 grid gap-4 sm:grid-cols-2 lg:grid-cols-4">
                <li v-for="project in projects" :key="project.id">
                    <router-link :to="`project/${project.name}`"
                        class="block rounded-md border border-gray-300 p-4 shadow-sm sm:p-6">
                        <div class="sm:flex sm:justify-between sm:gap-4 lg:gap-6">
                            <div class="sm:order-last sm:shrink-0">
                                <img alt=""
                                    src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSGML54I96lfKHTRkKYer07Nz_mjTEZtzRZbw&s"
                                    class="size-16 rounded-full object-cover sm:size-[72px]" />
                            </div>

                            <div class="mt-4 sm:mt-0">
                                <h3 class="text-lg font-medium text-pretty text-gray-900">
                                    {{ project.name }}
                                </h3>

                                <p class="mt-1 text-sm text-gray-700">{{ $t('san_piseth') }}</p>

                                <p class="mt-4 line-clamp-2 text-sm text-pretty text-gray-700">
                                    {{ project.description }}
                                </p>
                            </div>
                        </div>

                        <dl class="mt-6 flex gap-4 lg:gap-6">
                            <div class="flex items-center gap-2">
                                <dt class="text-gray-700">
                                    <span class="sr-only"> {{ $t('public') }} </span>

                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                        stroke-width="1.5" stroke="currentColor" class="size-5">
                                        <path stroke-linecap="round" stroke-linejoin="round"
                                            d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5" />
                                    </svg>
                                </dt>

                                <dd class="text-xs text-gray-700">{{ $t('date') }}</dd>
                            </div>

                            <div class="flex items-center gap-2">
                                <dt class="text-gray-700">
                                    <span class="sr-only"> {{ $t('reading_time') }} </span>

                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                        stroke-width="1.5" stroke="currentColor" class="size-5">
                                        <path stroke-linecap="round" stroke-linejoin="round"
                                            d="M12 6.042A8.967 8.967 0 0 0 6 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 0 1 6 18c2.305 0 4.408.867 6 2.292m0-14.25a8.966 8.966 0 0 1 6-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0 0 18 18a8.967 8.967 0 0 0-6 2.292m0-14.25v14.25" />
                                    </svg>
                                </dt>

                                <dd class="text-xs text-gray-700">{{ $t('time') }}</dd>
                            </div>
                        </dl>
                    </router-link>
                </li>

            </ul>
        </div>
    </section>
</template>
<script>
import axios from 'axios';
export default {
    async mounted() {
        const response = await axios.get(`${import.meta.env.VITE_GITHUB_API}/pisethsan/repos?page=1&per_page=10`, {
            headers: {
                'Authorization': `Bearer ${import.meta.env.VITE_GITHUB_TOKEN}`,
            }
        }
        )
        this.projects = response.data;
    },
    data() {
        return {
            projects: []
        }
    }
}
</script>
