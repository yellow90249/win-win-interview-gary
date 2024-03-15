<template>
  <div>
    <Post v-for="post in postList" :post :key="post.id"></Post>
  </div>
</template>

<script setup lang="ts">
import Post from '@/components/Post.vue';
import { ref } from 'vue';
const postList = ref([
  {
    id: 1,
    title: 'Post Title',
    name: 'User',
    date: '2021.09.21',
    content:
      "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.",

    tag: ['英文', '故事', '精選優質'],
    misc: { like: 100, sub: 100, com: 100, watch: 100 },
  },
  {
    id: 1,
    title: 'Post Title',
    name: 'User',
    date: '2021.09.21',
    content:
      "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.",

    tag: ['日文', '文章'],
    misc: { like: 100, sub: 100, com: 100, watch: 100 },
  },
]);
</script>

<style>
body {
  background-color: #eee;
  margin: 0;
}
</style>
