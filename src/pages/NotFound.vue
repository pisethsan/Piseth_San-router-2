<template>
  <!--
    This example requires updating your template:

    ```
    <html class="h-full">
    <body class="h-full">
    ```
  -->
  <main class="grid min-h-full place-items-center bg-white px-6 py-24 sm:py-32 lg:px-8">
    <div class="text-center">
      <p class="text-base font-semibold text-indigo-600">{{ $t('not_found') }}</p>
      <h1 class="mt-4 text-5xl font-semibold tracking-tight text-balance text-gray-900 sm:text-7xl">{{ $t('page_not_found') }}</h1>
      <p class="mt-6 text-lg font-medium text-pretty text-gray-500 sm:text-xl/8">{{ $t('text_not_found') }}</p>
      <div class="mt-10 flex items-center justify-center gap-x-6">
        <router-link to="/" class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-xs hover:bg-indigo-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">{{ $t('go_back_home') }}</router-link>
        <router-link to="/contact" class="text-sm font-semibold text-gray-900">{{ $t('contact_support') }} <span aria-hidden="true">&rarr;</span></router-link>
      </div>
    </div>
  </main>
</template>
