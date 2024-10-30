<template>
    <div class="bg-white text-black py-10">
      <div class="container mx-auto">
        <h2 class="text-3xl font-bold">{{ post.title }}</h2>
        <p class="mt-4">{{ post.content }}</p>
        <NuxtLink to="/posts" class="text-blue-500 mt-5 inline-block">Back to Posts</NuxtLink>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        post: {},
        posts: [
          { slug: 'post-1', title: 'Post Title 1', content: 'Full content of post 1.' },
          { slug: 'post-2', title: 'Post Title 2', content: 'Full content of post 2.' },
          { slug: 'post-3', title: 'Post Title 3', content: 'Full content of post 3.' },
          { slug: 'post-4', title: 'Post Title 4', content: 'Full content of post 4.' },
          { slug: 'post-5', title: 'Post Title 5', content: 'Full content of post 5.' },
          { slug: 'post-6', title: 'Post Title 6', content: 'Full content of post 6.' }
        ]
      };
    },
    mounted() {
      const postSlug = this.$route.params.slug;
      this.post = this.posts.find(post => post.slug === postSlug) || {};
    }
  };
  </script>