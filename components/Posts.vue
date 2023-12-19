<template>
    <section class="pt-20 pb-32 overflow-hidden">
      <div class="container mx-auto px-4">
        <div class="md:max-w-lg mx-auto text-center mb-20">
          <h2 class="mb-4 font-heading font-semibold text-gray-900 text-4xl sm:text-7xl">Articles</h2>
        </div>
        <div class="flex flex-wrap -m-9">
          <div v-for="(post, index) in latestPosts" :key="index" class="w-full md:w-1/3 p-4">
            <a :href="post.url" class="group">
              <div class="group flex flex-col mb-5 overflow-hidden rounded-xl aspect-w-4 w-80 aspect-h-2 h-40">
                <img :src="post.image" class="object-fill w-full h-full transform group-hover:scale-110 transition ease-out duration-500 rounded-xl" alt="">
              </div>
              <p class="mb-4 font-heading font-medium text-xl text-gray-900 group-hover:underline">{{ post.title }}</p>
              <h2 class="font-heading font-medium text-xs uppercase text-gray-500 tracking-px">{{ post.category }}</h2>
            </a>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import { getDevtoPosts } from '~/services/devto';
  
  const latestPosts = ref([]);
  
  onMounted(async () => {
    const allPosts = await getDevtoPosts();
    latestPosts.value = allPosts.slice(0, 3).map(post => ({
      ...post,
      readingTime: `${post.reading_time} min read`,
      image: post.cover_image || createPlaceholderImage() 
    }));
  });
  
  function createPlaceholderImage() {
   
    return `https://via.placeholder.com/800x600.png?text=No+Image`;
  }
  </script>

  