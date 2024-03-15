<template>
  <div class="post-container">
    <h1 class="post-title mb">{{ post.title }}</h1>
    <div class="post-author mb">
      <div class="img"></div>
      <div class="name">{{ post.name }}</div>
      <div class="date">{{ post.date }}</div>
    </div>
    <div class="post-content mb">{{ post.content }}</div>
    <div class="post-img mb">
      <div class="item"></div>
      <div class="item"></div>
      <div class="item"></div>
    </div>
    <div class="post-bottom">
      <div class="tags">
        <div class="tag" v-for="tag in post.tag">{{ tag }}</div>
      </div>
      <div class="misc">
        <div class="item">點贊:{{ post.misc.like }} ·</div>
        <div class="item">收藏:{{ post.misc.sub }} ·</div>
        <div class="item">頻論:{{ post.misc.com }} ·</div>
        <div class="item">觀看:{{ post.misc.watch }}</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  post: {
    id: number;
    title: string;
    name: string;
    date: string;
    content: string;
    tag: string[];
    misc: {
      like: number;
      sub: number;
      com: number;
      watch: number;
    };
  };
}>();
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  color: #333;
}

.mb {
  margin-bottom: 8px;
}

.post-container {
  font-family: sans-serif;
  background-color: #fff;
  padding: 10px 20px;
  margin-bottom: 10px;
}

.post-title {
  font-size: 20px;
}

.post-author {
  display: flex;
}

.post-author .img {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background-color: #ccc;
  margin-right: 4px;
}

.post-author .name {
  margin-right: 8px;
}

.post-img {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}

.post-img .item {
  height: 80px;
  background-color: #ccc;
  border-radius: 8px;
}

.post-bottom {
  display: flex;
  flex-wrap: wrap;
  gap: 4px 10px;
}

.tags {
  display: flex;
  gap: 4px;
}

.tags .tag {
  font-size: 12px;
  background-color: #eee;
  padding: 4px;
  border-radius: 8px;
}

.misc {
  display: flex;
}

.misc .item {
  font-size: 12px;
  padding: 4px;
}
</style>
