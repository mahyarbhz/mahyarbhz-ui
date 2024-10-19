<template>
    <div class="bg-white text-black">
      <section class="flex items-center justify-center h-screen">
        <div class="text-center">
          <h1 class="text-5xl font-bold">Welcome, I'm Mahyar.</h1>
          <p class="mt-4 text-xl">Exploring the synergy of code and circuits.</p>
        </div>
      </section>
  
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
  
  <script>
  export default {
    head() {
      return {
        title: 'My Personal Blog',
        meta: [
          { hid: 'description', name: 'description', content: 'Welcome to my personal blog.' },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  /* additional custom styles */
  </style>