<template>
    <div class="bg-white text-black py-10">
      <div class="container mx-auto">
        <h2 class="text-3xl font-bold text-center">All Posts</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-10">
          <div v-for="post in paginatedPosts" :key="post.slug" class="bg-gray-100 p-5 rounded-lg shadow">
            <h3 class="text-xl font-semibold">
              <NuxtLink :to="`/posts/${post.slug}`">{{ post.title }}</NuxtLink>
            </h3>
            <p class="mt-2">{{ post.summary }}</p>
          </div>
        </div>
  
        <div class="flex justify-center mt-10">
          <button 
            @click="prevPage" 
            :disabled="currentPage === 1" 
            class="bg-blue-500 text-white px-4 py-2 rounded-md disabled:opacity-50">
            Previous
          </button>
          <span class="mx-4">Page {{ currentPage }} of {{ totalPages }}</span>
          <button 
            @click="nextPage" 
            :disabled="currentPage === totalPages" 
            class="bg-blue-500 text-white px-4 py-2 rounded-md disabled:opacity-50">
            Next
          </button>
        </div>
      </div>
    </div>
  </template>
  
<!-- <script lang="ts">
  export default {
    data() {
      return {
        posts: [
          { slug: 'post-1', title: 'Post Title 1', content: 'Full content of post 1.' },
          { slug: 'post-2', title: 'Post Title 2', content: 'Full content of post 2.' },
          { slug: 'post-3', title: 'Post Title 3', content: 'Full content of post 3.' },
          { slug: 'post-4', title: 'Post Title 4', content: 'Full content of post 4.' },
          { slug: 'post-5', title: 'Post Title 5', content: 'Full content of post 5.' },
          { slug: 'post-6', title: 'Post Title 6', content: 'Full content of post 6.' }
        ],
        currentPage: 1,
        postsPerPage: 5
      };
    },
    computed: {
      totalPages() {
        return Math.ceil(this.posts.length / this.postsPerPage);
      },
      paginatedPosts() {
        const start = (this.currentPage - 1) * this.postsPerPage;
        return this.posts.slice(start, start + this.postsPerPage);
      }
    },
    methods: {
			async fetchPosts() {
				// const response = await this.$axios.$get(`/api/posts?page=${this.currentPage}&limit=${this.postsPerPage}`);
				const { data: response } = await useFetch(`http://localhost:8000/api/posts?page=${this.currentPage}&limit=${this.postsPerPage}`);
				this.posts = response.data; // Adjust based on your API response structure
				this.totalPosts = response.total; // Assuming your API returns total count of posts
			},
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
        }
      },
      prevPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
        }
      },
			async mounted() {
				await this.fetchPosts();
			}
    }
  };
  </script> -->

<script lang="ts">
	import { defineComponent, ref, computed, onMounted } from 'vue';
	
	interface Post {
		slug: string;
		title: string;
		content: string;
	}
	
	export default defineComponent({
		setup() {
			const posts = ref<Post[]>([
				{ slug: 'post-1', title: 'Post Title 1', content: 'Full content of post 1.' },
				{ slug: 'post-2', title: 'Post Title 2', content: 'Full content of post 2.' },
				{ slug: 'post-3', title: 'Post Title 3', content: 'Full content of post 3.' },
				{ slug: 'post-4', title: 'Post Title 4', content: 'Full content of post 4.' },
				{ slug: 'post-5', title: 'Post Title 5', content: 'Full content of post 5.' },
				{ slug: 'post-6', title: 'Post Title 6', content: 'Full content of post 6.' }
			]);
			
			const currentPage = ref<number>(1);
			const postsPerPage = 5;
	
			const totalPages = computed(() => Math.ceil(posts.value.length / postsPerPage));
	
			const paginatedPosts = computed(() => {
				const start = (currentPage.value - 1) * postsPerPage;
				return posts.value.slice(start, start + postsPerPage);
			});
	
			const fetchPosts = async () => {
				const { data: response } = await useFetch(`http://localhost:8000/api/posts?page=${currentPage.value}&limit=${postsPerPage}`);
				posts.value = response.data; // Adjust based on your API response structure
				// Assuming your API returns total count of posts, you can set it here if needed
			};
	
			const nextPage = () => {
				if (currentPage.value < totalPages.value) {
					currentPage.value++;
				}
			};
	
			const prevPage = () => {
				if (currentPage.value > 1) {
					currentPage.value--;
				}
			};
	
			onMounted(() => {
				fetchPosts();
			});
	
			return {
				posts,
				currentPage,
				totalPages,
				paginatedPosts,
				fetchPosts,
				nextPage,
				prevPage
			};
		}
	});
</script>