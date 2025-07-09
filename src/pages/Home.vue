<template>
  <div class=" font-sans">
    <!-- Main container -->
    <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
      <!-- Grid for two-column layout -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-16 items-center ">
        
        <!-- Left Column: Text Content -->
    <section class=" flex items-center justify-center text-center bg-cover bg-center">
      <div class="bg-white bg-opacity-75 p-10 rounded-xl shadow-lg">
        <h1 class="text-4xl md:text-6xl font-extrabold mb-4">{{ $t('welcome') }}</h1>
        <p class="text-xl lg:text-2xl text-gray-700 mb-8 max-w-3xl mx-auto">
          {{ $t('skill') }}
        </p>
        <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
            <router-link to="/about" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 px-8 rounded-lg text-lg transition-transform transform hover:scale-105 duration-300 ease-in-out">
              {{ $t('about') }}
            </router-link>
            <router-link to="/project" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 px-8 rounded-lg text-lg transition-transform transform hover:scale-105 duration-300 ease-in-out">
              {{ $t('project') }}
            </router-link>
            <router-link to="/contact" class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 px-8 rounded-lg text-lg transition-transform transform hover:scale-105 duration-300 ease-in-out">
              {{ $t('contact') }}
            </router-link>
        </div>
      </div>
    </section>

        <!-- Right Column: Image -->
        <div class="flex items-center justify-center">
          <img 
            src="https://play-lh.googleusercontent.com/PEm_7LpC6ycxSFv1EJDUE_bIRUzZS-DFxkvoWSQXm2kUt9Y2bVFTacrqdwGHq9sgxjfx=w526-h296-rw" 
            alt="Placeholder image for the hero section" 
            class="border-4 border-white object-cover h-96 rounded-xl shadow-2xl w-full max-w-md lg:max-w-full h-auto object-cover transition-all duration-500 ease-in-out transform hover:scale-105 hover:shadow-xl hover:shadow-indigo-400/60"
            @error="onImageError"
          >
        </div>

      </div>
    </div>
  </div>




</template>
