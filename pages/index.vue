<template>
  <div class="bg-white text-black">
    <div class="relative">
      <section class="flex items-center justify-center h-screen">
        <div class="text-left">
          <h1 class="text-5xl font-bold">I'm Mahyar,</h1>
          <p class="mt-2 text-sm sm:text-md text-gray-600">Welcome to my persoanl blog!</p>
          <p class="mt-4 text-md sm:text-xl">Exploring the synergy of code and circuits.</p>
          <p class="mt-4 text-sm sm:text-md text-blue-400 transition-all hover:pl-1">
            <NuxtLink to="/about">About me ></NuxtLink>
          </p>
        </div>
      </section>
      <div class="flex items-center justify-center absolute bottom-5 w-screen">
        <p class=" text-sm text-gray-600">scroll down...</p>
      </div>
    </div>

    <section class="py-20">
      <div class="container mx-auto">
        <h2 class="text-3xl font-bold text-center">Blog Categories</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-10">
          <div class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">Category 1</h3>
            <p class="mt-2">Brief description of category 1.</p>
          </div>
          <div class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">Category 2</h3>
            <p class="mt-2">Brief description of category 2.</p>
          </div>
          <div class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">Category 3</h3>
            <p class="mt-2">Brief description of category 3.</p>
          </div>
        </div>

        <h2 class="text-3xl font-bold text-center mt-20">Recent Posts</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-10">
          <div class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">Post Title 1</h3>
            <p class="mt-2">Brief description of post 1.</p>
          </div>
          <div class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">Post Title 2</h3>
            <p class="mt-2">Brief description of post 2.</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
  
  <!-- <script>
  export default {
    head() {
      return {
        title: 'My Personal Blog',
        meta: [
          { hid: 'description', name: 'description', content: 'Aspiring electrical engineer and passionate programmer with a background in web and application development, robotics, and DevOps. Currently pursuing a degree in electrical engineering while exploring the intersection of technology and innovation.' },
        ],
      };
    },
  };
  </script> -->

  <script setup lang="ts">
  useSeoMeta({
    title: 'Mahyar Behzadi Blog',
    ogTitle: 'Mahyar Behzadi Blog',
    description: 'Aspiring electrical engineer and passionate programmer with a background in web and application development, robotics, and DevOps. Currently pursuing a degree in electrical engineering while exploring the intersection of technology and innovation.',
    ogDescription: 'Aspiring electrical engineer and passionate programmer with a background in web and application development, robotics, and DevOps. Currently pursuing a degree in electrical engineering while exploring the intersection of technology and innovation.',
    // ogImage: 'https://example.com/image.png',
    twitterCard: 'summary_large_image'
  });
  </script>
  
  <style scoped>
  /* additional custom styles */
  </style>