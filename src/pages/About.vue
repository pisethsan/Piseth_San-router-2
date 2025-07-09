<template>
  <div class="font-sans mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
    <!-- Header Section -->
    <div class="bg-indigo-700 text-white text-center py-20">
      <div class="container mx-auto px-6">
        <h1 class="font-moul text-xl font-bold mb-2 sm:text-3xl">
          {{ $t('about_me') }}
        </h1>
        <p>
          {{ $t('about_des') }}
        </p>

        <!-- Flex Section: Text Left, Image Right -->
        <div class="mt-10 flex flex-col lg:flex-row items-start gap-8 text-left">
          <!-- Left: Text Content -->
          <div class="lg:w-1/2">
            <h3 class="text-xl font-bold mb-2">
              {{ $t('education') }}:
            </h3>
            <ul class="list-disc ml-6 mb-4">
              <li>RUPP: 2021–2022</li>
              <li>UMK-KPC: 2023–Now</li>
              <li>CADT: Now</li>
            </ul>

            <h3 class="text-xl font-bold mb-2">
              {{ $t('working_experience') }}:
            </h3>
            <ul class="list-disc ml-6">
              <li> Correctionnal Center 3: 2023–Now</li>
            </ul>
          </div>

          <!-- Right: Image -->
          <div class="lg:w-1/2">
          <img src="https://play-lh.googleusercontent.com/PEm_7LpC6ycxSFv1EJDUE_bIRUzZS-DFxkvoWSQXm2kUt9Y2bVFTacrqdwGHq9sgxjfx=w526-h296-rw" alt="cadt"
          class="border-4 border-white object-cover h-96 rounded-xl shadow-2xl w-full max-w-md lg:max-w-full h-auto object-cover transition-all duration-500 ease-in-out transform hover:scale-105 hover:shadow-xl hover:shadow-indigo-400/60"
            @error="onImageError"
          />
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
            <img
              src="https://cadt.edu.kh/wp-content/uploads/2021/11/NIPTICT-National-Institute-Officially-Rebranded-to-Cambodia-Academy-of-Digital-Technology-CADT-1-scaled.jpg"
              alt="CADT"
              
            />
          </div>
</template>
